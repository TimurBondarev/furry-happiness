<template>
    <li v-on:click="$emit('removeProduct', product.id)">
        <div class="img-product"><img :src="product.img" /></div>
        <div class="delete-product-icon"><img :src="require('../assets/deleteBut.svg')" /></div>
        <div class="inf-product">
            <span class="name-product">{{product.name}}</span>
            <span class="title-product">{{product.title}}</span>
            <span class="price-product">{{product.price}} руб.</span>
        </div>
    </li>
</template>

<script>
    export default {
        props: {
            product: {
                type: Object,
                required: true
            }
        }
    }
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
$font: 'Source Sans Pro', sans-serif;
    .main{
        font-family: $font;
        letter-spacing: -0.02em;
    }
    li{
        width: 322px;
        height: 423px;
        list-style: none;
        float: left;
        margin: 8px;
        position: relative;
        background: #FFFEFB;
        box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        transition: all 0.3s ease;
        &:hover>.delete-product-icon{
            display: block;
        }
        &:hover{
            transform: scale(1.01);
            z-index: 2;
        }
        &:active>.delete-product-icon{
            background-color: #FF0000;
        }
    }
    .delete-product-icon{
        display: none;
        position: absolute;
        top: 0%;
        left: 100%;
        width: 32px;
        height: 32px;
        background: #FF8484;
        box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
        border-radius: 10px;
        transform: translate(-50%, -50%);
        border: 0px;
        transition: all 0.3s ease;
        img{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    }
    .inf-product{
        padding: 16px 16px 16px 24px;
    }
    span{
        float: left;
        text-align: left;
        @extend .main;
    }
    .name-product{
        font-size: 20px;
        font-weight: 600;
        line-height: 25px;
        margin: 16px 0px;
    }
    .img-product{
        width: 100%;
        min-height: 200px;
        img{
            width: 100%;
            height: 100%;
        }
    }
    .title-product{
        line-height: 20px;
        font-size: 16px;
        font-weight: 400;
        margin-bottom: 32px;
    }
    .price-product{
        line-height: 30px;
        font-size: 24px;
        font-weight: 600;
    }
</style>