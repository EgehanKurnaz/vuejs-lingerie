<template>
    <div class="product">
        <strong>{{ product.title }}</strong>
        <p> {{product.description }} </p>
        <strong> Fiyat : {{ product.price }} | Adet : {{ product.count }} </strong>
        <br><br>
        <button @click="addtocart(product)"> Sepete Ekle </button>
    </div>
</template>

<script>
export default {
    props: ["product"],
    /* data() {
        return {
            product {

            }
        }
    }  Bu propsun uzun hali, ikisi aynı cacık. Üstteki div kısmını app.vue içindeki DEĞİŞKENLER İLE
    kullanmak istediğimiz için yapıyoruz. Elle yazmamak için. app.vue'ye bak, data kısmındaki
    productList'in içindeki bilgileri buraya çağırmak için kullanıyoruz. */
    
    methods: {
        addtocart(product) {
            this.$emit("addtocart", product)
        }
    },
}
</script>

<style>
    .product {
        border: 2px dashed #666;
        padding: 5px 10px;
        width: 300px;
        margin-bottom: 5px;
    }

    .product:hover {
        border: 2px solid #666;
    }

    .product:first-child {
        margin-top: 20px;
    }
</style>