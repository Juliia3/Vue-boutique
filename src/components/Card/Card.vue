<script setup>
import './card.scss'
</script>

<template>
    <div class="card">
        <div class="card__container">
            <div class="card__block"
            v-if="post">
                <p class="card__category">{{ post.category }}</p>
                <img class="card__img" :src="post.image" />
                <div class="card__name">
                    <h2 class="card__title">{{ post.title }}</h2>
                    <p class="card__price">{{ post.price }}$</p>
                </div>
                <p class="card__description">{{ post.description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      post: null,
    }
  },
  methods: {
    getPost() {
      const url = 'https://fakestoreapi.com/products/' + this.$route.params.id
        fetch(url)
            .then(res=>res.json())
            .then(json=>this.post = json)
    }, 
  },
  mounted() {
    this.getPost()
  }
}
</script>