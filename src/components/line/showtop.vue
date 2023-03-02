<template>
  <div class="NavTop">
    <div>
          
        </div>
        <div>
          {{Text}}
        </div>
        <div>
  
        </div>
  </div>
</template>

<script>
export default {
    props:['Text'],
  methods: {
    onClickLeft() {
      Toast('返回');
    },
    onClickRight() {
      Toast('按钮');
    }
  }
}
</script>

<style scoped lang="less">
.NavTop{
    height: 15vw;
    background-color: #88c9f5a9;
    display: flex;
    width: 100%;
   
    div{
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 5vw; 
        font-weight: 500;
        width: 100%;
        color: #425b6c;
    }
   
}

</style>