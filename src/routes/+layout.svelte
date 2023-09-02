
<nav class="h-15 bg-yellow-100">
    <div class="max-w-5xl mx-auto">
        <div class="flex ">
            <div class="my-auto p-4 hover:bg-yellow-300 rounded-lg"><a href="/layout">Layout</a></div>
            <div class="my-auto p-4 hover:bg-yellow-300 rounded-lg"><a href="/chart">Chart</a></div>
            <div class="my-auto p-4 hover:bg-yellow-300 rounded-lg"><a href="/map">Map</a></div>
        </div>
    </div>
</nav>

<slot />


<script>
    import "../app.css";
</script>

<style lang="postcss">
    :global(html) {
      background-color: theme(colors.gray.100);
    }
</style>