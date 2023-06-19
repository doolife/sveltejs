<script>
    export let text, childrenName, handleValueAdd;     // 부모가 보낸 데이터 및 함수를 export 형태로 받아서 사용 가능

    import { createEventDispatcher } from "svelte";     // 이벤트 디스패처 가져오기
    const dispatch = createEventDispatcher();           // 디스패처 생성
    function sayHello() {
        dispatch('message', {                           // 첫번째 매개변수로는 이벤트 이름, 두번째로는 이벤트 핸들러에 전달할 인자(부모에게 보낸 이벤트 이름과 부모의 함수를 연결하여 사용)
            text1: 'Hello!',                            // 이벤트 발생시 event.detail 프로퍼티에서 디스패치 함수의 두번째 매개변수로 지정한 데이터 값을 확인
            text2: 'World!'
        });
    }
</script>

<p>외부 컴포넌트 : {text}</p>
<button on:click={(event) => handleValueAdd(event, 10)} >Add 10</button>
<button on:click={sayHello}>자식 버튼 이벤트</button>
<button 
    type="button"
    on:click={() => { 
        childrenName = "lee eun seok";      // 부모 변수에 데이터 전달
    }}
>자식 버튼 이벤트 2</button>