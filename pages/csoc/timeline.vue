<template>
<v-container>
  <div class="timeline">
    <CommonTimeline :items="items" />
  </div>
</v-container>
</template>

<script>
import CommonTimeline from '@/components/CommonTimeline'
import '@mdi/font/css/materialdesignicons.css'
export default {
  components: {
    CommonTimeline,
  },
  async fetch() {
    const data = await this.$content('timeline_data').fetch()
    this.items = data.items
  },
  data() {
    return {
      items: [],
    }
  },
}
</script>
<style scoped>
.timeline{
  margin: 10% 0px;
}
</style>
