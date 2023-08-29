<script lang="ts">
    const states = ['QLD', 'NSW', 'VIC', 'TAS', 'SA', 'WA', 'NT', 'NZ'];
    let chosenState = states[0];

    const corpOptions = [
        'Manually',
        'Automatically to closest office',
        'Automatically match property suburb to office name',
    ];
    let corpAllocation = corpOptions[0];

    const stateOptions = ['Manually'];
    let stateAllocation = stateOptions[0];

    const officeOptions = [
        'Manually',
        'Automatically round robin by agent name',
        'Automatically random agent',
    ];
    let officeAllocation = officeOptions[0];

    let allocationOptions: string[] = [];

    const offices = ['Ray White New Farm', 'Ray White West End', 'Ray White Bulimba'];
    let chosenOffice = offices[0];

    let allocationOptionsOffice: string[] = [];
    $: officeAllocation = allocationOptionsOffice[0] ?? '';

    const classFieldset = 'border border-solid border-gray-700 p-4';
    const classLegend = 'px-1';
</script>

<div class="m-4">
    <fieldset class={classFieldset}>
        <legend class={classLegend}>Corporate view - Administrator Options</legend>

        <div>How would you like to allocate new referrals?</div>
        {#each corpOptions as corpOption}
            <div>
                <input type="radio" value={corpOption} bind:group={corpAllocation} />
                {corpOption}
            </div>
        {/each}
    </fieldset>
</div>

<div class="m-4">
    <fieldset class={classFieldset}>
        <legend class={classLegend}>Corporate view - Allocation Options for offices</legend>

        <div>
            <div>What office do you want to set allocation options for?</div>
            <select>
                <option>Queensland</option>
            </select>
            <select bind:value={chosenOffice}>
                {#each offices as o}
                    <option value={o}>{o}</option>
                {/each}
            </select>
        </div>

        <div class="mt-4">Current allocation options for {chosenOffice}:</div>
        <div>
            {#each officeOptions as s}
                <div>
                    <input type="checkbox" bind:group={allocationOptionsOffice} value={s} />
                    {s}
                </div>
            {/each}
        </div>
    </fieldset>
</div>

<div class="m-4">
    <fieldset class={classFieldset}>
        <legend class={classLegend}>Ray White New Farm Admini view - Allocation Options</legend>

        <div>How would you like to allocate new referrals?</div>
        {#each allocationOptionsOffice as officeOption}
            <div>
                <input type="radio" value={officeOption} bind:group={officeAllocation} />
                {officeOption}
            </div>
        {/each}
    </fieldset>
</div>
