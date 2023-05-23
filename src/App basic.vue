<!-- Компонента, обычно содержит 3 момента:
1 - HTML-code, который будет подказан пользователю
2 - CSS - стили, которые будут добавлены к HTML
3 - JS (Vue JS) code - -->

<template>
    <!-- для вызова обработчика можно использовать
    ':' '@' v-on:click -->
    <h1 v-on:click="changeText()">Hello {{title.toLowerCase()}}</h1>
    <p @mouseover="changeText('Some new')">Hello Text {{ !isHasCar }}</p>
    <p v-bind:style="style">{{ info }}</p>
    <!-- changeTextDynamic($event.target.value)
    вызываем ф.-обработчик и передаем в нее то, что ввел пользователь -->
    <input type="text" @input="changeTextDynamic($event.target.value)"/><br><br>

    <input type="text" @input="changeStyle($event.target.value)"/>
</template>

<script>
export default {
    // Внутри data() можно создать разные переменные (свойства)
    // с которыми можем работать внутри HTML
    data() {
        return {
            title: "Hello World!!!",
            isHasCar: true,
            userInput: '',
            style: ''
        }
    },
    // Создание методов
    methods: {
        changeText(word = "New") {
            this.title = word;
        },
        changeTextDynamic(value) {
            this.userInput = value;
        },
        changeStyle(value) {
            this.style = value;
        }  
    },
    // ф., которые в аторежиме отслеживают изменение переменных, 
    //как только переменная меняется, ф. выполняется
    computed: {
        info() {
            if (this.userInput === "") return "";
            else
            return "User text: " + this.userInput + "!";
        },
    },
};
</script>

<style>

</style>