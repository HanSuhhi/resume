<template>
<div class="division">
  <span class="left" v-show="left">{{ left }}</span>
  <!-- <span class="right" v-if="right">{{ right }}</span> -->
</div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component
export default class Division extends Vue {

  @Prop()
  private left?: string;

  @Prop()
  private right?: string;

}
</script>

<style lang="scss" scoped>
.division {
  background-color: #343434;
  height: 2rem;
  width: 100%;
  border-radius: 0 7px 7px 0;
  color: white;
  span {
    font-size: 19px;
    font-weight: bold;
    padding-top: .5px;
    line-height: 2rem;
  }
  .left {
    float: left;
    letter-spacing: 1px;
    padding-left: 2rem;
  }
  .right {
    float: right;
    padding-right: 1rem;
    font-size: 14px;
  }
}
.division::before {
  content: '\e61d';
  font-family: "iconfont" !important;
  font-size: 20px;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 7px;
  background-color: #343434;
  border-radius: 100%;
  position: absolute;
  left: -20px;
  bottom: -2px;
}
</style>
