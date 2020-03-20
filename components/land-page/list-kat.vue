<template>
  <div>
      <v-row style="padding: 8px 16px;">
        <v-btn color="info" text outlined>
        {{ nama }}
        </v-btn>
      </v-row>

  </div>
</template>

<script>
  export default {
    props:{
        id:{
            type: String,
            default: ''
        },
        nama:{
            type: String,
            default: ''
        }
    }
  }
</script>

<style>

</style>