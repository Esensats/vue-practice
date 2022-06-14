<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>строку</b>:</p>
    <input type="text" class="program__input" @input="onInputMain($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Результат: {{ result }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d5p2",
  data() {
    return {
      main: "",
      result: "",
    };
  },
  methods: {
    onInputMain($event) {
      try {
        this.main = $event.target.value;
      } catch (error) {
        this.result = error.message;
      }
    },
    onSubmit($event) {
      $event.preventDefault();
      this.result = /\d/.test(this.main)
        ? "Строка содержит цифры"
        : "Строка НЕ содержит цифры";
      if (!this.main) this.result = '';
    },
  },
};
</script>
