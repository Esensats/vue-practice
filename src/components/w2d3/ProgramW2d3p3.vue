<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>N</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Результат: {{ result }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d3p3",
  data() {
    return {
      n: null,
      result: null,
    };
  },
  methods: {
    onInputN($event) {
      this.n = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      let temp = 4;
      this.result = 0;
      for (let i = 1; i < this.n; i++) {
        this.result += temp; //1: 4, 2: 12 ...
        temp *= 2;           //1: 8, 2: 16 ...
      }
    },
  },
};
</script>
