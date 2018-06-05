<template>
  <div>
    <block v-if="data && data.length" v-for="(item, index) in data" :key="index">
      <htmlParse :item="item" />
    </block>
  </div>
</template>

<script>
  import htmlParse from './components/htmlParse1';

  export default {
    props: {
      data: null
    },
    components: {
      htmlParse
    }
  };
</script>