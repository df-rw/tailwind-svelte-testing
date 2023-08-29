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
    import { createEventDispatcher } from 'svelte';

    /* eslint-disable @typescript-eslint/no-explicit-any */
    export let search: (s: string) => Promise<Array<any>>;
    export let label: (i: any) => string;
    export let itemFormat: (i: any) => string;

    const dispatch = createEventDispatcher();

    let searchTerm: string;
    let timeout: ReturnType<typeof setTimeout>;
    let loading = false;
    let possibles: any[] | undefined = undefined;
    /* eslint-enable */

    const keyUp = () => {
        if (!searchTerm) {
            possibles = undefined;
            return;
        }

        if (timeout) {
            clearTimeout(timeout);
        }

        timeout = setTimeout(async () => {
            loading = true;
            possibles = await search(searchTerm);
            loading = false;
        }, 200);
    };

    const select = (i: any) => {
        // eslint-enabled @typescript-eslint/no-explicit-any
        dispatch('chosen', i);
        searchTerm = label(i);
        possibles = undefined;
    };
</script>

<p>
    {#if loading}loading{:else}idle{/if}
</p>

<div class="relative">
    <input type="search" role="combobox" bind:value={searchTerm} on:keyup={keyUp} />

    {#if possibles}
        {#if possibles.length > 0}
            <ul
                class="absolute z-10 mt-1 overflow-auto border border-black bg-white"
                role="listbox"
            >
                {#each possibles as p}
                    <!-- eslint-disable svelte/no-at-html-tags -->
                    <li
                        class="relative py-2 pl-3 pr-9 hover:cursor-pointer"
                        on:click={() => select(p)}
                    >
                        {@html itemFormat(p)}
                    </li>
                {/each}
            </ul>
        {:else}
            <p>no results</p>
        {/if}
    {/if}
</div>
