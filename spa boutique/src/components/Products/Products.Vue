<script setup>
import './products.scss'
</script>

<template>
    <div class="products">
        <div class="products__container container">
            <img class="products__line line" src="@/assets/img/line.svg" alt="line" />
            <h2 class="products__title">Products</h2>
            <div class="products__select">
              <button class="products__button">All</button>
              <button class="products__button">Men's clothing</button>
              <button class="products__button">Women's clothing</button>
              <button class="products__button">Jewelery</button>
              <button class="products__button">Electronics</button>
            </div>
            <div class="products__card-block">
                <div class="products__card" v-for="p in post" :key="p.id">
                    <p class="products__card-category">{{ p.category }}</p>
                    <img class="products__card-img" :src="p.image" />
                    <!-- <p class="products__card-img">{{ p.image }}</p> -->
                    <div class="products__card-name">
                        <h2 class="products__card-title">{{ p.title }}</h2>
                        <p class="products__card-price">{{ p.price }}$</p>
                    </div>
                    <div class="products__card-description-box">
                      <button @click="toggleElement" class="products__card-button">Read more</button>
                      <p 
                      class="products__card-description"
                      v-if="isElVisible"
                      >{{ p.description }}</p>
                    </div>
                    
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  data() {
    return {
      post: [],
      isElVisible: false
    }
  },
  methods: {
    getPosts() {
      fetch('https://fakestoreapi.com/products')
        .then(response => response.json())
        .then(data => this.post = data)
    }, 
    toggleElement() {
      this.isElVisible = !this.isElVisible
    }
  },
  mounted() {
    this.getPosts()
  }
}
</script>
