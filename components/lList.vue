<template>
  <div ref="l-list-box" class="l-list" @scroll="watchScroll">
    <div
      class="l-list__el"
      :style="!getElState(index) ? `height: ${elHeight}px;` : ''"
      v-for="(el, index) in value"
      :key="index"
    >
      <template v-if="getElState(index)">
        <slot :data="el">
          test
        </slot>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: "lList",
  data() {
    return {
      visibleElements: 0,
      elHeight: 0,
      boxHeight: 0,
      listPadding: 0,
    }
  },
  props: {
    value: {
      type: Array,
      default: () => {
        return []
      }
    },
    overflowElementsCount: {
      type: Number,
      default: () => {
        return 2
      }
    }
  },
  watch: {

  },
  updated() {
    this.parseBoxData();
  },
  mounted() {
    this.parseBoxData();
  },
  methods: {
    watchScroll(evn) {
      const target = evn.target;
      this.listPadding = Math.ceil(target.scrollTop / this.elHeight);
    },
    getElState(index) {
      return this.listPadding - this.overflowElementsCount <= index &&
        index < this.listPadding + this.visibleElements + this.overflowElementsCount;
    },
    parseBoxData() {
      const box = this.$refs["l-list-box"];
      this.boxHeight = box.clientHeight;
      const children = box.childNodes;
      this.elHeight = Object(children[0]).clientHeight;
      this.visibleElements = Math.ceil(this.boxHeight / this.elHeight);
    }
  }
}
</script>

<style lang="scss" scoped>
.l-list {
  &__el {
    box-sizing: border-box;
  }
}
</style>
