<script lang="ts">
    import Autocomplete from './Autocomplete.svelte';
    import type { Person } from './types';

    const stall = (secs: number) => new Promise((r) => setTimeout(() => r(null), secs * 1000));

    const people: Person[] = [
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

    let chosen: Person;

    const getPersons = async (s: string) => {
        if (s.length === 0) {
            return [];
        }
        const lowerS = s.toLowerCase();

        await stall(1);

        return people.filter((n) => n.name.toLowerCase().includes(lowerS)).slice(0, 5);
    };

    const handleChosen = (event: CustomEvent) => {
        chosen = event.detail;
    };
</script>

<div class="m-4 flex flex-col gap-4">
    <Autocomplete cb={getPersons} on:chosen={handleChosen} />

    {#if chosen}
        <p>Chosen person</p>
        <pre class="text-xs">
{JSON.stringify(chosen, null, ' ')}
        </pre>
    {/if}
    <p>Choose from:</p>
    <ul class="ml-4 list-disc">
        {#each people as person}
            <li>
                {person.name}
            </li>
        {/each}
    </ul>
</div>
