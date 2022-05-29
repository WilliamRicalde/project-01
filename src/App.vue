<script setup>
import { ref } from 'vue'

const video = ref(null)
const isPlaying = ref(false)
const question = ref(true)

const handlePlay = () => {
  video.value.play()
  isPlaying.value = true

}

const handleConfetti = () => {
  question.value = false
  confetti()
}

const handleAnimation = () => console.log('animation')
</script>

<template>
  <main>
    <video ref="video" controls @ended="handleAnimation" >
      <source src="https://v16-webapp.tiktok.com/0a8305350e313c90cdab42eb227130c8/62940e70/video/tos/useast2a/tos-useast2a-ve-0068c004/c45a363fc6c148d5a71151a04801fc4a/?a=1988&ch=0&cr=0&dr=0&lr=tiktok_m&cd=0%7C0%7C1%7C0&cv=1&br=1816&bt=908&btag=80000&cs=0&ds=3&ft=eXd.6HpDMyq8ZAAXSwe2NJZ3yl7Gb&mime_type=video_mp4&qs=0&rc=Njw3Nzo5MzczZWZkZGdmZ0BpMzlnOmg6Zjg7OjMzNzczM0AvYjExXy41NmMxMDUuXmEyYSNxMWdgcjRnMWJgLS1kMTZzcw%3D%3D&l=202205291822410101920460321B61D0F6" type="video/mp4" />
    </video>
    <button v-if="!isPlaying" class="play-button" @click="handlePlay">
      <Vue3Lottie
        animationLink="https://assets4.lottiefiles.com/packages/lf20_gpjapb8d.json"
        :height="200"
        :width="200"
      />
    </button>
  </main>
  <div>
    <Vue3Lottie
      animationLink="https://assets2.lottiefiles.com/packages/lf20_wsyyln4p.json"
      :height="200"
      :width="200"
    />
  </div>
  <section>
    <h1 v-if="question">¿Quieres ser mi novia?</h1>
    <h1 v-else>Wujuuuuu 🥳🥳🥰❤️</h1>
    <button @click="handleConfetti" class="yes-button" v-if="question">Si</button>
  </section>
</template>

<style>
body {
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  background-color: black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: black;
  margin: 0;
  padding: 0;
}

main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  padding: 0;
}

video {
  width: 100vw;
  height: 100vh;
}

.play-button {
  position: absolute;
  z-index: 10;
}

div {
  width: 100vw;
  height: 100vh;
  background-color: black;
}

section {
  height: 100vh;
  width: 100vw;
  display: grid;
  place-content: center;
  color: white;
}

.yes-button {
  padding: 10px 20px;
  background-color: darkviolet;
  outline: none;
  border: none;
  color: aliceblue;
  font-size: 22px;
  font-weight: bold;
  border-radius: 100px;
}
</style>
