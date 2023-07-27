<script>
    import source from './doctors.md?raw'
    import SvelteMarkdown from "svelte-markdown";
</script>

<SvelteMarkdown {source} />
