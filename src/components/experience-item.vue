<template>
<section>
  <division class="sub-division" :left="experienceDetails.left" :right="experienceDetails.right"></division>
  <header>{{ experienceDetails.header }}</header>
  <section class="player">
    <span>{{ experienceDetails.player }}</span>
  </section>
  <dl>
    <dd v-for="item in experienceDetails.items" :key="item.id">
      <i class="iconfont icon-file"></i>
      <span v-html="item"></span>
    </dd>
  </dl>
</section>
</template>
<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import { ExperienceDetail as detailInte } from '@/common/experience-detail';
import division from '@/components/division.vue';

@Component({
  components: {
    division,
  },
})
export default class Experience extends Vue {
  @Prop({
    required: true,
    type: Object,
  })
  private experienceDetails !: detailInte;

}
</script>
<style lang="scss" scoped>
section {
  width: 100%;
  word-break: break-all;
  .sub-division {
    position: relative;
    top: 1.4rem;
    left: -1%;
  }
  header {
    margin: 1.4rem .8rem .8rem 1.9rem;
    font-size: 22px;
    font-weight: bolder;
    // margin: 1.5rem;
    margin-top: 2.5rem;
    margin-bottom: 0;
    letter-spacing: 2px;
  }
  .player {
    margin: .3rem 0 0;
    margin-left: 1.5rem;
    margin-bottom: -.8rem;
    width: 95%;
    line-height: 30px;
    span {
      font-size: 18px;
      font-weight: 1000;
      letter-spacing: 1.5px;
      color: cadetblue;
    }
  }
  section, dd {
    letter-spacing: .5px;
    margin-left: .5rem;
    margin-top: .25rem;
    i {
      font-size: 16px;
      margin-left: 1rem;
    }
    span {
      margin-left: .4rem;
      font-size: 14px;
      line-height: .4rem;
      ::v-deep span{
        color: cadetblue;
        transition: all .5s;
      }
      ::v-deep span:hover {
        margin-right: .2rem;
        margin-left: .2rem;
      }
      ::v-deep a:link {
        color: cadetblue;
      }
      ::v-deep a:visited {
        color: cadetblue;
      }
    }
    // margin: .5rem;
    // margin-top: .8rem;
    // i {
    //   font-size: 25px;
    //   margin-left: 1rem;
    // }
    // span {
    //   margin-left: 1rem;
    //   font-size: 18px;
    //   ::v-deep span{
    //     color: cadetblue;
    //     transition: all .5s;
    //   }
    //   ::v-deep span:hover {
    //     margin-right: .2rem;
    //     margin-left: .2rem;
    //   }
    // }
  }
}
</style>