<script lang="ts">
    import { createEventDispatcher } from 'svelte';

    interface Person {
        name: string;
        email: string;
        business: string;
    }

    const names: Person[] = [
        { name: 'Alice', email: 'Alice@foo.com', business: 'Alice productions' },
        { name: 'Bob', email: 'Bob@foo.com', business: 'Bob productions' },
        { name: 'Carol', email: 'Carol@foo.com', business: 'Carol productions' },
        { name: 'David', email: 'David@foo.com', business: 'David productions' },
        { name: 'Elizabeth', email: 'Elizabeth@foo.com', business: 'Elizabeth productions' },
        { name: 'Fred', email: 'Fred@foo.com', business: 'Fred productions' },
        { name: 'Gabriel', email: 'Gabriel@foo.com', business: 'Gabriel productions' },
        { name: 'Holly', email: 'Holly@foo.com', business: 'Holly productions' },
        { name: 'Ian', email: 'Ian@foo.com', business: 'Ian productions' },
        { name: 'Janice', email: 'Janice@foo.com', business: 'Janice productions' },
        { name: 'Kyle', email: 'Kyle@foo.com', business: 'Kyle productions' },
    ];

    const dispatch = createEventDispatcher();

    let searchTerm = '';
    let possibles: Person[] = [];
    let loading = false;

    const stall = (secs: number) => new Promise((r) => setTimeout(() => r(null), secs * 1000));

    const getPersons = async (s: string) => {
        if (s.length === 0) {
            return [];
        }
        const lowerS = s.toLowerCase();

        await stall(1);

        return names.filter((n) => n.name.toLowerCase().includes(lowerS));
    };

    let timeout: ReturnType<typeof setTimeout>;
    const keyUp = () => {
        if (timeout) {
            clearTimeout(timeout);
        }
        timeout = setTimeout(async () => {
            loading = true;
            possibles = await getPersons(searchTerm).then((data) => data.slice(0, 5));
            loading = false;
        }, 200);
    };

    const select = (p: Person) => {
        searchTerm = p.name;
        possibles = [];
        dispatch('chosen', p);
    };

    const clear = () => {
        searchTerm = '';
        possibles = [];
        dispatch('chosen', undefined);
    };
</script>

<div class="m-4">
    <label for="combobox" class="block text-sm font-medium leading-6 text-gray-900"
        >Choose a person</label
    >
    <div class="relative mt-2">
        <input
            id="combobox"
            type="text"
            class="w-full rounded-md border-0 bg-white py-1.5 pl-3 pr-12 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
            role="combobox"
            aria-controls="options"
            aria-expanded="false"
            bind:value={searchTerm}
            on:keyup={keyUp}
        />
        <button
            type="button"
            class="absolute inset-y-0 right-0 flex items-center rounded-r-md px-2 focus:outline-none"
            on:click={clear}
            disabled
            >{#if loading}S{:else}X{/if}</button
        >

        {#if possibles.length}
            <ul
                class="absolute z-10 mt-1 max-h-60 w-full overflow-auto rounded-md bg-white py-1 text-base shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none sm:text-sm"
                id="options"
                role="listbox"
            >
                <!--
        Combobox option, manage highlight styles based on mouseenter/mouseleave and keyboard navigation.

        Active: "text-white bg-indigo-600", Not Active: "text-gray-900"
      -->
                {#each possibles as p}
                    <li
                        class="relative cursor-default select-none py-2 pl-3 pr-9 text-gray-900 hover:bg-indigo-600 hover:text-white"
                        id="option-0"
                        role="option"
                        tabindex="-1"
                        on:mousedown={() => select(p)}
                    >
                        <!-- Selected: "font-semibold" -->
                        <span class="block truncate"
                            >{p.name} - {p.email}<br /><span class="text-sm">{p.business}</span
                            ></span
                        >
                    </li>{/each}
            </ul>
        {/if}
    </div>

    <p>here's some more stuff</p>
</div>
