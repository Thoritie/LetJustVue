<template>
  <div class="container">
      <div class="columns">
        <div class="column is-4 is-offset-4">
            <h3 class="title is-3">แจกวาร์ป</h3>
            <div class="field">
              <div class="control">
                  <input class="input is-primary is-rounded is-large" type="text" placeholder="Title"  v-model="wrap.title">
              </div>
            </div>
            <div class="field">
              <div class="control">
                  <input class="input is-primary is-rounded is-large" type="text" placeholder="image" v-model="wrap.image">
              </div>
            </div>
            <div class="field">
              <div class="control">
                  <input class="input is-primary is-rounded is-large" type="text" placeholder="Success input" v-model="wrap.desc">
              </div>
            </div>
          <a class="button is-primary is-rounded is-large is-focused" @click="onclick">Rounded</a>

        </div>
      </div>


      <template  v-for="wrap in wraps">
        <div :key="wrap.id">
        <div class="card">
            <div class="card-content">
              <div class="media">
                <div class="media-right">
                  <figure class="image is-128x128">
                     <img :src="wrap.title" alt="">
                  </figure>
                </div>
                <div class="media-content">
                  <p class="title is-4">{{ wrap.title}}</p>
                  <img :src="wrap.image" alt="">
                  <p class="subtitle is-6">{{ wrap.desc}}</p>
                </div>
              </div>
              <div class="content">
               
              </div>
            </div>
          </div>
          </div>
      </template>


  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      wrap: {
        title: "",
        desc: "",
        image: ""
      },
      wraps: []
    };
  },
  methods: {
    onclick() 
    {
      this.wraps.push(this.wrap)
    }
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>