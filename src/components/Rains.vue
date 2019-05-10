<template>
  <div id="str">
    <div id="div1">
      <div id="div2">
        <div class="class1">雅住</div>
        <ul class="class2">
          <li><a href="#">首页</a></li>
          <li><a href="#">逗号公寓</a></li>
          <li><a href="#">青草公寓</a></li>
          <li><a href="#">逗号之家</a></li>
          <li><a href="#">社区生活</a></li>
          <li><a href="#">关于我们</a></li>
        </ul>
        <div class="class3">
          <span><a href="#">登录</a></span>|
          <span><a href="#">注册</a></span>
        </div>
      </div>
      <div id="div3" style="width: 100%">
        <div v-for="item in shuju">
          <a href="#"><img v-bind:src="item.bannerimg" style="width: 100%"/></a>
        </div>
      </div>
      <div id="div4">
        <div class="class4">精选推荐</div>
        <div id="div5">
          <div class="class5"></div>
          <div class="class5"></div>
          <div class="class5"></div>
          <div class="class5"></div>
          <div class="class5"></div>
          <div class="class5"></div>
        </div>
        <div class="class6">热门城市</div>
        <ul class="class6" id="div6">
          <li class="class7"><a href="#">北京</a></li>
          <li class="class7"><a href="#">上海</a></li>
          <li class="class7"><a href="#">广州</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
	export default {
		name: "Rains",
    data(){
		  return{
		    shuju:[]
      }
    },
    methods:{
      GetData(){
        this.$http.get('../../static/getTopBanner.json').then(response => {
          this.shuju = response.data.data;
          console.log(response.data)
        }, response => {
          // error callback
        })
      }
    },
    mounted() {
      this.GetData();
    }
	}
</script>

<style scoped>
  #str{
    width: 100%;
    height: 1900px;
  }
  #div1{
    width: 100%;
    height: 5%;
    margin: auto;
    background: red;
  }
  #div2{
    width: 100%;
    height: 5%;
    background: red;
  }
  .class1{
    width: 20%;
    float: left;
    line-height: 45px;
    margin-left: 5%;
    color: white;
  }
  a{
    text-decoration:none;
    color: white;
  }
  li{
    list-style: none;
  }
  .class2 li{
    margin-left: 2%;
    line-height: 45px;
    float: left;
  }
  .class3{
    margin-left: 5%;
    line-height: 45px;
    float: left;
  }
  #div3{
    width: 100%;
    height: 330px;
    clear:both
  }
  #div4{
    width: 100%;
    height: 500px;
    background: blue;
  }
  .class4{
    width: 100%;
    height: 30px;
    line-height: 30px;
    background: white;
  }
  #div5{
    margin: 0 8.3%;
  }
  .class5{
    width: 280px;
    height: 180px;
    margin: 0 20px 20px 0;
    background: lightgreen;
    float: left;
  }
  .class6{
    clear: both;
    margin-left: -850px;
  }
  .class7{
    float: left;
  }
</style>
