<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>N</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Исходный массив:<br/>{{ arr }}</p>
    <p class="program__paragraph">Результат:<br/>{{ result }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d4p1",
  data() {
    return {
      n: null,
      arr: [],
      result: [],
    };
  },
  methods: {
    onInputN($event) {
      this.n = Number($event.target.value);
    },
    onSubmit($event) {
      $event.preventDefault();
      this.arr = Array.from({ length: this.n }, () =>
        Math.floor(Math.random() * 40)
      );
      let indexMin = this.n - 1;
      let indexMax = 0;

      for (let i = 0; i < this.n; i++) {
        indexMin = this.arr[indexMin] > this.arr[i] ? i : indexMin;
        indexMax = this.arr[indexMax] < this.arr[i] ? i : indexMax;
      }
      if (indexMin > indexMax) {
        [indexMin, indexMax] = [indexMax, indexMin];
      }
      let k = 0;
      for (let i = 0; i < indexMin; i++) {
        this.result[k++] = this.arr[i];
      }
      for (let i = indexMax; i >= indexMin; i--) {
        this.result[k++] = this.arr[i];
      }
      for (let i = indexMax + 1; i < this.n; i++) {
        this.result[k++] = this.arr[i];
      }
    },
  },
};
</script>
