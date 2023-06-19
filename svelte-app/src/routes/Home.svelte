<script>
    // 외부 컴포넌트 불러오기
    import Nested from "../components/Nested.svelte";

    let text = "World!";

    let htmlName = "<span style='color:red;'>World2</span>";

    let imgSrc = "https://w.namu.la/s/a636b3150457472abd5f85746ae2f3af19f80c4579016079c2e8c99f9920b8d829ded36fbdf22e63c17d4b34952da1b3db6c8760d712d34647ebb18d41728fc9efc318b96bd7e27e004e0e6a9367add176de44eca0ff2abd3de575e347fb88de45a74e4b6a74dd71ac10409f638342f8";
    let src = "https://ojsfile.ohmynews.com/BIG_IMG_FILE/2022/1008/IE003061575_BIG.jpg";

    // 카운트 함수
    let count = 0;
    const clickCount = ()=>{
        count = count + 1;
    }

    // watch or computed 같은 역할
    $: double = count * 2;  // count 변수가 바뀔때마다 자동으로 갱신(let 선언시 반영되지않음)

    // 다중 데이터 화면 구성 관련
    let arrData = [
        {title:"제목1", contents:"내용1"},
        {title:"제목2", contents:"내용2"},
        {title:"제목3", contents:"내용3"},
    ]
</script>

<h1>Hello {text}</h1>

{@html htmlName}

<img src="{imgSrc}" alt="" style="width:200px;">
<img {src} alt="" style="width:200px;">

{#if count<3}
    <div>Click Count : {count}</div>
{:else}
    <div>Click Count2 : {count}</div>
{/if}

<div>double : {double}</div>
<button type="button" on:click="{clickCount}">Count</button>

<table>
    {#each arrData as {title, contents}, i}
    <tr>
        <th>{title}</th>
        <td>{contents}</td>
    </tr>
    {/each}
</table>

<Nested {text} />

<style>
	h1 {color:blue;}
</style>