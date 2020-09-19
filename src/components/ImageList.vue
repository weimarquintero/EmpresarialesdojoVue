<template>
  <v-container>
    <v-row>
      <v-col v-bind:key="item.id" v-for="item in items.hits" sm="4" cols="12">
        <v-card class="ma-5" max-width="600">
          <img class="ma-2" :src="item.previewURL" alt />
          <v-card-title>Propiedad de {{item.user}}</v-card-title>
          <v-card-subtitle>Tags: {{item.tags}}</v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "ImageList",
  props: ["items"],
};
</script>