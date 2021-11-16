<template>
<main class="h-screen flex">
  <modal v-if="modal" :colors="colors" @toggle="toggle()"></modal>
  <!-- color preview section -->
  <div class="h-full sm:w-2/3 md:w-3/4 pt-1 px-2 bg-gray-100">
    <preview :colors="colors"></preview>
  </div>
  <!-- color input section -->
  <div class="h-full sm:w-1/3 md:w-1/4 px-2 bg-gray-300 shadow-lg py-5 flex flex-col justify-between">
    <navigation v-model:colors="colors"></navigation>

    <div class="button-container">
      <button class="w-full bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mb-5 inline-flex items-center justify-center">
        <span>Generate</span>
        <span class="material-icons fill-current ml-2">refresh</span>
      </button>
      <button @click="toggle()" class="w-full bg-yellow-500 hover:bg-yellow-600 text-white font-bold py-2 px-4 rounded inline-flex items-center justify-center">
        <span>Export</span>
        <span class="material-icons fill-current ml-2">file_download</span>
    </button>
    </div>
  </div>
</main>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import './assets/tailwind.css'
import Navigation from './components/Navigation.vue';
import Preview from './components/Preview.vue';
import Modal from './components/Modal.vue';
@Options({
  components: {
    Navigation,
    Preview,
    Modal
  },
})
export default class App extends Vue {
  name = 'custom';
  modal = false;
  colors = [
    {
      name: '100',
      value: '#f8f9fa'
    },
    {
      name: '200',
      value: '#e9ecef'
    },
    {
      name: '300',
      value: '#dee2e6'
    },
    {
      name: '400',
      value: '#ced4da'
    },
    {
      name: '500',
      value: '#adb5bd'
    },
    {
      name: '600',
      value: '#6c757d'
    },
    {
      name: '700',
      value: '#495057'
    },
    {
      name: '800',
      value: '#343a40'
    },
    {
      name: '900',
      value: '#212529'
    }
  ];

  toggle() {
    switch (this.modal) {
      case false:
        this.modal = true;
        break;
      case true:
        this.modal = false;
    }
  }
}
</script>

<style lang="postcss" scoped>
  @import url(https://fonts.googleapis.com/icon?family=Material+Icons);
  .button-container {
  }

  input {
    @apply border-2 p-2 rounded-md focus:bg-white focus:ring-indigo-500 focus:border-indigo-500 w-full;
}
</style>
