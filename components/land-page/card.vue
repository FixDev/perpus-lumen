<template>
    <div>
        <v-container fluid>
            <v-row
            style="padding: 4px 10px;"
            align="center"
            justify="justify">
                <v-card
                    class="mx-auto"
                    max-width="300px"
                >
                    <v-img
                    class="white--text align-end"
                    height="200px"
                    src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                    >
                    <v-card-title>{{ judul }}</v-card-title>
                    </v-img>

                    <v-card-subtitle class="pb-0">{{ penulis }}</v-card-subtitle>

                    <v-card-text class="text--primary">
                    <div>{{ deskripsi }}</div>
                    </v-card-text>

                    <v-card-actions>
                    <v-btn
                        color="info"
                    >
                        Details
                    </v-btn>

                    <v-btn
                        color="orange"
                        text
                    >
                        Lainnya
                    </v-btn>
                    </v-card-actions>
                </v-card>
            </v-row>
        </v-container>
    </div>
</template>

<script>
  export default {
    data: () => ({
      show: false,
    }),

    props:{
        id:{
            type: String,
            default: ''
        },

        judul:{
            type: String,
            default: ''
        },

        deskripsi:{
            type: String,
            default: ''
        },

        penulis:{
            type: String,
            default: ''
        },

        gambar:{
            type: String,
            default: ''
        },

        created_at:{
            type: Date,
            default: ''
        },

        updated_at:{
            type: Date,
            default: ''
        }
    }
  }
</script>