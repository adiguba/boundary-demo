<script>
    let { children } = $props();
</script>

<header>
    <a href='/'>home</a>
    <a href='/onerror'>onerror</a>
    <a href='/failed'>failed</a>
    <a href='/client'>client</a>
</header>
<div>
    {@render children?.()}
</div>


<style>

    :global(body) {
        background: #f1f1f1;
    }

    header {
        display: flex;
        justify-content: center;
        gap: 1em;
    }

    div {
        margin: 1em auto;
        padding: 1em;
        max-width: 540px;
        border: 1px solid #ccc;
        background: #fff;
    }

    :global(pre) {
        border: 1px solid darkred;
        color: darkred;
        padding: 1em;
        background: #fff2f2;
    }
</style>