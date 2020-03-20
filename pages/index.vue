<template>
  <div>
    <Carousel />
    <FilterKat />
    <Card
    v-for="buku in bukus"
    :key="buku.id"
    :id="buku.id"
    :judul="buku.judul"
    :penulis="buku.penulis"
    :deskripsi="buku.deskripsi"></Card>
  </div>
</template>

<script>
import Carousel from '~/components/land-page/carousel.vue';
import FilterKat from '~/components/land-page/list-kat.vue';
import Card from '~/components/land-page/card.vue';

export default {
  data(){
    return{
      bukus: [],
    }
  },

  components: {
    Carousel,
    FilterKat,
    Card
  },

  mounted(){
    this.getData();
  },

  methods:{
    async getData(){
      const res = await this.$axios.get('http://192.168.1.20:8000/api/buku');
      this.bukus = res.data;
    }
  }
}
</script>
