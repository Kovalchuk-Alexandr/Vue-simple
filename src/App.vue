<!-- Компонента, обычно содержит 3 момента:
1 - HTML-code, который будет показан пользователю
2 - CSS - стили, которые будут добавлены к HTML
3 - JS (Vue JS) code - -->
<!-- Подключаем компонент (шапку) из файла Header.vue -->
<template>
  <Header title="itProger" />
  <Articles />
  <!-- можно вызывать несколько раз <Header title="Main text 1 "/>
    <Header title="Main text 2 "/>
    <Header title="Main text 3"/> -->
</template>

<script>
import Header from "./components/Header.vue";
import Articles from "./components/Articles.vue";

export default {
  // Чтобы вывести, указываем с какими компонентами будет работать
  components: {
    Header,
    Articles,
  },
  // Внутри data() можно создать разные переменные (свойства)
  // с которыми можем работать внутри HTML
  data() {
    return {};
  },
};
</script>

<style>
/* Здесь прописываем глобальные стили для всего сайта */
* {
  margin: 0;
  padding: 0;
  /* обводки должны вписываться в ширину объекта */
  box-sizing: border-box;
}

body {
  background: antiquewhite;
}
</style>
