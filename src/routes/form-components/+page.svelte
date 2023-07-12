<script lang="ts">
    const types = [
        'text',
        'password',
        'email',
        'number',
        'url',
        'date',
        'datetime-local',
        'month',
        'week',
        'time',
        'search',
        'tel',
    ];
</script>

<div class="m-4">
    <h1 class="text-2xl">Inputs</h1>
    <ul class="list-disc m-4">
        {#each types as type}
            <li><input {type} placeholder={type} /></li>
        {/each}
    </ul>

    <hr class="mt-4 mb-4" />

    <h1 class="text-2xl">checkboxes</h1>
    <ul>
        <li><label><input type="checkbox" />one</label></li>
        <li><label><input type="checkbox" />two</label></li>
        <li><label><input type="checkbox" />three</label></li>
    </ul>

    <hr class="mt-4 mb-4" />

    <h1 class="text-2xl">radio group</h1>
    <ul>
        <li><label><input type="radio" name="radio-group" />one</label></li>
        <li><label><input type="radio" name="radio-group" />two</label></li>
        <li><label><input type="radio" name="radio-group" />three</label></li>
    </ul>

    <hr class="mt-4 mb-4" />

    <h1 class="text-2xl">buttons</h1>
    <ul>
        <li><button type="button">unstyled normal</button></li>
        <li>
            <button type="button" class="local-button">locally-styled button</button> (see
            <code>&lt;style&gt;</code> tag in the code for this page)
        </li>
    </ul>

    <hr class="mt-4 mb-4" />

    <h1 class="text-2xl">select</h1>
    <ul class="pb-8">
        <li>
            unstyled <select>
                <option>one</option>
                <option>two</option>
                <option>three</option>
            </select>
        </li>
        <li>
            <a
                href="https://tailwindui.com/components/application-ui/forms/select-menus#component-79592f355ca6f6e3b081e0158109981c"
                class="hover:underline">simple native (from tailwind-ui)</a
            ><select
                id="location"
                name="location"
                class="mt-2 block w-full rounded-md border-0 py-1.5 pl-3 pr-10 text-gray-900 ring-1 ring-inset ring-gray-300 focus:ring-2 focus:ring-indigo-600 sm:text-sm sm:leading-6"
            >
                <option>United States</option>
                <option selected>Canada</option>
                <option>Mexico</option>
            </select>
        </li>
    </ul>
</div>

<style>
    .local-button {
        border: 1px solid black;
        padding: 5px;
    }
</style>
