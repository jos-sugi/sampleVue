<template>
  <v-app>
    <v-main>
      <v-btn @click="sampleApi">一覧を取得</v-btn>
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      name: "aaa",
      commnet: "bbb",
    };
  },
  methods: {
    sampleApi() {
      axios
        .post(
          "https://firestore.googleapis.com/v1/projects/vuejs-sample-ff968/databases/(default)/documents/cities/LA",
          {
            fields: {
              name: {
                // stringValue: this.name,
                stringValue: "aaa",
              },
              commnent: {
                // stringValue: this.comment,
                stringValue: "bbb",
              },
            },
          }
        )
        .then((response) => {
          console.log(response);
        });
    },
  },
};
</script>
