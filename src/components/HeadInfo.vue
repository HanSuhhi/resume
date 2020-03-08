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
header {
  background: #343434;
  padding: 5px 38px;
  display: flex;
  figure {
    padding: 0 5px 0 5px;
    float: left;
    img {
      width: 100px;
      height: auto;
      margin-top: 15%;
      transition: all 1s;
      box-shadow: 2px 5px 10px 5px rgba($color: black, $alpha: .2);
    }
    img:hover {
      transform: scale(1.03);
    }
  }
  @media (max-width: 580px) {
    figure {
      display: none;
    }
  }
  ul {
    float: left;
    text-align: left;
    padding: 0 10px;
    padding-inline-start: 0px;
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
  @media screen and (min-width: 1200px) {
    ul {
      float: left;
      text-align: left;
      padding: 0 10px;
      padding-inline-start: 0px;
      color: white;
      margin-right: 22%;
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
  }
  @media screen and (min-width: 768px) {
    ul {
      float: left;
      text-align: left;
      padding: 0 10px;
      padding-inline-start: 0px;
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
  }
  @media screen and (min-width: 992px) {
    ul {
      float: left;
      text-align: left;
      padding: 0 10px;
      padding-inline-start: 0px;
      color: white;
      margin-right: 20%;
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
  }
  address {
    color: white;
    font-style: normal;
    float: right;
    text-align: right;
    margin-right: .2rem;
    h1 {
      width: 120%;
      font-size: 62px;
      margin-top: 3rem;
      margin-bottom: .2rem;
      letter-spacing: 7px;
      position: relative;
      right: 1rem;
    }
    h2 {
      font-size: 24px;
      letter-spacing: 2px;
      margin-top: .2rem;
    }
  }
  @media screen and (max-width: 768px) {
    address {
      margin-right: .2rem;
      color: white;
      font-style: normal;
      float: right;
      text-align: right;
      h1 {
        width: 140%;
        font-size: 32px;
        margin-top: 5rem;
        margin-bottom: .2rem;
        letter-spacing: 7px;
        position: relative;
        right: .5rem;
      }
      h2 {
        font-size: 14px;
        letter-spacing: 2px;
        margin-top: .4rem;
      }
    }
  }
}
@media (max-width: 580px) {
  header {
    background: #343434;
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    text-align: center;
    ul {
      float: left;
      text-align: left;
      padding-inline-start: 0px;
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
      width: 100%;
      text-align: center;
      h1 {
        width: 100%;
        font-size: 62px;
        margin-top: 2.5rem;
        margin-bottom: .2rem;
        letter-spacing: 7px;
      }
      h2 {
        font-size: 24px;
        letter-spacing: 2px;
        margin-top: .2rem;
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
