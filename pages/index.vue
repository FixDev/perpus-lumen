<template>
  <div>
    <Carousel />
    
    <v-row
    align="center"
    justify="center">
      <v-btn-toggle>
        <FilterKat v-for="kat in kategoris" :key="kat.id" :nama="kat.nama"></FilterKat>
      </v-btn-toggle>
    </v-row>

    <v-row
    align="center"
    justify="center">
      <Card
      v-for="buku in bukus.slice(0,3)"
      :key="buku.id"
      :id="buku.id"
      :judul="buku.judul"
      :penulis="buku.penulis"
      :deskripsi="buku.deskripsi"></Card>
    </v-row>
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
      kategoris: [],
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
      const res1 = await this.$axios.get('http://192.168.1.20:8000/api/buku');
      this.bukus = res1.data;

      const res2 = await this.$axios.get('http://192.168.1.20:8000/api/kategori');
      this.kategoris = res2.data;
    }
  }
}
</script>
