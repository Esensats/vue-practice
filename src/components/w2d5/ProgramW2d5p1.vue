<template>
  <form class="program" @submit="onSubmit($event)">
    <p class="program__paragraph">Введите <b>число</b>:</p>
    <input type="text" class="program__input" @input="onInputN($event)" />
    <br />
    <input type="submit" class="btn" value="Готово" />
    <p class="program__paragraph">Исходный порядок:<br />{{ num }}</p>
    <p class="program__paragraph">Обратный порядок:<br />{{ rev }}</p>
  </form>
</template>

<script>
export default {
  name: "ProgramW2d5p1",
  data() {
    return {
      num: null,
      rev: null,
    };
  },
  methods: {
    onInputN($event) {
      try {
        this.num = Number($event.target.value);
      } catch (error) {
        this.rev = error.message;
      }
    },
    onSubmit($event) {
      $event.preventDefault();
      let tempNum = this.num;
      this.rev = "";
      while (tempNum > 0) {
        const buffer = tempNum % 10;
        tempNum = Math.floor(tempNum / 10);
        this.rev = this.rev.concat(buffer);
      }
      this.rev = Number(this.rev);
    },
  },
};
</script>
