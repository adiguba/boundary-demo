<script>
    import { browser } from "$app/environment";
    import ComponentThatErrors from "$lib/ComponentThatErrors.svelte";

    let boom = $state(!browser);
</script>

<h1>client</h1>

<p>This page use a <code>&ltsvelte:boundary&gt;</code> with a component that fail only on server-side.</p>

<svelte:boundary>
    <ComponentThatErrors boom={boom}/>
    {#snippet failed(err, reset)}
        <pre>Oops, an error occurred! <button onclick={()=>{
            boom = false;
            reset();
        }}>Try again</button></pre>
    {/snippet}
</svelte:boundary>