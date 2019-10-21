<template>
  <div>
    <div class="container">
      <div>
        <logo />
        
        <h1 class="title">
          NuxtSax
        </h1>
        <h2 class="subtitle">
          Nuxt.js + VueSax
        </h2>
        <vs-row vs-type="flex" vs-align="center" vs-justify="space-around">
          <vs-col vs-w="1"></vs-col>
          <vs-col vs-w="5">
            <vs-button color="primary" type="flat" size="large" icon="cast" @click="openLoading('https://nuxtjs.org/')">
              Nuxt.js Documentation
            </vs-button>
          </vs-col>
          <vs-col vs-w="5">
            <vs-button color="danger" type="gradient" size="large" icon="favorite" :icon-after="true" @click="openLoading('https://github.com/nuxt/nuxt.js')">
              Nuxt.js GitHub
            </vs-button>
          </vs-col>
          <vs-col vs-w="1"></vs-col>
        </vs-row>
        <vs-row vs-type="flex" vs-align="center" vs-justify="space-around">
          <vs-col vs-w="1"></vs-col>
          <vs-col vs-w="5">
            <vs-button color="success" type="filled" size="large" icon="emoji_emotions" @click="openLoading('https://lusaxweb.github.io/vuesax/development/#quick-start-cdn')">
              VueSax Documentation
            </vs-button>
          </vs-col>
          <vs-col vs-w="5">
            <vs-button color="warning" type="border" size="large" icon="adb" :icon-after="true" @click="openLoading('https://github.com/lusaxweb/vuesax')">
              VueSax GitHub
            </vs-button>
          </vs-col>
          <vs-col vs-w="1"></vs-col>
        </vs-row>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  data:()=>({
    activeItem: 0,
    type: 'gradient',
    types:[
      'default',
      'point',
      'radius',
      'corners',
      'border',
      'sound',
      'material',
    ],
  }),
  methods:{
    openLoading(link){
      this.$vs.loading({
        type: this.typeLoading,
        background:'rgb(255, 255, 255)',
        color:'rgb(0, 0, 255)',
      })
      setTimeout( ()=> {
        window.location.href = link 
      }, 1000);
    }
  },
  computed:{
    typeLoading(){
      return this.types[Math.floor(Math.random() * 7)]
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
