<!-- <script>
import CommentList from './components/CommentList.vue';

export default {
  name: 'App',
  components: {
    CommentList
  }
};
</script>

<template>
  <div id="app">
    <h1>Tambahkan Komentar</h1>
    <CommentList />
  </div>
</template>

<style>
#app {
  font-family: 'Arial', sans-serif;
  background-color: #f9f9f9;
  padding: 30px;
}

h1 {
  text-align: center;
  font-size: 24px;
  color: #333;
  margin-bottom: 20px;
}
</style> -->

<script>
export default {
  data() {
    return {
      isVisible: true,
      items: ['Item A', 'Item B', 'Item C'],
      imageSrc: './public/garuda.jpg',
      imageAlt: 'Gambar Placeholder',
      name: ''
    };
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    },
    changeImage() {
      this.imageSrc = './public/UntukWeb2.jpg';
      this.imageAlt = 'Gambar Baru';
    }
  }
};
</script>

<template>
  <div id="app">
    <!-- v-if -->
    <p v-if="isVisible">Teks ini hanya muncul jika `isVisible` bernilai true.</p>
    <button @click="toggleVisibility">Toggle Visibility</button>

    <!-- v-for -->
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ index + 1 }}. {{ item }}
      </li>
    </ul>

    <!-- v-bind -->
    <img :src="imageSrc" :alt="imageAlt" style="width: 150px; height: 150px;">
    <button @click="changeImage">Ganti Gambar</button>

    <!-- v-model -->
    <input v-model="name" placeholder="Masukkan nama">
    <p>Halo, {{ name }}!</p>
  </div>
</template>



<style>

</style>
