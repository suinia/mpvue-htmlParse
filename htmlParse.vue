<template>
  <div>
    <block v-if="nodeList && nodeList.length" v-for="(item, index) in nodeList" :key="index">
      <htmlParse :item="item" />
    </block>
  </div>
</template>

<script>
  import htmlParse from './components/htmlParse1';
  import html2json from './lib/html2json/index';
  export default {
    data() {
      return {
        nodeList: []
      }
    },
    props: {
      data: null,
      html: ''
    },
    components: {
      htmlParse
    },
    mounted() {
      if (this.data) {
        this.nodeList = this.data;
      } else {
        this.nodeList = html2json(this.html);
      }
    }
  };
</script>