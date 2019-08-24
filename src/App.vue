<template>
  <div class="home">
    <div class="bar">
      <span :class="{'active': layout == 'grid'}" @click="layout = 'grid'">one</span>
      <span :class="{'active': layout == 'list'}" @click="layout = 'list'">two</span>
    </div>
    <!-- 第一种样式 -->
    <ul v-if="layout == 'grid'" class="grid">
      <li v-for="(item,index) in article" :key="index">
        <img :src="item.url" alt="">
        <p>{{item.title}}</p>
      </li>
    </ul>
    <!-- 第一种样式 -->
    <ul v-if="layout == 'list'" class="list">
      <li v-for="(item,index) in article" :key="index">
        <img :src="item.url" alt="">
        <p>{{item.title}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: "home",
  components: {},
  data() {
    return {
      layout: "grid",
      article: [
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "What You Need To Know About CSS Variables"
        },
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "Freebie: 4 Great Looking Pricing Tables"
        },
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "Creating Your First Desktop App With HTML, JS and Electron"
        },
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "Learn SQL In 20 Minutes"
        },
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "Quick Tip: The Easiest Way To Make Responsive Headers"
        },
        {
          url:
            "http://img5.imgtn.bdimg.com/it/u=4278174810,3297227253&fm=26&gp=0.jpg",
          title: "20 Interesting JavaScript and CSS Libraries for February 2016"
        }
      ]
    };
  },
  methods: {}
};
</script>

<style lang="less" scoped>
.home {
  margin: auto;
  width: 50%;
  .active {
    color: orange;
  }
  .bar {
    display: flex;
    justify-content: flex-end;
    background-color: green;
    span {
      margin-right: 10px;
      cursor: pointer;
    }
  }
  ul.grid {
    list-style: none;
    width: 100%;
    border: 1px solid #ccc;
    display: flex;
    flex-wrap: wrap;
    padding: 0;
    li {
      width: 50%;
      border: 1px solid #ccc;
      box-sizing: border-box;
      padding: 5px 0;
      img {
        width: 200px;
        height: 120px;
      }
    }
  }
  ul.list {
    list-style: none;
    width: 100%;
    border: 1px solid #ccc;
    padding: 0;
    overflow: hidden;
    li {
      width: 100%;
      display: flex;
      align-items: center;
      border-bottom: 1px solid #ccc;
      padding: 5px;
      img {
        width: 200px;
        height: 120px;
      }
      p {
        flex: 1;
      }
    }
  }
}
</style>
