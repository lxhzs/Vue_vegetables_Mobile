<template>
  <div class="myset" style="background:#fff; height:100vh">
      <ul class="list">
          <li>
              <p>关于我们</p>
              <!-- <img src="../image/right_tip.png"> -->
          </li>
          <li>
              <p>{{company_intro}}</p>
          </li>
          <!-- <li>
              <p>答案</p>
              <img src="../image/right_tip.png">
          </li> -->
      </ul>
      <!-- <div class="exit">退出登录</div> -->
  </div>
</template>

<script>
import $ from '../common';
export default {
  name: 'about_us',
  data () {
    return {
      company_intro:''
    }    
  },
  metaInfo: {
    title: '关于我们'
  },
  mounted: function() {
    this.getIntroduce()
  },
  computed: {

  },
  methods:{
     getIntroduce () {
        var self = this;
        $.ajax({
          url: '/api/v1/common/introduce',
          success: function (res) {
            self.company_intro=res.data.company_intro
          }
        })
      }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .list li{
      padding-left: .4rem;
      padding-right: .3rem;
      height: .88rem;
      line-height: .88rem;
      display: flex;
      justify-content: space-between;

      border-bottom: 1px solid #E5E5E5;
    }
    .list li p{
      font-size: .34rem;
      color: #000000;
    }
    .list li img{
      margin-top: .3rem;
      margin-left: .3rem;
      width:.16rem;
      height: .26rem;
    }
    .exit{
      margin:0 auto;
      margin-top: 2.68rem;
      width: 6.7rem;
      height: .94rem;
      line-height: .94rem;
      text-align: center;
      border-radius: .1rem;
      font-size: .34rem;
      color: #fff;
      background: #bde8c7
    }
    iframe{
      margin:0 auto;
      width: 6.86rem;
      height: 9.53rem;
    }
</style>
