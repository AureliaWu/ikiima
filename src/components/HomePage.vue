<template>
<div>
  <div>
  <Menu mode="horizontal" active-name="home" style="position: absolute;background-color: rgba(0,0,0,0)" >
        <MenuItem name="home">
            <Icon type="ios-paper" />
           主页
        </MenuItem>
        <Submenu name="news">
          <template slot="title">
            <Icon type="ios-people" />
                  最新新闻
          </template>
           <MenuItem name="news-1">吉冈圣惠</MenuItem>
           <MenuItem name="news-2">水野良树</MenuItem>
           <MenuItem name="news-3">山下穗尊</MenuItem>
           <MenuItem name="news-4">生物股长</MenuItem>
           <MenuItem name="news-5">姨妈生产队</MenuItem>
        </Submenu>      
        <Submenu name="collections">
            <template slot="title">
                <Icon type="ios-stats" />
                作品集
            </template>
            <MenuGroup title="演唱会">
                <MenuItem name="3-1">2016（十周年）</MenuItem>
                <MenuItem name="3-2">2015</MenuItem>
                <MenuItem name="3-3">2013</MenuItem>
            </MenuGroup>
            <MenuGroup title="番组">
                <MenuItem name="3-4">Music Station</MenuItem>
                <MenuItem name="3-5">红白歌会</MenuItem>
            </MenuGroup>
        </Submenu>
        <MenuItem name="resource">
            <Icon type="ios-color-wand" />
          资源站          
        </MenuItem>
        <MenuItem name="about">
            <Icon type="ios-happy-outline" />
          关于我们
        </MenuItem>
    </Menu>
    <div class="logo">
      <img src="../assets/ikiimaLogo.png" class="logo">
    </div>
    </div>
    <Carousel :autoplay-speed="setting.autoplaySpeed" autoplay v-model="value2" loop>
        <CarouselItem v-for="item in pictures">
             <img :src="item.address" class="rollingPic">
        </CarouselItem>     
    </Carousel>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data () {
    return {
    value2: 0,
    pictures: [
      {address: require("../assets/houboku.jpg")},
      {address: require("../assets/fc20180821.jpg")},
      {address: require("../assets/ins20180822.jpg")},
      {address: require("../assets/ins20180826.jpg")},
      {address: require("../assets/ins20180830.jpg")},
    ],
    setting: {
      autoplaySpeed: 3000,
      dots: 'inside'
    }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.rollingPic {
  width:100%;
  height:100%;
  min-width: 1000px;
  z-index:-10;
  zoom: 1;
  background-color: #fff;
  background-repeat: no-repeat;
  background-size: cover;
  -webkit-background-size: cover;
  -o-background-size: cover;
  background-position: center 0;
}
.logo {
  position: absolute;
  right: 25px;
  top: 5px;
  z-index: 1;
  height: 60px;
}
</style>
