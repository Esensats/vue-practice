<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>N</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Исходный массив:<br />{{ arr }}</p>
    <p class="program__paragraph">Результат:<br />{{ result }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d4p2",
  data() {
    return {
      n: null,
      arr: null,
      result: null,
    };
  },
  methods: {
    onInputN($event) {
      this.n = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      this.result = 0;
      this.arr = Array.from({ length: this.n }, () =>
        Math.floor(Math.random() * 40)
      );
      for (const el of this.arr) {
        if(this.arr[0] < el) this.result++;
      }
    },
  },
};
</script>
