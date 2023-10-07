<template>
  <div class="container">
    <!-- <div class="row">
      <div class="col">col</div>
      <div class="w-100"></div>
      <div class="col">col</div>
      <div class="w-100"></div>
      <div class="col">col</div>
      <div class="col">col</div>
    </div> -->
    <div class="content-list">
      <div
        class="content-item"
        :class="{ hidden: !item.show }"
        v-for="(item, idx) in showContent"
        :key="idx"
      >
        <img src="../assets/logo.png" alt="content-item-img" />
        <div class="content-item-title">{{ item.title }}</div>
        <div class="content-item-descr">{{ item.descr }}</div>
      </div>
    </div>
    <div class="content-show-container" v-if="!isAll">
      <button class="btn btn-primary content-showmore-btn" @click="incrCount">
        Show more
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showCount: 2,
      isAll: false,
      showItems: [],
      items: [
        {
          title: "title - 1",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 2",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 3",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 4",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 5",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 6",
          descr: "lorem ipsum set dolore",
          show: false,
        },
        {
          title: "title - 7",
          descr: "lorem ipsum set dolore",
          show: false,
        },
      ],
    };
  },
  methods: {
    incrCount() {
      this.showCount += 2;
    },
  },
  computed: {
    showContent() {
      const showItems = this.items.slice(0, this.showCount);

      const newShowItems = showItems.map((i) => {
        return i;
      });
      console.log(newShowItems);

      showItems.forEach((i) => (i.show = true));

      if (this.items.length === showItems.length) {
        this.isAll = true;
        return showItems;
      } else {
        return showItems;
      }
    },
  },
};
</script>

<style>
.content-list {
  display: grid;
  row-gap: 10px;
  padding: 10px;
  background: lightgrey;
}
.content-item {
  display: grid;
  justify-content: center;
  row-gap: 20px;
  background: whitesmoke;
}

.content-item-title {
}

.content-item-descr {
}

@media (min-width: 576px) {
  .content-list {
    padding: 20px;
    row-gap: 20px;
    column-gap: 20px;
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (min-width: 992px) {
  .content-list {
    column-gap: 20px;
    grid-template-columns: repeat(3, 1fr);
  }
}
.hidden {
  display: none;
}
</style>
