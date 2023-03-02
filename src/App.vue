<template>
  <nav>
  </nav>
  <router-view/>
</template>

<style lang="less">
    *{
      margin: 0; 
      padding: 0;
      box-sizing: border-box;
      font-family: '微软雅黑';
    }
    .icon {
       width: 0.3rem; height: 0.3rem;
       /* vertical-align: -0.15rem; */
       fill: currentColor;
       overflow: hidden;
    }

    a{
      color: #333;
      text-decoration: none;
    }
.slide-fade{
  position: fixed;left:0;right: 0;
  width: 80%;
  background-color: white;
}
</style>
