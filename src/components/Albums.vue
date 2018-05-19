<template>
  <div class="columns">
      <div class="column is-4 is-offset-4">
       
        <button class="button is-primary is-rounded is-large is-focused" @click="fetch">Check Albums</button>
        
       
            <table style="width:100%" class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">
                 <template v-for="album in albums">
                    <div :key="album.id">
                        <tr>
                        <td><h2 class="title is-2">{{ album.userId}}</h2></td>
                        <td><h2 class="title is-2">{{ album.id}}</h2></td>
                        <td><h2 class="title is-2">{{ album.title}}</h2></td>
                        </tr>
                    </div>
                </template>
            </table>

      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    data () {
        return {
            album: {
                userId: "",
                id: "",
                title: ""
            },
        albums: []
        }
    },
    methods : {
        async fetch () {
            let {data} = await axios.get('https://jsonplaceholder.typicode.com/albums')
            this.ans = data

        }
    }
}
</script>
