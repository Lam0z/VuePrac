<template>
  <div class="container">
    <div class="tabs d-flex justify-content-start text-start">
      <div class="tabs-item" v-for="(item, idx) in tabsContent" :key="idx">
        <a
          @click="choose(idx)"
          class="tabs-link text-decoration-none d-flex p-3"
          :class="{ active: item.active }"
          href="#"
          >{{ item.title }}</a
        >
      </div>
    </div>
    <div class="tabs-content-item p-3 border-top border-primary text-start">
      {{ tabsContent[curIndex].descr }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      curIndex: 0,
      tabsContent: [
        {
          title: "Active",
          descr: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
          href: "",
          active: true,
        },
        {
          title: "Link",
          descr:
            "Quaerat at eius asperiores sed minus dignissimos est iusto nemo.",
          href: "",
          active: false,
        },
        {
          title: "Link",
          descr: "Vero veritatis veniam laborum excepturi reprehenderit?",
          href: "",
          active: false,
        },
      ],
    };
  },
  methods: {
    choose(i) {
      this.curIndex = i;
      this.tabsContent.forEach((i) => {
        i.active = false;
      });
      this.tabsContent[i].active = true;
    },
  },
};
</script>

<style>
.tabs-link {
  transition: 0.2s all ease-in;
}
.tabs-link.active {
  background: #d4d4d4;
  color: white;
}
.tabs-link:hover {
  background: #d4d4d4;
}
</style>
