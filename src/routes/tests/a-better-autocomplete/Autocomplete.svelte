<script lang="ts">
    /*
     * Jono pointed me at <script generics="T"> to allow for generic
     * components. Not formalised yet:
     * - https://github.com/sveltejs/language-tools/issues/273
     * - https://github.com/sveltejs/rfcs/pull/38
     *
     * Turn the linter off and use callbacks for now, but this should
     * be revisited once the RFC makes it into the language.
     */

    /* eslint-disable @typescript-eslint/no-explicit-any */
    export let search: (s: string) => Promise<Array<any>>;
    export let itemFormat: (p: any) => string;

    let searchTerm: string;
    let timeout: ReturnType<typeof setTimeout>;
    let loading = false;
    let possibles: any[] | undefined = [];
    /* eslint-enable */

    const keyUp = (t: string) => {
        if (!t) {
            possibles = undefined;
            return;
        }

        if (timeout) {
            clearTimeout(timeout);
        }

        timeout = setTimeout(async () => {
            loading = true;
            possibles = await search(t);
            loading = false;
        }, 200);
    };

    $: keyUp(searchTerm);
</script>

<p>
    {#if loading}loading{:else}idle{/if}
</p>

<div>
    <input
        type="search"
        role="combobox"
        aria-controls="options"
        aria-expanded="false"
        bind:value={searchTerm}
    />
</div>

{#if possibles}
    {#if possibles.length > 0}
        <ul>
            {#each possibles as p}
                <!-- eslint-disable svelte/no-at-html-tags -->
                <li>{@html itemFormat(p)}</li>
            {/each}
        </ul>
    {:else}
        <p>no results</p>
    {/if}
{/if}
