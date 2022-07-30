<template>
    <form @submit.prevent="onSubmit">
        <label for="new-product-name">Наименование товара<img :src="require('../assets/redBall.svg')" /></label>
        <input id="new-product-name" type="text" name="name" required placeholder="Введите наименование товара" v-model="name">
        <label for="new-product-title">Описание товара<img :src="require('../assets/redBall.svg')" /></label>
        <textarea id="new-product-title" name="name" required placeholder="Введите описание товара" v-model="title"></textarea>
        <label for="new-product-url">Ссылка на изображение товара<img :src="require('../assets/redBall.svg')" /></label>
        <input id="new-product-url" type="text" name="name" required placeholder="Введите ссылку" v-model="img">
        <label for="new-product-price">Цена товара<img :src="require('../assets/redBall.svg')" /></label>
        <input v-maska="'# ### ### ###'" id="new-product-price" type="text" step="1" min="1" name="name" required placeholder="Введите цену" v-model="price">
        <button>Добавить товар</button>
    </form>
</template>


<script>
import { maska } from 'maska'
export default{
    directives: { maska },
    data(){
        return{
            name: '',
            title: '',
            img: '',
            price: ''
        }
    },
    methods:{
        onSubmit(){
            if(this.name.trim() && this.title.trim() && this.img.trim() && this.price.trim()){
                const newProduct = {
                    id: Date.now(),
                    name: this.name,
                    title: this.title,
                    img: this.img,
                    price: this.price,
                    completed: false
                }
                this.$emit('addProduct', newProduct)
            }
        }
        
    }
}
</script>

<style scoped>
    form{
        width: 308px;
        height: 416px;
        border-radius: 4px;
        box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04), 0px 6px 10px rgba(0, 0, 0, 0.02);
        background: #FFFEFB;
        padding: 24px;
        margin-right: 40px;
    }
    label{
        font-weight: 400;
        font-size: 10px;
        line-height: 13px;
        letter-spacing: -0.02em;
        padding: 0px;
        margin-bottom: 4px;
        float: left;
    }
    label img{
        margin-bottom: 5px;;
    }
    input{
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        letter-spacing: -0.02em;
        width: 100%;
        height: 26px;
        border-radius: 4px;
        border: 0px;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        padding: 10px 16px;
        margin-bottom: 16px;
        text-overflow: ellipsis;
    }
    input:focus{
        outline: 0;
    }
    #new-product-title{
        width: 100%;
        height: 108px;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        letter-spacing: -0.02em;
        text-overflow: ellipsis;
        resize: none;
        padding: 10px 16px;
        border: 0px;
    }
    #new-product-title:focus{
        outline: 0;
    }
    button{
        font-weight: 600;
        font-size: 12px;
        line-height: 15px;
        letter-spacing: -0.02em;
        width: 284px;
        height: 36px;
        border-radius: 10px;
        border: 0px;
        color: #B4B4B4;
        transition: all 0.3s ease;
    }
    button:hover{
        background-color: rgb(31, 104, 214);
        color: #ffffff;
        cursor: pointer;
    }
    @media (max-width: 426px) {
        div{
            height: 145px;
        }
        form{
            width: 100%;
            height: 488px;
            padding: 0px;
            margin: 0px auto;
        }
        input{
            font-weight: 400;
            font-size: 12px;
            line-height: 15px;
            max-width: 377px;
            height: 26px;
            padding: 10px 16px;
            margin-bottom: 16px;
        }
        #new-product-title{
            max-width: 377px;
            height: 108px;
            border-radius: 4px;
            font-weight: 400;
            font-size: 12px;
            line-height: 15px;
            padding: 10px 16px;
        }
        button{
            font-weight: 600;
            font-size: 12px;
            line-height: 15px;
            width: 100%;
            height: 36px;
        }
    }
    @media (max-width: 376px) {
        form{
            height: 488px;
            padding: 0px;
            margin: 0px auto;
        }
        input{
            max-width: 327px;
            height: 26px;
            padding: 10px 16px;
            margin-bottom: 16px;
        }
        #new-product-title{
            max-width: 327px;
            height: 108px;
            padding: 10px 16px;
        }
        button{
            width: 100%;
            height: 36px;
        }
    }
</style>