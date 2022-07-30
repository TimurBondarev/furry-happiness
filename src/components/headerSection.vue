<template>
    <div>
        <h1>Добавление товара</h1>
        <select name="select">
            <option  value="s1">По умолчанию</option>
            <option value="s1">По цене min</option> 
            <option value="s1">По цене max</option>
        </select>
    </div>
</template>
<script>

</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
$font: 'Source Sans Pro', sans-serif;
    .main{
        font-family: $font;
        text-align: center;
        height: 35px;
    }
    div{
        display: flex;
        height: 83px;
        padding: 32px;
        justify-content: space-between;
    }
    h1{
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        color: #3F3F3F;
        @extend .main;
    }
    select{
        width: 121.49px;
        border-radius: 4px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border: 0px;
        color: #B4B4B4;
        margin: 20px 0px;
        @extend .main;
    }
</style>