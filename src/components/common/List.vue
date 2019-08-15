<template>
  <div class="list">
    <div v-if="title" class="title">{{ title }}</div>
    <div>
      <div
        v-for="(item, key) in items"
        :key="key"
        class="list-item"
        @click="$emit('item-clicked', item)"
      >
        <slot v-bind="item" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    title: {
      type: String,
      default: () => null
    },
    items: {
      type: Array,
      required: true
    }
  }
};
</script>

<style>
.title {
  top: 0px;
  position: sticky;
  background-color: #616365;
  padding: 8px;
}

.list-item {
  border-bottom: 1px solid #616365;
  padding: 4px;
  background-color: #f8f8f8;
}

.list-item:hover {
  background-color: white;
}

.list {
  border: 1px solid #616365;
  height: 100%;
  overflow-y: scroll;
}
</style>
