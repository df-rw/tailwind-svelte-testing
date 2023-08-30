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
    export let itemFormat: (i: any) => string;
    export let chosenFormat: (i: any) => string;

    const dispatch = createEventDispatcher();

    let searchTerm: string;
    let timeout: ReturnType<typeof setTimeout>;
    let loading = false;
    let possibles: any[] | undefined = undefined;
    /* eslint-enable */

    const handleInput = () => {
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
            if (searchTerm === '') {
                possibles = undefined;
            }
            loading = false;
        }, 200);
    };

    /* eslint-disable @typescript-eslint/no-explicit-any */
    const select = (i: any) => {
        dispatch('chosen', i);
        searchTerm = chosenFormat(i);
        possibles = undefined;
    };

    $: if (searchTerm === '') {
        possibles = undefined;
    }
</script>

<p>
    {#if loading}loading{:else}idle{/if}
</p>

<div class="relative">
    <input type="search" class="w-full rounded-md" bind:value={searchTerm} on:input={handleInput} />

    {#if possibles}
            <ul
                class="absolute w-full z-10 mt-1 overflow-auto border border-black rounded-md bg-white"
                role="listbox"
            >
                {#if possibles.length > 0}
                    {#each possibles as p}
                        <li class="relative hover:bg-black hover:text-white">
                            <!-- eslint-disable svelte/no-at-html-tags -->
                            <button type="button" class="w-full text-left pl-2 py-2" on:click|preventDefault={() => select(p)}
                                >{@html itemFormat(p)}</button
                            >
                        </li>
                    {/each}
                {:else}
                    <li class="relative pl-2 py-2">No results</li>
                {/if}
            </ul>
    {/if}
</div>
