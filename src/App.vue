<template>
  <div class="container">
      <div class="cart">
          <h3>Sepet</h3>
            <ul>
                <li v-for="item in cartItems" :key="item.id"> {{ item.title }} </li>
            </ul>
            <p v-if="cartItems.length == 0">Sepetiniz boş! Alışverişe hemen Necati mağazları farkıyla başlayabilirsiniz...</p>
      </div>

      <Product @addtocart="cartItems.push($event)" :product="product" v-for="product in productList" :key="product.id" />
      <!-- :product="product" kısmındaki ":product" kısmına da ne yazdığının önemi yok, değer orası
      -->

  </div>
</template>

<!-- Template tek element içermek zorunda -->

<script>
import Product from "@/components/Product.vue"
export default {
    components : {
        Product : Product
    },

    data(){
        return {
            productList : [
                    {
                        id : 1,
                        title : "Macbook Pro",
                        price : 100,
                        count : 10,
                        description : "Necati Mağazaları Gururla Sunmaz."
                    },
                    {
                        id : 2,
                        title : "iMac",
                        price : 500,
                        count : 5,
                        description : "Necati Mağazaları Gururla Sunmaz."
                    },
                    {
                        id : 3,
                        title : "Klavye",
                        price : 10,
                        count : 1000,
                        description : "Necati Mağazaları Gururla Sunmaz."
                    },
                    {
                        id : 4,
                        title : "iPhone",
                        price : 50,
                        count : 0,
                        description : "Necati Mağazaları Gururla Sunmaz."
                    }
                ],

            cartItems : []
            
        }

    }

}
/* DATANIN TEK KOMPONENTLİ HALİ BU, ESKİSİ GİBİ YAPARSAN ÇALIŞMAZ DATA Bİ FUNCTION OLMAK ZORUNDA */
</script>

<style>

.container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.cart {
    margin-bottom: 50px;
}
</style>
