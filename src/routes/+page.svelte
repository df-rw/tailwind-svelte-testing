<script lang="ts">
    const samples = [
        {
            tailwindReference:
                'https://tailwindui.com/components/application-ui/application-shells/sidebar#component-5548358cb34897c6b28551f2ad885eec',
            title: 'Dark sidebar with header',
            route: '/samples/dark-sidebar-with-header',
        },
        {
            tailwindReference: 'https://tailwindcss.com/docs/plugins#forms',
            title: 'Form components',
            route: '/samples/form-components',
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/navigation/steps',
            title: 'Steppers',
            route: '/samples/steps',
        },
        {
            tailwindReference:
                'https://tailwindui.com/components/application-ui/overlays/slide-overs',
            title: 'Slide overlays (basic)',
            route: '/samples/slide-overlay-basic',
        },
        {
            tailwindReference:
                'https://tailwindui.com/components/application-ui/overlays/slide-overs#component-b76ed25b74c40b7f3a181393e2b7742f',
            title: 'Slide overlays (with form)',
            route: '/samples/slide-overlay-with-form',
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/layout/dividers',
            title: 'Dividers',
            route: '/samples/dividers',
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/forms/comboboxes',
            title: 'Comboboxes',
            route: '/samples/comboboxes',
        },
        {
            tailwindReference:
                'https://tailwindui.com/components/application-ui/forms/input-groups',
            title: 'Input Groups',
            route: '/samples/input-groups',
        },
        {
            tailwindReference: 'https://tailwindcss.com/docs/ring-width',
            title: 'Ring width',
            route: '/samples/ring-width',
        },
    ];

    const tests = [
        {
            title: 'Allocator config',
            route: '/tests/allocator-config',
        },
        {
            title: 'Notification settings',
            route: '/tests/notification-settings',
        },
    ];
</script>

<div class="m-4">
    <div>
        <h1 class="text-xl">Samples</h1>
        <ul class="m-4 list-disc">
            {#each samples as sample}
                <li>
                    <a class="hover:underline" href={sample.route}>{sample.title}</a> (<a
                        class="hover:underline"
                        href={sample.tailwindReference}>tailwind docs</a
                    >)
                </li>
            {/each}
        </ul>
    </div>

    <div>
        <h1 class="text-xl">Tests</h1>
        <ul class="m-4 list-disc">
            {#each tests as test}
                <li>
                    <a class="hover:underline" href={test.route}>{test.title}</a>
                </li>
            {/each}
        </ul>
    </div>

    <div>
        <hr class="mb-4 mt-4" />

        <h1 class="text-xl">Tailwind doc reference</h1>
        <ul class="m-4 list-disc">
            <li>
                <a
                    class="hover:underline"
                    target="_blank"
                    href="https://tailwindcss.com/docs/adding-custom-styles">Adding Custom Styles</a
                >
            </li>
            <li>
                <a
                    class="hover:underline"
                    target="_blank"
                    href="https://tailwindcss.com/docs/reusing-styles">Reusing Styles</a
                >
            </li>
            <li>
                <a
                    class="hover:underline"
                    target="_blank"
                    href="https://tailwindcss.com/docs/adding-custom-styles#adding-component-classes"
                    >Adding component classes</a
                >
            </li>
            <li>
                <a
                    class="hover:underline"
                    target="_blank"
                    href="https://github.com/tailwindlabs/tailwindcss-forms"
                    >TailwindCSS Forms plugin</a
                >
            </li>
            <li>
                <a
                    class="hover:underline"
                    target="_blank"
                    href="https://tailwindcss.com/docs/plugins#css-in-js-syntax">CSS-in-JS syntax</a
                >
            </li>
        </ul>
    </div>
</div>
