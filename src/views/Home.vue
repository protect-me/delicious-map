<template>
  <v-container>
    <v-card>
      <v-card-title>title</v-card-title>
      <v-card-text>
        <v-text-field label="instagram address"></v-text-field>
      </v-card-text>
      <v-card-actions>
        <v-btn @click="parsing">here</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
import axios from 'axios'

export default {
  methods: {
    async parsing() {
      const article = 'CQ047lWJ4Z8'
      const url = `https://www.instagram.com/p/${article}/`
      await axios
        .get(url)
        .then((res) => {
          console.log('성공')
        })
        .catch((err) => {
          console.log('실패')
        })
      console.log('here', url)
      // const url = await axios.get(URL)
      // https://solbel.tistory.com/781
      //         const url:
      //     'https://www.instagram.com/p/CQ047lWJ4Z8//?__a=1',
      //   success: function (data) {
      //     for (
      //       var ins = 0;
      //       ins < data.graphql.user.edge_owner_to_timeline_media.edges.length;
      //       ins++
      //     ) {
      //       console.log(data.graphql.user.edge_owner_to_timeline_media.edges[ins])
      //       console.log(
      //         data.graphql.user.edge_owner_to_timeline_media.edges[ins].node
      //           .edge_media_to_caption.edges[0].node.text,
      //       )
      //       $('#instar').append(
      //         "<img src='" +
      //           data.graphql.user.edge_owner_to_timeline_media.edges[ins].node
      //             .display_url +
      //           "'/>",
      //       )
      //     }
      //   },
      // })
      // }
    },
  },
}
</script>
