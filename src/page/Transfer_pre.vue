<template>
  <div class="Transfer_pre">
    <BackBar></BackBar>
    <div class="MainBox TextCenter">
      <!-- <Row type="flex" justify="center" class="code-row-bg">
          <Col span="6" style="z-index:999;margin:0 auto 10px auto;"> -->
            <Button type="error" shape="circle" size="large" long @click="GoTransfer">申请</Button>
          <!-- </Col>
      </Row> -->
      <Card :bordered="false" dis-hover>
          <div style="text-align:center">
              <img :src="BgImg">
          </div>
      </Card>
    </div>
  </div> 
</template>
<script>
import Vue from 'vue'
import axios from 'axios'
import BackBar from 'components/BackBar'
  export default{
    data: function () {
      return {
        BgImg:''
      }
    },
    mounted: function () {
      
    },
    created: function () {
      axios.get(R_PRE_URL+'/selectimage.do'
      ).then((res)=> {
        this.BgImg = res.data[0].zzgximage1
      }).catch((error)=> {
        console.log(error)
      })
      
    },
    computed: {
      
    },
    watch: {
      
    },
    components: {
      BackBar

    },
    methods: {
      GoTransfer(){
        this.$router.push({name:'组织关系接转资料填写'})
      }
    }
  }
</script>
<style lang="scss">
.Transfer_pre{
  width: 100%;
  height: 100%;
  .MainBox{
    width: 100%;
    margin: 70px auto;
    img{
      width: 100%;
      height: auto;
    }
    button{
      width: 100px;
      margin: 0 auto;
    }
  }

}
</style>
