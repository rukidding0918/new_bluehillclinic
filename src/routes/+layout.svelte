<script>
    import Notification from "$lib/Notification.svelte";
    import Navbar from "$lib/Navbar.svelte";

</script>

<svelte:head>
</svelte:head>

<Notification />
<Navbar />

<div class="uk-container uk-container-small">
    <div class="uk-margin-top">
        <slot />
    </div>
</div>