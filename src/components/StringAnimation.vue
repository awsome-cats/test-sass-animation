<template>
  <div id="container">
      <div class="animate-title" :class="{'inview': hasInview}">
          <span class="char">A</span>
          <span class="char">N</span>
          <span class="char">I</span>
          <span class="char">M</span>
          <span class="char">A</span>
          <span class="char">T</span>
          <span class="char">I</span>
          <span class="char">O</span>
          <span class="char">N</span>
      </div>
      <button @click="onClick">Animation</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            hasInview: false
        }
    },
    methods: {
        onClick() {
            this.hasInview = !this.hasInview
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/animation.scss';


#container {
    font-family: 'Roboto', sans-serif;
    font-size: 20px;

    position: relative;
    height: 25vh;
    background-color: teal;

    & > button {
        position: absolute;
        top:20px;
        left:50px;
        //transform: translateY(50%);
    } 
    
    .animate-title {
        position: absolute;
        top:50%;
        left:50%;
        transform: translate(-50%, -50%);
        color:white;
        opacity: 0;

        &.inview {
            opacity: 1;
            & .char {
                // inline-blockがないとtransformが当たらない(spanタグ)
                display: inline-block;
                @include animation(
                    $name: kf-animate-chars,
                    $duration:0.5s,
                    $timing-function: cubic-bezier(0.39, 1.57, 0.58, 1),
                    $fill-mode: both
                );

                @for $i from 1 through 9 {
                    &:nth-child(#{$i}) {
                        animation-delay: $i * 0.04s;
                    }
                }

            }
        }
    }
}

@keyframes kf-animate-chars {
    0% {
        opacity: 0;
        transform: translateY(-50%);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}




</style>