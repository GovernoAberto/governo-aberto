<template>
  <btn-download-json :url="url"></btn-download-json>
</template>
<script>
import ApiService from '@/services/ApiService';

export default {
  props: {
    alias: {
      type: String,
      required: true
    },
    city: {
      type: Number,
      required: true
    }
  },
  computed: {
    url() {
      return new ApiService().getDownloadTableRoute(this.alias, 'json', this.city);
    }
  }
}
</script>

<style>

</style>