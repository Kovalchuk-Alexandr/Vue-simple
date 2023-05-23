<!-- Компонента, обычно содержит 3 момента:
1 - HTML-code, который будет подказан пользователю
2 - CSS - стили, которые будут добавлены к HTML
3 - JS (Vue JS) code - -->

<template>
  <div v-if="num < 3 && isVisible">
    <h1>Hello</h1>
    <!-- v-if="num > 3" абзац будет показываться, если num > 3 -->
    <p>First</p>
  </div>
  <div v-else-if="num == 3">Second div</div>
  <div v-else>Third div</div>
  <!-- Полученное при вводе значение устанавливаем 
    в переменную num и в зависимости от значения, выводим -->
  <input @input="this.num = $event.target.value" /><br /><br />
  <!-- '!isVisible - проверка на false -->
  <!-- При нажатии на кнопку, блок показываем/скрываем -->
  <button @click="this.isVisible = !this.isVisible">Show/Hide</button>
  <!-- v-if - удаляет объект -->
  <div v-if="isVisible">Div text 1</div>
  <!-- v-show - показывает/скрывает объект -->
  <div v-show="!isVisible">Div text 2</div>
  <p>{{ books[1].author }}</p>
  <ul>
    <li v-for="(element, index) in books" v-bind:key="index">
      № {{ index + 1 }} {{ element.name }} - <b>{{ element.author }}</b> /
      <em>{{ element.genre }}</em>
    </li>
  </ul>
</template>

<script>
export default {
  // Внутри data() можно создать разные переменные (свойства)
  // с которыми можем работать внутри HTML
  data() {
    return {
      num: 3,
      isVisible: false,
      books: [
        { name: "1984", author: "Джордж Оруэл", genre: "Роман" },
        {
          name: "Собака Баскервилей",
          author: "Артур Коннан Дойл",
          genre: "Детектив",
        },
        { name: "Гарри Поттер", author: "Джоан Роулинг", genre: "Роман" },
      ],
    };
  },
};
</script>

<style></style>
