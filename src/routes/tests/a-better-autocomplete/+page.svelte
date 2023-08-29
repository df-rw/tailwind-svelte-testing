<script lang="ts">
    import Autocomplete from './Autocomplete.svelte';
    import type { Person, Car } from './types';

    const stall = (msecs: number) => new Promise((r) => setTimeout(() => r(null), msecs));

    const MAX_RESULTS = 5;

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
    const getPersons = async (term: string) => {
        await stall(500);
        const lowerTerm = term.trim().toLowerCase();
        return people.filter((p) => p.name.toLowerCase().includes(lowerTerm)).slice(0, MAX_RESULTS);
    };
    const formatPerson = (p: Person) => {
        return `${p.name} - ${p.email}<br /><span class="text-sm">${p.business}</span>`;
    };
    const labelPerson = (p: Person) => {
        return p.name;
    };
    const gotPerson = (event: CustomEvent) => {
        console.log({ person: event.detail });
    };

    const cars: Car[] = [
        { make: 'Subaru', model: 'XV', year: 2012 },
        { make: 'Datsun', model: '120Y', year: 1977 },
        { make: 'Datsun', model: '180B', year: 1975 },
        { make: 'BYD', model: 'Atto3', year: 2022 },
    ];
    const getCars = async (term: string) => {
        await stall(500);
        const lowerTerm = term.trim().toLowerCase();
        return cars.filter(
            (c) =>
                c.make.toLowerCase().includes(lowerTerm) ||
                c.model.toLowerCase().includes(lowerTerm) ||
                c.year.toString().includes(lowerTerm)
        );
    };
    const formatCar = (c: Car) => {
        return `${c.make} - ${c.model} - ${c.year}`;
    };
    const labelCar = (c: Car) => formatCar(c);
    const gotCar = (event: CustomEvent) => {
        console.log({ car: event.detail });
    };
</script>

<div class="m-4">
    <Autocomplete
        search={getPersons}
        itemFormat={formatPerson}
        label={labelPerson}
        on:chosen={gotPerson}
    />
    <Autocomplete search={getCars} itemFormat={formatCar} label={labelCar} on:chosen={gotCar} />
</div>
