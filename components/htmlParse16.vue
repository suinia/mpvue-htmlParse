<template>
  <!--文本节点-->
  <block v-if="item.node == 'text' && item.text"><text>{{item.text}}</text></block>
  <!--其他点-->
  <block v-else-if="item.node == 'element'">
    <!--图片节点-->
    <block v-if="item.tag == 'img'">
      <parse-img :item="item" />
    </block>
    <!--换行-->
    <block v-else-if="item.tag == 'br'">
      <parse-br />
    </block>
    <!--wx video节点-->
    <block v-else-if="item.tag == 'video' || (item.tag == 'iframe' && item.attr && item.attr.class == 'video_iframe')">
      <parse-video :item="item"/>
    </block>
  </block>
</template>

<script>
import parseImg from './parseImg';
import parseBr from './parseBr';
import parseVideo from './parseVideo';

export default {
  name: 'wxParse',
  props: {
    item: {
      type: Object,
      default: {}
    }
  },
  components: {
    parseImg,
    parseBr,
    parseVideo
  }
};
</script>
