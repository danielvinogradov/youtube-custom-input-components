<template>
  <div class="home">

    <div class="block">
      <h2 class="heading">Как вас зовут?</h2>
      <ui-input v-model:username="userName"/>
    </div>

    <div class="block">
      <h2 class="heading">Оцените качество доставки</h2>
      <ui-radio value="bad" v-model="deliveryQuality">Плохо</ui-radio>
      <ui-radio value="ok" v-model="deliveryQuality">Нормально</ui-radio>
      <ui-radio value="good" v-model="deliveryQuality">Хорошо</ui-radio>
    </div>

    <div class="block">
      <h2 class="heading">Что можно было бы улучшить?</h2>
      <ui-checkbox value="1" v-model="suggestionsList">Скорость доставки</ui-checkbox>
      <ui-checkbox value="2" v-model="suggestionsList">Вежливость курьера</ui-checkbox>
      <ui-checkbox value="3" v-model="suggestionsList">Качество товаров</ui-checkbox>
    </div>

  </div>
</template>

<script>
  import UiInput from '@/components/ui-input.vue'
  import UiRadio from '@/components/ui-radio.vue'
  import UiCheckbox from '@/components/ui-checkbox.vue'

  export default {
    components: { UiInput, UiRadio, UiCheckbox, },
    data() {
      return {
        /**
         * Имя пользователя
         * @type String
         */
        userName: null,

        /**
         * Качество доставки
         * @type String
         */
        deliveryQuality: null,

        /**
         * Что можно было бы улучшить
         * @type Array
         */
        suggestionsList: [],
      }
    },
  }
</script>

<style lang="scss" scoped>
  .block {
    padding: 15px 0;

    &:not(:last-of-type) {
      border-bottom: 1px solid #f4f4f4;
    }
  }

  .heading {
    margin: 0 0 5px 0;
    font-size: 16px;
    color: #010101;
  }
</style>