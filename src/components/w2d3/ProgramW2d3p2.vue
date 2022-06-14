<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>N</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Факториал: {{ f }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d3p2",
  data() {
    return {
      n: null,
      f: null,
    };
  },
  methods: {
    onInputN($event) {
      this.n = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      this.f = this.factorialize(this.n);
    },
    factorialize(num) {
      if (num === 0 || num === 1) return 1;
      for (let i = num - 1; i >= 1; i--) {
        num *= i;
      }
      return num;
    },
  },
};
</script>
