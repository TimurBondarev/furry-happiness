<template>
    <ul>
        <ProductItem 
            v-for="product of products"
            v-bind:product="product"
            v-on:removeProduct="removeProduct"
        />
    </ul>
</template>
<script>
import ProductItem from '@/components/ProductItem.vue'
export default {
    props: ['products'],
    components: {
        ProductItem
    },
    methods: {
        removeProduct(id){
            this.$emit('removeProduct', id)
        }
    }
}
</script>

<style lang="scss" scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>