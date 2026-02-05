<script setup>
import Button from './../base/Button.vue'
import Search from './../base/Search.vue'
import Dropdown from './../base/Dropdown.vue'
import Calendar from './../Calendar.vue'
import Table from './../base/Table.vue'
import { ref, onMounted } from 'vue'
import axios from 'axios';

const regions = ref([]);

const selectedView = ref('Все виды');
const arrAllView = ['Школа', 'Гимназия', 'Лицей', 'Центр образования'];

const selectedStatus = ref('Все статусы');
const arrAllStatuses = ['Государственные', 'Муниципальные', 'Частные'];

defineProps({
  title: String,
})

onMounted(async () => {
  axios.get('/schools.json')
    .then(response => {
      //regions = ref(structuredClone(response.data.data.list))
    
      console.log(response.data.data.list);
    })
    .catch(error => {
      console.error('Error fetching data:', error);
    });
})
</script>

<template>
  <main class="main-content">
    <div class="container">
      <div class="main-content__box">
        
        <div class="main-content__box-top mb-24">
          <h2>{{ title }}</h2>
          <div class="main-content__box-actions">
            <Search placeholder="Поиск" />            
            <Button
              icon="icon-docs"
              label="Скачать"
              btn-style="accent"
            />
          </div>
        </div>

                
        <div class="main-content__box-filters d-flex flex-col flex-lg-row gap-16 mb-24">
          <Calendar 
            v-model="dates" 
            range 
            :time-config="{ enableTimePicker: false }"
            class="custom-datepieker"
          />

          <Dropdown
            :items="arrAllView" 
            v-model="selectedView" 
          />

          <Dropdown
            :items="arrAllStatuses" 
            v-model="selectedStatus" 
          />
        </div> 
        
        <div class="main-content__box-table">
          <Table />
        </div>
      </div>



      <section class="mt-48">
        <h2 class="mb-24 mt-24 h1">Ui-kit</h2>

        <h4 class="mt-48 mb-24">
          Typography:
        </h4>
        <h2 class="h1 mb-16">Heading H1 (size example)</h2>
        <h2 class="mb-16">Heading H2</h2>
        <h3 class="mb-16">Heading H3</h3>
        <h4 class="mb-16">Heading H4</h4>
        <h5 class="mb-24">Heading H5</h5>

        <h4 class="mt-48 mb-24">
          Buttons primary:
        </h4>
        <div class="d-flex flex-wrap gap-16">
          <Button
            label="Button"
            btn-style="primary"
          />
        </div>

        <h4 class="mt-48  mb-24">
          Buttons accent:
        </h4>
        <div class="d-flex flex-wrap gap-16">
          <Button
            icon="icon-docs"
            label="Скачать"
            btn-style="accent"
          />
          <Button
            icon="icon-search"
            label="Поиск"
            btn-style="accent"
          />
        </div>

        <h4 class="mt-48 mb-24">
          Icons:
        </h4>
        <div class="d-flex flex-wrap gap-16"> 
          <span class="icon-arrow-bottom-sort"></span>
          <span class="icon-search"></span>
          <span class="icon-docs"></span>
          <span class="icon-dash"></span>
          <span class="icon-check"></span>
          <span class="icon-calendar"></span>
          <span class="icon-arrow-top-sort"></span>
          <span class="icon-arrow-right"></span>
          <span class="icon-arrow-left"></span>
          <span class="icon-arrow-select"></span>
        </div>

      </section>


      <!-- <div v-if="regions.length">
        <ul>
          <li v-for="item in regions" :key="item.id">
            {{ item.name }}
          </li>
        </ul>
      </div>
      <div v-else>Загрузка данных из data...</div> -->



    </div>
  </main>
</template>

<style scoped lang="scss">
.main-content {
  padding-top: clmp(24, 48);
  padding-bottom: clmp(24, 48);
  background-color: #F1F4FD;
  flex: 1;

  &__box {
    padding: clmp(16, 24);
    background-color: #fff;
    border-radius: 1rem;
  }

  &__box-top, &__box-actions {
    display: flex;
    flex-direction: column;
    gap: rem(20);

    @include media-min($screen-md-min) {
      align-items: center;
      flex-direction: row;
    }
  }

  &__box-actions {
    @include media-min($screen-md-min) {
      margin-left: auto ;
    }
    .btn {
      justify-content: center;
    }
  }
}

:deep(input.dp__pointer) {
  padding: rem(17) rem(56) rem(17) rem(24);
  border: 1px solid #D3D3DE;
  border-radius: rem(8);
}

:deep(.dp__icon) {
  direction: rtl;
}

:deep(.dp--clear-btn) {
  display: none;
}

</style>
