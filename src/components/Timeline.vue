<template>
  <q-timeline
    :color="color"
    :layout="layout"
  >
    <q-timeline-entry
      v-for="(item, i) in items"
      :key="i"
      :title="item.title"
      :subtitle="item.subtitle"
      :icon="item.icon && item.icon"
    >
     <div v-if="item.content.length">
       {{item.content}}
     </div>
    </q-timeline-entry>
  </q-timeline>
</template>

<script>
export default {
  name: 'Timeline',
  props: {
    items: Array,
    layout: {
      type: String,
      default: 'dense'
    },
    color: {
      type: String,
      default: 'red-8'
    }
  }
}
</script>
