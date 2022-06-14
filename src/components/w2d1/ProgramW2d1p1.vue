<template>
  <div class="program">
    <p class="program__paragraph">Введите длину ребра куба:</p>
    <input
      type="text"
      class="program__input"
      :value="w2d1p1.cubeLength"
      @input="onCubeLengthChange($event)"
      placeholder="Например: 5.3"
    />
    <p class="program__paragraph">
      Площадь грани куба: {{ w2d1p1.cubeFaceArea }}
    </p>
    <p class="program__paragraph">
      Площадь полной поверхности куба: {{ w2d1p1.cubeFullArea }}
    </p>
    <p class="program__paragraph">Объем куба: {{ w2d1p1.cubeVolume }}</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "ProgramW2d1p1",
  data() {
    return {
      w2d1p1: {
        cubeLength: null,
        cubeFaceArea: 0,
        cubeFullArea: 0,
        cubeVolume: 0,
      },
    };
  },
  methods: {
    onCubeLengthChange($event) {
      this.w2d1p1.cubeLength = Number($event.target.value);
      this.w2d1p1.cubeFaceArea =
        this.w2d1p1.cubeLength * this.w2d1p1.cubeLength;
      this.w2d1p1.cubeFullArea = this.w2d1p1.cubeFaceArea * 6;
      this.w2d1p1.cubeVolume = Math.pow(this.w2d1p1.cubeLength, 3);
    },
  }
};
</script>
