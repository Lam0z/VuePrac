<template>
  <div class="container">
    <div class="accordion">
      <div
        class="accordion-item"
        v-for="(item, idx) in accordionData"
        :key="idx"
      >
        <h2 class="accordion-header" @click="toggle(idx)">
          <button
            class="accordion-button"
            type="button"
            :class="{ collapsed: !item.show }"
          >
            {{ item.title }}
          </button>
        </h2>
        <div class="accordion-collapse collapse" :class="{ show: item.show }">
          <div class="accordion-body">
            {{ item.description }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      accordionData: [
        {
          title: "1occaecati dolor accusantium",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, voluptatum.",
          show: true,
        },
        {
          title: "2occaecati dolor accusantium",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, voluptatum.",
          show: false,
        },
        {
          title: "3occaecati dolor accusantium",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, voluptatum.",
          show: false,
        },
      ],
    };
  },
  methods: {
    toggle(i) {
      //   hide All
      this.accordionData.forEach((i) => {
        i.show = false;
      });
      const item = this.accordionData[i];
      item.show = item.show ? false : true;
    },
  },
};
</script>

<style scoped>
.accordion-button {
  background-color: var(--bs-accordion-active-bg);
}
</style>
