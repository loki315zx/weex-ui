<!-- CopyRight (C) 2017-2022 Alibaba Group Holding Limited. -->
<template>
  <div class="wxc-demo">
    <scroller class="scroller">
      <title title="wxc-rich-text"></title>
      <category title="使用案例"></category>
      <div class="wrapper">
        <div class="type-container">
          <text class="type-text">Weex富文本混排方案：</text>
          <wxc-rich-text class="special-rich"
                         :config-list="configList"
                         v-on:wxcRichTextLinkClick="wxcRichTextLinkClick"></wxc-rich-text>
        </div>

        <div class="type-container">
          <text class="type-text">纯字符串兼容：</text>
          <wxc-rich-text class="special-rich"
                         :config-list="configString"></wxc-rich-text>
        </div>

        <div class="type-container">
          <text class="type-text">特殊富文本组件：(tag+2行文字)</text>
          <wxc-special-rich-text class="special-rich"
                                 :config-list="specialConfigList"></wxc-special-rich-text>
        </div>

        <div class="type-container">
          <text class="type-text">特殊富文本组件：(icon+2行文字)</text>
          <wxc-special-rich-text class="special-rich"
                                 :config-list="specialConfigList1"></wxc-special-rich-text>
        </div>
      </div>
    </scroller>
  </div>

</template>

<style scoped>
  .wxc-demo {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: #FFFFFF;
  }

  .scroller {
    flex: 1;
  }

  .wrapper {
    padding: 30px;
    padding-top: 10px;
  }

  .type-container {
    margin-bottom: 70px;
    margin-top: 20px;
  }

  .type-text {
    font-size: 28px;
  }

  .special-rich {
    margin-top: 14px;
  }
</style>
<script>
  import Title from '../_mods/title.vue';
  import Category from '../_mods/category.vue';
  import { WxcRichText, WxcSpecialRichText } from '../../index';
  import { setTitle } from '../_mods/set-nav';

  module.exports = {
    components: { Title, Category, WxcRichText, WxcSpecialRichText },
    data: () => ({
      configList: [{
        type: 'icon',
        src: '//gw.alicdn.com/tfs/TB1RRVWQXXXXXasXpXXXXXXXXXX-24-22.png',
        style: {
          width: 24,
          height: 22
        }
      }, {
        type: 'text',
        value: '黄色主题',
        theme: 'yellow'
      }, {
        type: 'link',
        value: '自定义颜色link',
        href: '//h5.m.taobao.com',
        style: {
          color: '#546E7A'
        }
      }, {
        type: 'icon',
        src: '//gw.alicdn.com/tfs/TB1qygJRXXXXXX2XFXXXXXXXXXX-117-37.png'
      }, {
        type: 'tag',
        value: '满100减20',
        theme: 'red'
      }, {
        type: 'tag',
        value: '自定义标签',
        style: {
          fontSize: 26,
          color: '#ffffff',
          borderColor: '#3d3d3d',
          backgroundColor: '#546E7A',
          height: 40
        }
      }],
      configString: '不小心传入了字符串不小心传入了字符串不小心传入了字符串不小心传入了字符串不小心传入了字符串',
      specialConfigList: [
        {
          type: 'tag',
          value: '自由行',
          style: {
            width: 84,
            fontSize: 24,
            color: '#3D3D3D',
            borderColor: '#FFC900',
            backgroundColor: '#FFC900',
            height: 28,
            borderRadius: 14
          }
        },
        {
          type: 'text',
          value: '春秋旅游广州-泰国曼谷6天往返单机票自由行自由春秋旅游广州-泰国曼谷6天往返单机票自由行自由行…',
          theme: 'black',
          style: {
            fontSize: 28
          }
        }
      ],
      specialConfigList1: [
        {
          type: 'icon',
          src: '//gw.alicdn.com/tfs/TB1RRVWQXXXXXasXpXXXXXXXXXX-24-22.png',
          style: {
            width: 24,
            height: 22
          }
        },
        {
          type: 'text',
          value: '首先我很满意酒店，很整洁，早上的自助餐也很丰富，游泳池也不错，其次，租车公司也很赞，这次旅行非常的完美...',
          theme: 'black'
        }
      ]
    }),
    created () {
      setTitle('RichText');
    },
    methods: {
      wxcRichTextLinkClick () {

      }
    }
  };
</script>
