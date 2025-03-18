<script setup lang="ts">
import {ref} from 'vue'

const theVideo = ref<HTMLVideoElement|null>(null)
const playButton = ref<HTMLButtonElement|null>(null)
//const videoVolume = ref<HTMLAudioElement|null>(null)
const muteButton = ref<HTMLButtonElement|null>(null)

const seekMax = ref<number>(0)
const seekValue = ref<number>(0)

const seekMaxVolume = ref<number>(1);
const seekValueVolume = ref<number>(theVideo.value?.volume ?? 1);

function togglePlay():void {
  if (theVideo.value!.paused || theVideo.value!.ended) {
    theVideo.value!.play()
  } else {
    theVideo.value!.pause()
  }
}

function toggleMute(): void {
  if (theVideo.value) {
    theVideo.value.muted = !theVideo.value.muted;
    toggleMuteButtonLabel();
  }
}


function togglePlayButtonLabel():void {
  playButton.value!.textContent = theVideo.value!.paused ? "Play" : "Pause"
}

function toggleMuteButtonLabel():void {
  muteButton.value!.textContent = theVideo.value!.muted ? "Unmute" : "Mute"
}

function setupSeekbar(): void {
  seekMax.value = theVideo.value!.duration
  console.log(seekMax.value)
}

function updateSeekbar(): void {
  seekValue.value = theVideo.value!.currentTime
}

function seekVideo(): void {
  theVideo.value!.currentTime = seekValue.value
}

function setupVolumebar(): void {
  if (theVideo.value) {
    seekMaxVolume.value = 1;
    seekValueVolume.value = theVideo.value.volume;
  }
}

function updateVolumebar(): void {
  if (theVideo.value) {
    seekValueVolume.value = theVideo.value.volume;
  }
}

function seekVolume(): void {
  if (theVideo.value) {
    theVideo.value.volume = seekValueVolume.value;
    theVideo.value.muted = seekValueVolume.value === 0;
  }
}

function requestFullscreen(): void {
  theVideo.value!.requestFullscreen()
}

</script>

<template>

<video
  ref="theVideo"
  @play="togglePlayButtonLabel"
  @pause="togglePlayButtonLabel"
  @durationchange="setupSeekbar"
  @timeupdate="updateSeekbar"
  @volumechange="updateVolumebar">

  <source src="/bigBunny.mp4" type="video/mp4">
</video>

  <br>
  <button ref="playButton" @click="togglePlay">Play</button><br>
  <input type="range" min="0" :max="seekMax" v-model="seekValue" @change="seekVideo" step="any"><br>
  <button @click="requestFullscreen">Fullscreen</button><br>
  <button ref="muteButton" @click="toggleMute">Mute</button><br>
  <input
  type="range"
  min="0"
  :max="seekMaxVolume"
  v-model="seekValueVolume"
  @change="seekVolume"
  step="any"/>

  
</template>

<style scoped>

</style>
