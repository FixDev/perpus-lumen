<template>
  <v-card>
    <v-card-title>
      <v-text-field
        v-model="search"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="items"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      search: "",
      headers: [
        {
          text: "Judul", value: "judul"
        },
        { text: "Deskripsi", value: "deskripsi" },
        { text: "Penulis", value: "penulis" },
        { text: "Kategori", value: "kategori_id" }
      ],
      items: []
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      const res = await this.$axios.get("http://192.168.1.20:8000/api/buku");
      this.items = res.data;
    }
  }
};
</script>

<style></style>
