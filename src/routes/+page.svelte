<script lang="ts">
    const samples = [
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/application-shells/sidebar#component-5548358cb34897c6b28551f2ad885eec',
            title: 'Dark sidebar with header',
            route: '/dark-sidebar-with-header',
        },
        {
            tailwindReference: 'https://tailwindcss.com/docs/plugins#forms',
            title: 'Form components',
            route: '/form-components',
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/navigation/steps',
            title: 'Steppers',
            route: '/steps'
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/overlays/slide-overs',
            title: 'Slide overlays (basic)',
            route: '/slide-overlay-basic'
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/overlays/slide-overs#component-b76ed25b74c40b7f3a181393e2b7742f',
            title: 'Slide overlays (with form)',
            route: '/slide-overlay-with-form'
        },
        {
            tailwindReference: 'https://tailwindui.com/components/application-ui/layout/dividers',
            title: 'Dividers',
            route: '/dividers',
        },
    ];
</script>

<div class="m-4">
    <div>
        <hr class="mt-4 mb-4" />

        <h1 class="text-xl">Samples</h1>
        <ul class="list-disc m-4">
            {#each samples as sample}
                <li><a class="hover:underline" href={sample.route}>{sample.title}</a> (<a class="hover:underline" href={sample.tailwindReference}>tailwind docs</a>)</li>
            {/each}
        </ul>
    </div>

    <div>
        <hr class="mt-4 mb-4" />

        <h1 class="text-xl">Tailwind doc reference</h1>
        <ul class="list-disc m-4">
            <li><a class="hover:underline" target="_blank" href="https://tailwindcss.com/docs/adding-custom-styles">Adding Custom Styles</a></li>
            <li><a class="hover:underline" target="_blank" href="https://tailwindcss.com/docs/reusing-styles">Reusing Styles</a></li>
            <li><a class="hover:underline" target="_blank" href="https://tailwindcss.com/docs/adding-custom-styles#adding-component-classes">Adding component classes</a></li>
            <li><a class="hover:underline" target="_blank" href="https://github.com/tailwindlabs/tailwindcss-forms">TailwindCSS Forms plugin</a></li>
            <li><a class="hover:underline" target="_blank" href="https://tailwindcss.com/docs/plugins#css-in-js-syntax">CSS-in-JS syntax</a></li>
        </ul>
    </div>

</div>
