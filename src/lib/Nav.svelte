<script>
    import Logo from '$lib/Logo.svelte'
    import { base } from '$app/paths'
    let size = 24;
    const closeNav = ()=>{UIkit.offcanvas('#offcanvas-slide').hide();}
</script>

<a href="#offcanvas-slide" class="uk-button uk-button-text menu-button" uk-toggle aria-label="menu">
    <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 448 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
</a>

<div id="offcanvas-slide" uk-offcanvas="overlay:true;">
    <div class="uk-offcanvas-bar">
        <button class="uk-offcanvas-close" type="button" uk-close></button>
        <ul class="uk-nav uk-nav-default">
            <div class="nav-title">
                <Logo {size} />
                <h4>청구경희한의원</h4>
            </div>
            <hr class="uk-divider">

            <details open>
                <summary>
                    <span class="nav-header">청구경희한의원</span>
                </summary>
                <ul class="uk-list">
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/intro">인사말</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/doctors">의료진</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/office">한의원 둘러보기</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/opening">진료시간 및 예약</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/location">오시는 길 및 주차 안내</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/costs">비급여 안내</a></li>
                    <li><a on:click={closeNav} href="{base}/bluehillclinic/telecare">비대면 진료 및 처방 안내</a></li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">통증 클리닉</span>
                </summary>
                <ul class="uk-list">
                    <li>통증</li>
                    <li>근육통 관절염</li>
                    <li>척추질환</li>
                    <li>턱관절질환</li>
                    <li>발목손목 염좌</li>
                    <li>테니스엘보 골프엘보</li>
                    <li>족저근막염</li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">교통사고 클리닉</span>
                </summary>
                <ul class="uk-list">
                    <li>교통사고</li>
                    <li>어혈제거 한약</li>
                    <li>한의물리치료</li>
                    <li>추나요법</li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">보양 클리닉</span>
                </summary>
                <ul class="uk-list">
                    <li>청정한약</li>
                    <li>공진단</li>
                    <li>경옥고</li>
                    <li>산후보약</li>
                    <li>러시아 녹용</li>
                    <li>면역력 강화</li>
                    <li>남성보약</li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">다이어트 클리닉</span>
                </summary>
                <ul class="uk-list">
                    <li><a on:click={closeNav} href="{base}/diet/bmi">비만 계산기</a></li>
                    <li>라인탕 다이어트</li>
                    <li>플러스마이너스정</li>
                    <li>나의 기록</li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">청경 클리닉</span>
                </summary>
                <ul class="uk-list">
                    <li>추나요법</li>
                    <li>다이어트</li>
                    <li>안면마비 구안와사</li>
                    <li>담적</li>
                    <li>숙취해소</li>
                    <li>후유증 장애</li>
                </ul>
            </details>

            <details>
                <summary>
                    <span class="nav-header">커뮤니티</span>
                </summary>
                <ul class="uk-list">
                    <li>공지사항</li>
                    <li>치료후기</li>
                    <li>건강칼럼</li>
                    <li>자주하는 질문</li>
                    <li>한의원정보</li>
                </ul>
            </details>
        </ul>
    </div>
</div>

<style>
    .menu-button {
        margin: auto 0 auto auto;
        height: 44;
        line-height: 12px;
    }
    .uk-button-text {
        margin: auto 15px auto auto;
        height: 44;
    }
    .uk-offcanvas-bar {
        background: #fff;
        color: #292929;
    }
    .uk-offcanvas-close {
        margin-top: 15px;
        margin-right: 15px;
        color: var(--primary-color);
    }
    .nav-title {
        display: flex;

    }
    .nav-title h4 {
        color: var(--primary-color);
        font-weight: bold;
        margin: 0;
        padding-left: 15px;
    }
    .nav-header {
        color: var(--primary-color);
        font-size: 1rem;
    }
    details {
        margin-bottom: 10px;
    }
    .uk-list {
        margin-left: 15px;
        margin-top: 10px;
    }
    .uk-list li {
        margin-top: 8px;
    }
    .uk-list li a {
        color: var(--primary-color);
    }
</style>