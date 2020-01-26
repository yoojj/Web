# dialog
: 팝업, 모달, 오버레이 등 대화 상자 기능을 제공하는 엘리먼트



```html
<dialog open>
    <h1>팝업</h1>
</dialog>
<!-- open 속성 사용 -->



<dialog>
    <h1>팝업</h1>
</dialog>

<script>
(function(){
    const dialog = document.getElementById('dialog');
    dialog.show();
})();
</script>
<!-- JS 제어 -->



<dialog>
    <h1>팝업</h1>
    <button id="close">닫기</button>
</dialog>

<style>
dialog::backdrop {background-color:black;}
</style>

<script>
(function(){
    const dialog = document.getElementById('dialog');
    const close = document.getElementById('close');

    dialog.showModal();

    close.addEventListener('click', function (e) {
        e.preventDefault();
        dialog.close();
    });

})();
</script>
```



[top](#)
