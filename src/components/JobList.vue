<template>
  <div class="job-list">
    <p>Order by {{ order }}</p>
  </div>
</template>

<script lang="ts">
import {defineComponent, PropType} from 'vue';
import OrderTerm from '@/types/OrderTerm';

export default defineComponent({
  name: 'JobList',
  props: {
    order: {
      required: true,
      types: String as PropType<OrderTerm>
    }
  },
  setup: function () {

    return {

    }
  }
});

</script>

<style>

</style>