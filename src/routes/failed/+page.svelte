<script>
    import ComponentThatErrors from "$lib/ComponentThatErrors.svelte";

    let boom = $state(true);
</script>

<h1>failed</h1>

<p>This page use a <code>&ltsvelte:boundary&gt;</code> with a <code>failed</code> snippet to handle the error : </p>

<svelte:boundary>
    <ComponentThatErrors boom={boom}/>
    {#snippet failed(err, reset)}
        <pre>Oops, an error occurred! <button onclick={()=>{
            boom = false;
            reset();
        }}>Try again</button></pre>
    {/snippet}
</svelte:boundary>