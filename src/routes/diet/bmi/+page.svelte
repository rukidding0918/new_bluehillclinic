<script>
    import source from './bmi.md?raw'
    import SvelteMarkdown from "svelte-markdown";
    import {onMount} from "svelte";
    let height
    let weight
    let inputHeight
    let inputWeight
    const resetResults = () => {
        let results = document.querySelectorAll('.result');
        results.forEach(result => {
            result.innerHTML = '';
        })

        inputHeight.value = ''
        inputWeight.value = ''
        inputHeight.focus()
    }
    const calc = () => {
        const bmi = weight / ((height / 100) * (height / 100));
        const bmiFloor = bmi.toFixed(1);
        resetResults();
        if (bmi >= bmi_base_line.over3) {
            document.querySelector('#over3').innerHTML = bmiFloor;
        }
        else if (bmi >= bmi_base_line.over2) {
            document.querySelector('#over2').innerHTML = bmiFloor;
        }
        else if (bmi >= bmi_base_line.over1) {
            document.querySelector('#over1').innerHTML = bmiFloor;
        }
        else if (bmi >= bmi_base_line.over) {
            document.querySelector('#over').innerHTML = bmiFloor;
        }
        else if (bmi >= bmi_base_line.normal) {
            document.querySelector('#normal').innerHTML = bmiFloor;
        }
        else {
            document.querySelector('#under').innerHTML = bmiFloor;
        }
    }
    const onInput = (event) => {
        if (event.key === 'Enter') {
            event.preventDefault();
            calc();
        }
    }
    const bmi_base_line = {
        under: 0,
        normal: 18.5,
        over: 23,
        over1: 25,
        over2: 30,
        over3: 35
    }
    onMount(()=>inputHeight.focus())
</script>

<SvelteMarkdown {source} />

<table id="result-table" class="uk-table uk-table-small uk-table-divider uk-table-hover uk-text-small">

    <thead>
        <tr>
            <th>분류</th>
            <th>체질량지수<br>(kg/m²)</th>
            <th>결과</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>저체중</td>
            <td>18.5 미만</td>
            <td id="under" class="result"></td>
        </tr>
        <tr>
            <td>정상</td>
            <td>18.5 ~ 22.9</td>
            <td id="normal" class="result"></td>
        </tr>
        <tr>
            <td>비만전단계</td>
            <td>23 ~ 24.9</td>
            <td id="over" class="result"></td>
        </tr>
        <tr>
            <td>1단계 비만</td>
            <td>25 ~ 29.9</td>
            <td id="over1" class="result"></td>
        </tr>
        <tr>
            <td>2단계 비만</td>
            <td>30 ~ 34.9</td>
            <td id="over2" class="result"></td>
        </tr>
        <tr>
            <td>3단계 비만</td>
            <td>35 이상</td>
            <td id="over3" class="result"></td>
        </tr>
    </tbody>
</table>

<form on:submit|preventDefault={calc}>

    <fieldset class="uk-fieldset">
        <div class="uk-margin-small uk-flex uk-flex-middle">
            <input id="height" type="number" placeholder="키(cm)" bind:this={inputHeight} bind:value={height} class="uk-input">
        </div>
        <div class="uk-margin-small uk-flex uk-flex-middle">
            <input id="weight" type="number" placeholder="몸무게(kg)" bind:this={inputWeight} bind:value={weight} on:keydown={onInput} class="uk-input">
        </div>
        <button type="submit" class="uk-button uk-button-primary uk-width-1-1" href="#result-table">결과보기</button>
    </fieldset>
</form>

<style>
    #under {
        color: blue;
    }
    #normal {
        color: green;
    }
    #over {
        color: greenyellow;
    }
    #over1 {
        color: orange;
    }
    #over2 {
        color: coral;
    }
    #over3 {
        color: red;
    }
    th:nth-child(2) {
        text-align: right;
    }
    th:nth-child(3) {
        text-align: right;
    }
    td:nth-child(2) {
        text-align: right;
    }
    td:nth-child(3) {
        text-align: right;
    }
    .result {
        font-weight: bold;
    }
</style>