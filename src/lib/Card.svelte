<script>
    let { children, ...rest } = $props();
</script>

<div {...rest} class="card">
    {@render children?.()}
</div>

<style>
    .card {
        display: flex;
        padding: 20px;
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
        align-self: stretch;
        position: relative;

        border-radius: 5px;
        border: 1px solid var(--Tertiary-Steger-Silver, #a7a5aa);
    }
</style>
