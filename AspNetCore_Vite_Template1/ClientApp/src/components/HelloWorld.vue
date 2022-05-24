<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios  from "axios"

defineProps<{ msg: string }>()

    const count = ref(0)


    const userUrl = '/api/User/GetUserDetail'
    const employeeUrl = '/api/User/GetEmployees'
    const projectUrl = '/api/Project/GetOpenProjectsDateSpan?startDate=2022%2F05%2F01&endDate=2022%2F05%2F10'
    const url = "/Weatherforecast"
    //fetch(employeeUrl, {
    //    method: 'GET',
    //    mode: 'cors',
    //    credentials: 'include'
    //}).then(res => res.json())

    onMounted(() => {
        axios.get(url).then((res) => {
          var ss = res.data
          console.log(ss)
          //state.sentBox = response.data;
          //Promise.all(state.sentBox);
          //state.sentBoxCount = state.sentBox.length;
        });
      }
    )

</script>

<template>
  <h1>{{ msg }}</h1>

  <p>
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>
    +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
  </p>

  <p>See <code>README.md</code> for more information.</p>
  <b>SSSSSSSS</b> 
  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Docs 
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Docs</a>
  </p>

  <button type="button" @click="count++">count is: {{ count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
