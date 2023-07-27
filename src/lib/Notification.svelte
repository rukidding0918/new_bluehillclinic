<script>
    import Siema from 'siema';
    import {onMount} from "svelte";

    let screenWidth;
    let slider, prev, next
    let select = 0

    onMount(()=>{
        slider = new Siema({
            selector: '.siema',
            duration: 200,
            easing: 'ease-out',
            perPage: 1,
            startIndex: 0,
            draggable: true,
            multipleDrag: true,
            threshold: 20,
            loop: true,
            rtl: false,
            onInit: () => {},
            onChange: () => {},
        });
        prev = () => {
            slider.prev()
            if (select > 0) {
                select--
            }
        }

        next = () => {
            slider.next()
            if (select >= 0) {
                select++;
            }
        }
        setInterval(()=>slider.next(), 3000);
    })
</script>

<div class="notification">
    <div class="siema notification-item">
        <div>
            <a href="https://m.booking.naver.com/booking/13/bizes/369432?theme=place&entry=pll&area=pll" aria-label="예약하기">
                <span uk-icon="icon: clock"></span>
                <span> 평일 AM 10~PM 8</span>
            </a>
        </div>
        <div>
            <a href="https://m.booking.naver.com/booking/13/bizes/369432?theme=place&entry=pll&area=pll" aria-label="예약하기">
                <span uk-icon="icon: clock"></span>
                <span> 토 AM 10~PM 2</span>
            </a>
        </div>
        <div>
            <a href="tel:0507-1352-5175" aria-label="전화 걸기">
                <span uk-icon="icon: receiver"></span>
                <span> 0507-1352-5175</span>
            </a>
        </div>
        <div>
            <a href="https://naver.me/Gd1h6pUp" aria-label="네이버 지도 바로가기">
                <span uk-icon="icon: location"></span>
                <span> 수원시청역 7번 출구 8m</span>
            </a>
        </div>
    </div>

    <button on:click={prev} class="notification-item" aria-label="notification-prev">
<!--        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512">&lt;!&ndash;! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. &ndash;&gt;<path d="M380.6 81.7c7.9 15.8 1.5 35-14.3 42.9L103.6 256 366.3 387.4c15.8 7.9 22.2 27.1 14.3 42.9s-27.1 22.2-42.9 14.3l-320-160C6.8 279.2 0 268.1 0 256s6.8-23.2 17.7-28.6l320-160c15.8-7.9 35-1.5 42.9 14.3z"/></svg>-->
        <span uk-icon="icon: chevron-left"></span>
    </button>

    <button on:click={next} class="notification-item" aria-label="notification-next">
<!--        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512">&lt;!&ndash;! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. &ndash;&gt;<path d="M3.4 81.7c-7.9 15.8-1.5 35 14.3 42.9L280.5 256 17.7 387.4C1.9 395.3-4.5 414.5 3.4 430.3s27.1 22.2 42.9 14.3l320-160c10.8-5.4 17.7-16.5 17.7-28.6s-6.8-23.2-17.7-28.6l-320-160c-15.8-7.9-35-1.5-42.9 14.3z"/></svg>-->
        <span uk-icon="icon: chevron-right"></span>
    </button>

</div>

<hr>

<!--<div>[평일] 오전 10시 ~ 오후 8시까지(점심시간 1시반 ~ 2시반)</div>-->
<!--<div>[토] 오전 10시 ~ 오후 2까지(점심시간 없이 진료)</div>-->
<!--<div><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512">&lt;!&ndash;! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. &ndash;&gt;<path d="M164.9 24.6c-7.7-18.6-28-28.5-47.4-23.2l-88 24C12.1 30.2 0 46 0 64C0 311.4 200.6 512 448 512c18 0 33.8-12.1 38.6-29.5l24-88c5.3-19.4-4.6-39.7-23.2-47.4l-96-40c-16.3-6.8-35.2-2.1-46.3 11.6L304.7 368C234.3 334.7 177.3 277.7 144 207.3L193.3 167c13.7-11.2 18.4-30 11.6-46.3l-40-96z"/></svg> <a href="tel:0507-1352-5175">0507-1352-5175</a></div>-->
<!--<div> <a type="button" href="https://naver.me/Gd1h6pUp"><svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 384 512">&lt;!&ndash;! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. &ndash;&gt;<path d="M215.7 499.2C267 435 384 279.4 384 192C384 86 298 0 192 0S0 86 0 192c0 87.4 117 243 168.3 307.2c12.3 15.3 35.1 15.3 47.4 0zM192 128a64 64 0 1 1 0 128 64 64 0 1 1 0-128z"/></svg></a> 수원시청역 7번 출구</div>-->
<!--<hr>-->

<style>
    .notification {
        display: flex;
        margin: 0 10px;
    }
    div.notification-item {
        padding: 5px 10px;
        text-align: center;
        width:100%;
        transform:translateX(-12px);
    }
    button.notification-item {
        border:none;
        background: none;
    }
    .notification-item:nth-child(1) {order: 2;}
    .notification-item:nth-child(2) {order: 1;}
    .notification-item:nth-child(3) {order: 3}
    hr {
        border: 1px solid #eee;
        margin: 0px;
    }
</style>
