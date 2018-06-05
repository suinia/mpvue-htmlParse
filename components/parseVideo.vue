<template>
  <div class="html-parse__video">
    <video :src="item.attr.src"></video>
  </div>
</template>
<script>
export default {
  name: 'parseVideo',
  item: {
    type: Object,
    default: {}
  }
};
</script>