<template>
<header class="Head-Info">
  <!-- 头像图片 -->
  <figure>
    <img src="https://ludazuo.oss-cn-beijing.aliyuncs.com/%E8%AF%81%E4%BB%B6%E7%85%A7.jpg">
  </figure>
  <!-- 用户信息 -->
  <ul class="personalInfo">
    <li
      v-for="info in details"
      :key="info.id">
      <i :class="'iconfont icon-' + info.icon"></i>
      <span v-if="!info.link">{{ info.content }}</span>
      <a :href="info.content" v-if="info.link">{{ info.content }}</a>
    </li>
  </ul>
  <!-- 头信息 -->
  <address>
    <h1>{{ name }}</h1>
    <h2>{{ job }}</h2>
  </address>
</header>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import '@/assets/iconfont.css';

@Component
export default class HelloWorld extends Vue {
  private name = '卢大佐';
  private job = '前端实习生';
  private details = [
    {
      icon: 'youxiang',
      content: 'ludazuo741@126.com'
    },
    {
      icon: 'weixin',
      content: '850330897',
    },
    {
      icon: 'dianhua', // 图标名可能根据搜索记录确定
      content: '18966172600'
    },
    {
      icon: 'nianling',
      content: '1998.11.04',
    },
    {
      icon: 'github',
      content: 'https://github.com/HanSuhhi',
      link: true,
    },
    {
      icon: 'weizhi',
      content: '浙江 - 杭州',
    }
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@media (min-width: 800px)  {
  header {
    background: #343434;
    padding: 25px;
    display: flex;
    figure {
      padding: 0 20px 0 20px;
      img {
        width: 140px;
        height: auto;
        transition: all 1s;
        box-shadow: 2px 5px 10px 5px rgba($color: black, $alpha: .2);
      }
      img:hover {
        transform: scale(1.03);
      }
    }
    ul {
      padding: 0 20px;
      padding-inline-start: 0px;
      text-align: left;
      color: white;
      li {
        font-size: 16px;
        font-weight: 100;
        list-style-type: none;
        margin-top: .5rem;
        letter-spacing: 2px;
        i {
          margin-right: 1rem;
        }
        a {
          color: rgba($color: white, $alpha: .8);
          text-decoration: none;
        }
        a:hover {
          animation: a-hover 1.5s infinite;
        }
      }
    }
    address {
      color: white;
      text-align: right;
      margin-left: .5rem;
      padding-right: 10px;
      font-style: normal;
      h1 {
        font-size: 42px;
        margin-top: 4.5rem;
        margin-bottom: .2rem;
        letter-spacing: 7px;
      }
      h2 {
        font-size: 16px;
        letter-spacing: 2px;
        margin-top: .2rem;
      }
    }
  }
}
@media (max-width: 800px) {
  header {
    background: #343434;
    padding: 25px;
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
    figure {
      padding: 0 20px 0 20px;
      display: none;
      img {
        width: 130px;
        height: auto;
        transition: all 1s;
        box-shadow: 2px 5px 10px 5px rgba($color: black, $alpha: .2);
      }
    }
    ul {
      padding: 0 20px;
      padding-inline-start: 0px;
      text-align: left;
      color: white;
      li {
        font-size: 16px;
        font-weight: 100;
        list-style-type: none;
        margin-top: .5rem;
        letter-spacing: 2px;
        i {
          margin-right: 1rem;
        }
        a {
          color: rgba($color: white, $alpha: .8);
          text-decoration: none;
        }
        a:hover {
          animation: a-hover 1.5s infinite;
        }
      }
    }
    address {
      color: white;
      font-style: normal;
      h1 {
        margin-top: .3rem;
        font-weight: 100;
        font-size: 72px;
        margin-bottom: .2rem;
        letter-spacing: 7px;
      }
      h2 {
        font-size: 24px;
        letter-spacing: 2px;
        font-weight: 100;
        margin-top: .2rem;
        margin-bottom: .2rem;
      }
    }
  }
}
@keyframes a-hover {
50%{
  transform:scale(0.99);
  filter:brightness(60%)
  }
100%{
  transform:scale(1);
  filter:brightness(100%)
  }
}
</style>
