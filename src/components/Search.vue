<template>
  <v-container>
    <v-row>
      <v-col>
        <v-text-field label="Search" v-model="word"></v-text-field>
      </v-col>
      <v-col>
        <v-btn class="mx-2" fab dark color="blue lighten-34" @click = "searchItem">
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
import axios from 'axios';
export default {
  name: "Search",
  word: '',
  data() {
    return {
      search: [],
      word: '',
    };
  },
  methods: {
    searchItem() {
      axios
        .get("https://pixabay.com/api/?key=18325849-94cafec8b0f30985ae8cfbdde&q="+this.word+"&image_type=photo")
        .then((response) => {
         this.search = response.data;
         this.$emit("searchresult", response.data);
        })
    },
  },
};
</script>