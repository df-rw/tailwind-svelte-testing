<script lang="ts">
    import { slide } from 'svelte/transition';

    let editing = false;
    const toggleEditing = () => {
        editing = !editing;
    };
</script>

<div class="m-4">
    <div class="border border-2 border-black">
        <button type="button" class="btn bg-sky-500" on:click={toggleEditing}>toggle editing</button>

        {#if !editing}
            <div class="bg-yellow-500">
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
                this is the first div
            </div>
        {:else}
            <div class="bg-green-500" transition:slide={{duration: 1000}}>
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
                this is the second div
            </div>
        {/if}
    </div>

    <div class="border border-2 border-green">
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
        this is the first div
    </div>
</div>
