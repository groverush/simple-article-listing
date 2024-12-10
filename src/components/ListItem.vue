<script setup lang="ts">
import { ref, onMounted } from 'vue'
import img1 from '../assets/photo_1@2x.png'
import img2 from '../assets/photo_2@2x.png'
import img3 from '../assets/photo_3@2x.png'
import phoneImg1 from '../assets/photo_1.png'
import phoneImg2 from '../assets/photo_2.png'
import phoneImg3 from '../assets/photo_3.png'

let articleId = 0
const articles = ref([
  {
    articleId: articleId++,
    img: img1,
    phoneImg: phoneImg1,
    description: 'Unlocking the Power of Cloud Computing: A Guide to Scalable Solutions',
    date: 'November 12, 2024',
  },
  {
    articleId: articleId++,
    img: img2,
    phoneImg: phoneImg2,
    description:
      'The Impact of 5G on Business: How Faster Networks are Transforming the Way We Work',
    date: 'November 12, 2024',
  },
  {
    articleId: articleId++,
    img: img3,
    phoneImg: phoneImg3,
    description: 'The Future of AI: How Machine Learning is Revolutionizing Industries',
    date: 'November 12, 2024',
  },
])
onMounted(() => {
  console.log(articles.value)
})
</script>

<template>
  <div class="container">
    <ul>
      <li class="list-item" v-for="article in articles" :key="article.articleId">
        <img :src="article.img" alt="some image" />
        <div class="desc">
          <p>{{ article.description }}</p>
          <span>{{ article.date }}</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.container,
ul,
.list-item {
  width: 100%;
}

ul {
  display: flex;
  flex-direction: column;
  gap: 2em;
}
.list-item {
  list-style: none;
  display: flex;

  justify-content: space-evenly;
}
.list-item img {
  border-radius: 8px;
  width: 150px;
  height: 140px;
  object-fit: cover;
}
.desc {
  font-size: 1rem;
  display: flex;
  flex-direction: column;
  width: 57%;
}
.desc span {
  font-size: 0.875rem;
  color: #4d5562;
  font-weight: 400;
}

@media (max-width: 1024px) {
  .list-item {
    justify-content: left;
    gap: 1.625em;
  }
  .list-item img {
    width: 120px;
    height: 110px;
  }
  .desc {
    font-size: 0.825rem;
    width: 60%;
  }
  .desc span {
    font-size: 0.625rem;
  }
}
</style>
