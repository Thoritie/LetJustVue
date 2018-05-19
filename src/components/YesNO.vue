<template>
  <div class="columns">
      <div class="column is-4 is-offset-4">
        <div class="field">
            <div class="control">
                <input class="input is-primary is-rounded is-large" type="text" placeholder="Question ?"  v-model="question">
            </div>
        </div>
        <button class="button is-primary is-rounded is-large is-focused" @click="fetch">Gentle press</button>
        
        <template v-if="ans">
            <h2 class="title is-2">{{ ans.answer}}</h2>
            <img :src="ans.image" alt="">
        </template>
        
      </div>
  </div>
</template>

<script>
import axios from 'axios'
import cors from 'cors'
export default {
    data () {
        return {
            question: '',
            ans : null
        }
    },
    methods : {
        async fetch () {
            let {data} = await axios.get('https://yesno.wtf/api')
            this.ans = data

        }
    }
}
</script>
