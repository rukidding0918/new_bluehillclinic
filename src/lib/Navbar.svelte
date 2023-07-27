<script>
    import Logo from '$lib/Logo.svelte'
    import Nav from '$lib/Nav.svelte'
    let size = 24;
</script>


<div class="navbar">
    <div class="upper-nav">
        <Logo {size} />
        <p class="title">청구경희한의원</p>
        <Nav />
    </div>

    <div class="lower-nav uk-flex">
        <div class="lower-nav-item">추나요법</div>
        <div class="lower-nav-item">교통사고</div>
        <div class="lower-nav-item">다이어트</div>
        <div class="lower-nav-item">공진단</div>
        <div class="lower-nav-item">공진단</div>
        <div class="lower-nav-item">공진단</div>
        <div class="lower-nav-item">공진단</div>
    </div>
</div>

<style>
    .upper-nav {
        /*background-color: #f4b41a;*/
        color: var(--primary-color);
        display: flex;
        padding-left: 15px;
    }
    .title {font-weight: bold; margin: 10px;}
    .lower-nav {
        margin: 0 auto;
        align-items: center;
        background-color: var(--primary-color);
        height: 44px;
        overflow: scroll;
        white-space: nowrap;
        gap: 10px;
    }
    .lower-nav::-webkit-scrollbar {
        display: none;
    }
    .lower-nav-item {
        color: #eeeeee;
        margin: 10px 0;
        border: 1px solid #eee;
        border-radius: 10px;
        padding: 2px 3px;
    }
    .lower-nav-item:first-child {
        margin-left: 10px;
    }
</style>