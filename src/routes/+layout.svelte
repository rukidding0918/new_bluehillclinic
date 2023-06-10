<script>
    import { Seo, SvelteUIProvider  } from '@svelteuidev/core';
</script>

<svelte:head>
    <script type="application/ld+json">
        {
            "@context": "https://schema.org",
            "@type": "Hospital",
            "image": [
                "https://hani.one/photos/1x1/photo.jpg",
                "https://hani.one/photos/4x3/photo.jpg",
                "https://hani.one/photos/16x9/photo.jpg"
            ],
            "name": "청구경희한의원",
            "address": {
                "@type": "PostalAddress",
                "postalCode": "16490",
                "addressRegion": "경기",
                "addressLocality": "수원시 팔달구",
                "streetAddress": "효원로 269 에스팝타워 214호"
            },
            "openingHours": ["Mo-Fr 10:00-20:00", "Sa 10:00-14:00"],
            "geo": {
                "@type": "GeoCoordinates",
                "latitude": 127.0312243,
                "longitude": 37.2622655
            },
            "areaServed": "경기도 수원시, 인계동 수원시청역 인근, 화성, 동탄, 오산, 안산, 안양, 인천, 분당, 용인, 죽전 등",
            "url": "https://map.naver.com/v5/entry/place/1283292950",
            "telephone": "0507-1352-5175",
            "keyword": "인계동 한의원, 수원시청역 한의원",
            "description": "추나요법은 청구경희한의원, 평일 매일 8시까지, 교정, 턱관절, 교통사고 등 추나요법으로 통증잡는 청구경희한의원입니다.",
            "acceptsReservations": "True"
        }
    </script>
</svelte:head>

<Seo
    title="수원한의원"
    titleTemplate="%t% | 인계동 청구경희한의원"
    description="추나요법은 청구경희한의원, 평일 매일 8시까지, 교정, 턱관절, 교통사고 등 추나요법으로 통증잡는 청구경희한의원입니다."
/>

<SvelteUIProvider>
    <slot />
</SvelteUIProvider>