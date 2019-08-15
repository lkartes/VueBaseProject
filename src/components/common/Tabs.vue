<template>
  <div>
    <ul
      class="nav nav-tabs"
      role="tablist"
    >
      <li
        v-for="(tab, index) in tabs"
        :key="index"
        class="nav-item"
      >
        <a
          class="nav-link"
          data-toggle="tab"
          role="tab"
          :class="{ active : tab.active }"
          :aria-selected="tab.active"
          href=""
          @click="$emit('tab-selected', tab.title)"
        >{{ tab.title }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Tabs',
  props: {
    tabs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>

</style>
