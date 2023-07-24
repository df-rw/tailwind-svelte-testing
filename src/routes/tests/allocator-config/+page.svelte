<script lang="ts">
    const states = ['QLD', 'NSW', 'VIC', 'TAS', 'SA', 'WA', 'NT', 'NZ'];
    let chosenState = states[0];

    const corpOptions = ['Manually', 'Automatically, by property state'];
    let corpAllocation = corpOptions[0];

    const stateOptions = [
        'Manually',
        'Automatically to closest office',
        'Automatically match property suburb to office name',
    ];
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

    let allocationOptionsOffice: string = [];
</script>

<div class="m-4">
    <fieldset class="border border-solid border-gray-700 p-4">
        <legend>Corporate view - Administrator Options</legend>

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
    <fieldset class="border border-solid border-gray-700 p-4 grid">
        <legend>Corporate view - Allocation options for states</legend>

        <div>
            <div>What state do you want to set allocation options for?</div>
            <select bind:value={chosenState}>
                {#each states as s}
                    <option value={s}>{s}</option>
                {/each}
            </select>
        </div>

        <div class="mt-4">Current allocation options for {chosenState}:</div>
        <div>
            {#each stateOptions as s}
                <div>
                    <input type="checkbox" bind:group={allocationOptions} value={s} /> {s}
                </div>
            {/each}
        </div>
    </fieldset>
</div>

<div class="m-4">
    <fieldset class="border border-solid border-gray-700 p-4">
        <legend>Queensland State Administrator view - Allocation Options</legend>

        <div>How would you like to allocate new referrals?</div>
        {#each allocationOptions as stateOption}
            <div>
                <input type="radio" value={stateOption} bind:group={stateAllocation} />
                {stateOption}
            </div>
        {/each}
    </fieldset>
</div>

<div class="m-4">
    <fieldset class="border border-solid border-gray-700 p-4">
        <legend>Queensland State Administrator view - Allocation Options for offices</legend>

        <div>
            <div>What office do you want to set allocation options for?</div>
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
                    <input type="checkbox" bind:group={allocationOptionsOffice} value={s} /> {s}
                </div>
            {/each}
        </div>
    </fieldset>
</div>


<div class="m-4">
    <fieldset class="border border-solid border-gray-700 p-4">
        <legend>Ray White New Farm Administrator view - Allocation Options</legend>

        <div>How would you like to allocate new referrals?</div>
        {#each officeOptions as officeOption}
            <div>
                <input type="radio" value={officeOption} bind:group={officeAllocation} />
                {officeOption}
            </div>
        {/each}
    </fieldset>
</div>
