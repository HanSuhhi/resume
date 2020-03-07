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
  padding-top: .6rem;
  word-break: break-all;
  .sub-division {
    position: relative;
    top: .8rem;
    left: -2%;
  }
  header {
    margin: 1.4rem .8rem .8rem 1.9rem;
    font-size: 26px;
    font-weight: bolder;
    margin: 2rem;
    margin-bottom: 1rem;
    letter-spacing: 2px;
  }
  .player {
    margin-left: 1.2rem;
    span {
      font-size: 20px;
      font-weight: 1000;
      letter-spacing: 1.5px;
      color: cadetblue;
    }
  }
  section, dd {
      margin: .5rem;
      margin-top: .8rem;
      i {
        font-size: 25px;
        margin-left: 1rem;
      }
      span {
        margin-left: 1rem;
        font-size: 18px;
        line-height: 1.8rem;
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