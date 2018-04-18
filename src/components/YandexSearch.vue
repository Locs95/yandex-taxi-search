<template>
  <div class="YandexSearch">
      <div class="container yandex-search-wrap">
        <div class="row">
          <div class="col-sm-12">
            <table class="table table-responsive table-hover table-striped">
              <thead>
                <tr>
                  <th scope="col" class="text-center">Марка и модель автомобиля</th>
                  <th scope="col" colspan="6" class="text-center">
                    Минимальный год подключения
                  </th>
                </tr>
                <tr>
                  <th><input type="text" v-model="searchYandex" placeholder="Введите марку или модель автомобиля" class="form-control"></th>
                  <th class="text-center">Эконом</th>
                  <th class="text-center">Комфорт</th>
                  <th class="text-center">Комфорт +</th>
                  <th class="text-center">Бизнес</th>
                  <th class="text-center">Минивэн</th>
                  <th class="text-center">Детский</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in filteredItems" v-bind:key="item.name">
                  <td>{{ item.name }}</td>
                  <td class="text-center">{{ item.economy }}</td>
                  <td class="text-center">{{ item.comfort }}</td>
                  <td class="text-center">{{ item.comfortplus }}</td>
                  <td class="text-center">{{ item.business }}</td>
                  <td class="text-center">{{ item.minivan }}</td>
                  <td class="text-center">{{ item.child }}</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
  </div>
</template>

<script>

import yandexauto from '../yandexauto.json'

export default {
  name: 'YandexSearch',
  data () {
    return {
      searchYandex: '',
      data: yandexauto
    }
  },
  computed: {
     filteredItems() {
         return this.data.filter(item => {
             return item.name.toLowerCase().match(this.searchYandex.toLowerCase())
         })
     }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.yandex-search-wrap {
  min-height: 100vh;
  border: 1px solid #ddd;
}
.table tbody > tr:hover {
  background-color: #FFC000;
}
</style>
