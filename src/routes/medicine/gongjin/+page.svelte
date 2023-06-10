<script>
    import source from './content.md?raw'
    import { TypographyProvider} from '@svelteuidev/core'
    import SvelteMarkdown from "svelte-markdown";
</script>

<TypographyProvider>
    <SvelteMarkdown {source} />
</TypographyProvider>