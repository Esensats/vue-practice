<template>
  <div class="ProgramView">
    <div class="container">
      <h2 class="ProgramView__heading">
        {{ filteredTask.name }} - {{ filteredProgram.name }}
      </h2>
      <p class="ProgramView__paragraph">{{ filteredProgram.overview }}</p>
      <div class="task" v-if="filterTask === 'w2d1'">
        <ProgramW2d1p1 v-if="filterProgram === 'p1'" />
        <ProgramW2d1p2 v-else-if="filterProgram === 'p2'" />
        <ProgramW2d1p3 v-else-if="filterProgram === 'p3'" />
      </div>
      <div class="task" v-else-if="filterTask === 'w2d2'">
        <ProgramW2d2p1 v-if="filterProgram === 'p1'" />
        <ProgramW2d2p2 v-else-if="filterProgram === 'p2'" />
      </div>
      <div class="task" v-else-if="filterTask === 'w2d3'">
        <ProgramW2d3p1 v-if="filterProgram === 'p1'" />
        <ProgramW2d3p2 v-else-if="filterProgram === 'p2'" />
        <ProgramW2d3p3 v-else-if="filterProgram === 'p3'" />
      </div>
      <div class="task" v-else-if="filterTask === 'w2d4'">
        <ProgramW2d4p1 v-if="filterProgram === 'p1'" />
        <ProgramW2d4p2 v-else-if="filterProgram === 'p2'" />
      </div>
      <div class="task" v-else-if="filterTask === 'w2d5'">
        <ProgramW2d5p1 v-if="filterProgram === 'p1'" />
        <ProgramW2d5p2 v-else-if="filterProgram === 'p2'" />
      </div>
      <div class="task" v-else-if="filterTask === 'w2d6'">
        <ProgramW2d3p2 v-if="filterProgram === 'p3'" />
      </div>
      <!-- <div class="task">
        <router-view name="program" />
      </div> -->
      <router-link class="btn btn-block" to="/">Назад</router-link>
    </div>
  </div>
</template>

<script>
import json from "@/data/data.json";
import ProgramW2d1p1 from "@/components/w2d1/ProgramW2d1p1.vue";
import ProgramW2d1p2 from "@/components/w2d1/ProgramW2d1p2.vue";
import ProgramW2d1p3 from "@/components/w2d1/ProgramW2d1p3.vue";
import ProgramW2d2p1 from "@/components/w2d2/ProgramW2d2p1.vue";
import ProgramW2d2p2 from "@/components/w2d2/ProgramW2d2p2.vue";
import ProgramW2d3p1 from "@/components/w2d3/ProgramW2d3p1.vue";
import ProgramW2d3p2 from "@/components/w2d3/ProgramW2d3p2.vue";
import ProgramW2d3p3 from "../components/w2d3/ProgramW2d3p3.vue";
import ProgramW2d4p1 from "@/components/w2d4/ProgramW2d4p1.vue";
import ProgramW2d4p2 from "@/components/w2d4/ProgramW2d4p2.vue";
import ProgramW2d5p1 from "@/components/w2d5/ProgramW2d5p1.vue";
import ProgramW2d5p2 from "@/components/w2d5/ProgramW2d5p2.vue";
export default {
  name: "ProgramView",
  data() {
    return {
      filterTask: this.$route.params.taskSlug,
      filterProgram: this.$route.params.programSlug,
    };
  },
  computed: {
    filteredTask() {
      return json.tasks.find((object) => object.slug === this.filterTask);
    },
    filteredProgram() {
      return this.filteredTask.programs.find(
        (object) => object.slug === this.filterProgram
      );
    },
  },
  methods: {},
  components: { ProgramW2d1p1, ProgramW2d1p2, ProgramW2d1p3, ProgramW2d2p1, ProgramW2d2p2, ProgramW2d3p1, ProgramW2d3p2, ProgramW2d3p3, ProgramW2d4p1, ProgramW2d4p2, ProgramW2d5p1, ProgramW2d5p2 },
};
</script>

<style lang="scss">
@use "@/styles";
.ProgramView {
  &__heading {
    margin-bottom: 0.8rem;
    text-align: center;
  }
  .task {
    font-family: "Fira Code", "Courier New", Courier, monospace;
    background-color: styles.$colorCodeDark;
    color: styles.$colorCodeLight;
    padding: 1rem 0.5rem;
    border-radius: 5px;
    border: 2px solid styles.$colorPrimary;
    box-shadow: 0 0 10px 2px styles.$colorPrimaryShadow;

    margin-top: 1rem;
    margin-bottom: 1rem;

    .program {
      &__input {
        background-color: styles.$colorCodeDarker;
        color: styles.$colorCodeLight;
        margin: 0.25rem;
        padding: 0.25rem;
        font-size: 1em;
        font-family: inherit;

        border-radius: 5px;

        &::placeholder {
          color: styles.$colorCode;
        }
        &:focus {
          outline: none;
        }
      }
      &__paragraph {
        margin-top: 5px;
      }
      .btn {
        padding: 6px 9px;
        margin-left: 15px;
        margin-top: 5px;
        margin-bottom: 5px;
      }
    }
  }
}
</style>
