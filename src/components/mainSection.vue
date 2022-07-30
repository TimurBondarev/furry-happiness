<template>
    <section>
        <div><addProductForm @addProduct="addProduct"/></div>
        <div><ProductList 
            v-bind:products="products"
            @removeProduct="removeProduct"/>
        </div>
    </section>
</template>
<script>
import addProductForm from '@/components/addProductForm.vue'
import ProductList from '@/components/ProductList.vue'
export default {
    props: ['products'],
    data() {
        return {
            products: [
                {id: 1, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 2, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 3, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 4, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 5, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 6, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 7, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false},
                {id: 8, img: require('../assets/productImg.jpg'), name: 'Наименование товара', title: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк', price: '10 000 ', competed: false}
            ]
        }
    },
    components: {
        addProductForm,
        ProductList
    },
    methods: {
        removeProduct(id) {
            this.products = this.products.filter(product => product.id !== id)
        },
        addProduct(product){
            this.products.push(product)
        }
    }
}
</script>

<style lang="scss" scoped>
    section{
        display: flex;
        margin: 0px;
        padding: 0px;
    }
    div{
        margin-bottom: 10px;
        padding: 0px;
    }
</style>