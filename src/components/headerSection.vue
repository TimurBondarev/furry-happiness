<template>
    <div>
        <h1>Добавление товара</h1>
        <select name="select">
            <option  value="s1">По наименованию</option>
            <option value="s1">По цене min</option> 
            <option value="s1">По цене max</option>
        </select>
    </div>
</template>
<script>

</script>

<style scoped>
    div{
        display: block;
        height: 83px;
        padding: 32px;
        min-width: 100%;
    }
    h1{
        height: 35px;
        font-weight: 600;
        font-size: 28px;
        line-height: 35px;
        color: #3F3F3F;
        float: left;
    }
    select{
        min-width: 121.49px;
        min-height: 36px;
        border-radius: 4px;
        background: #FFFEFB;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border: 0px;
        color: #B4B4B4;
        float: right;
        margin: 20px 0px;
        text-align: center;
        padding: 10px;
    }
    @media (max-width: 426px) {
        div{
            padding: 0px;
            width: 100%;
        }
        h1{
            height: 35px;
            font-weight: 600;
            font-size: 28px;
            line-height: 35px;
            clear: both;
            width: 100%;
            text-align: center;
        }
        select{
            min-height: 36px;
            margin: 20px 0px;
            padding: 0px;
            clear: both;
            width: 100%;
        }
    }
</style>