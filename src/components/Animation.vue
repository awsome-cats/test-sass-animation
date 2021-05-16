<template>
    <div>
      <div class="anime-container">
        <div class="rect-wrapper">
          <div class="rect"></div>
          <div class="rect"></div>
          <div class="rect"></div>
        </div>
        <space/>
        <double-spiner/>
        <space/>
        <rect-spinner/>
        </div>
        <space/>
        <Menu/>
        <string-animation/>
    </div> 
</template>

<script>
import DoubleSpiner from '@/components/DoubleSpiner'
import Space from './utilities/Space.vue'
import RectSpinner from '@/components/RectSpinner'
import Menu from './menu/Menu.vue'
import StringAnimation from './StringAnimation.vue'
export default {
  components: {
    DoubleSpiner,
    Space,
    RectSpinner,
    Menu,
    StringAnimation
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/animation.scss';

.rect-wrapper {
  display: flex;
  justify-content: center;
}

.anime-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.rect {
  background-color: $cOrange;
  width:18px;
  height: 18px;
  margin:8px;
  @include animation(
    $name: xyround-rect,
    $duration:1.2s,
    $delay:0s,
    $iteration-count:infinite,
    $timing-function:ease,
    $direction:normal
  )
}


@keyframes xyround-rect {
  0% {
    transform: perspective(120px) rotateX(0deg) rotateY(0deg);
  }
  50% {
    transform: perspective(120px) rotateX(-180deg) rotateY(0deg);
  }
  
  100% {
    transform: perspective(120px) rotateX(-180deg) rotateY(-180deg);
  }

}

</style>
