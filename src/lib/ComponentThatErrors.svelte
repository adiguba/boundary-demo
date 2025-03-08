<script>
    let { boom = false } = $props();

    function message() {
        if (boom) {
            throw new Error('💣 BOOM !!! 💣');
        }
        return "It's work"
    }

</script>

<p>{message()}</p>
<img src='/firework.webp' alt=''/>