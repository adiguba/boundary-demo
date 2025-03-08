<script>
    import ComponentThatErrors from "$lib/ComponentThatErrors.svelte";

    /** @type {any} */
    let error = $state();
    /** @type {(() => void) | undefined} */
    let reset = $state();

    let boom = $state(true);

  
</script>

<h1>onerror</h1>

<p>This page use a <code>&ltsvelte:boundary&gt;</code> with a <code>onerror</code> to handle the error : </p>

{#if error}
    <pre>Oops, an error occurred! <button onclick={()=>{
        boom = false;
        reset?.();
        error = null;
    }}>Try again</button></pre>
{/if}

<svelte:boundary onerror={ (e,r) => { error = e; reset = r;}}>
    <ComponentThatErrors boom={boom}/>
</svelte:boundary>