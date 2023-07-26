<script lang="ts">
    import '../app.css';
</script>

<div class="flex h-full flex-col">
    <div class="m-4">
        <a href="/" class="underline">home</a>
        <hr class="mt-4" />
    </div>

    <div class="grow">
        <slot />
    </div>

    <div class="p-4">&copy; 2023 this | is | the | footer</div>
</div>
