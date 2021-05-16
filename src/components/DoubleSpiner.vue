<template>
  <div class="double-spinner">
    <div></div>
    <div></div>
  </div>
</template>

<script>
export default {
name:'DoubleSpiner'
}
</script>s

<style lang="scss" scoped>
@import '@/assets/style/animation.scss';

.double-spinner {
  // margin-top:150px;
  margin:0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  width:30px;
  height: 30px;
  & > div {
    opacity: .6;
    width:100%;
    height: 100%;
    border-radius: 50%;
    position: absolute;
    background-color: $cGray;
    @include animation(
      $name: bigger-spinner,
      $iteration-count:infinite,
      $timing-function: ease-in-out,
      $duration: 2s
    );

    &:nth-child(2) {
    background-color: black;
    animation-delay: -1s;
   } 
  
  }
  
}

@keyframes bigger-spinner {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1);
    
  }
  100% {
    transform: scale(0);

  }
}

</style>