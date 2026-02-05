<script setup>
import Header from './components/layout/Header.vue'
import MainContent from './components/layout/MainContent.vue'
import { ref, onMounted } from 'vue'
import axios from 'axios';

const regions = ref([])


onMounted(async () => {
/*
  axios.get('/schools.json')
    .then(response => {
      console.log(response.data.data.list);
    })
    .catch(error => {
      console.error('Error fetching data:', error);
    });
  */
/*  try {
    const response = await fetch('/schools.json')
    const json = await response.json()
    
    // Присваиваем именно массив из ключа data
    regions.value = json.data 
    
    console.log('Массив получен:', regions.value.list)
  } catch (error) {
    console.error('Ошибка:', error)
  }
*/
  
})
</script>

<template>

  <Header title="Тестовое задание" />
  <MainContent title="Таблица учреждений" />
  
</template>

<style scoped lang="scss">
.logo {
  height: 6em;
  padding: 1.5em;
}
</style>
