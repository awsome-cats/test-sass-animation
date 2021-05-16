<template>
  <div id="container">
      <div class="cover-slide inview hover-darken">
          <img :src="img.src" alt="" class="img-zoom">
      </div>
  </div>
</template>

<script>
export default {
    props: {
      img: {
          type:Object,
          required: true
      }
    },
}
</script>

<style lang="scss">
@import '@/assets/style/animation.scss';

img {
    max-width: 100%;
    //余白がとれつ
    vertical-align:bottom;
}

.img-zoom {
    opacity: 0;
    
    .inview & {
        opacity: 1;
        transition: transform 0.3s ease;
        @include animation(
            $name: kf-image-show,
            $duration:1.6s,
            $timing-function:ease-in-out,
            $fill-mode: none
        );
        &:hover {
            transform: scale(1.3);

        }
    }
}

.hover-darken {
    &::before {
        content: '';
        position: absolute;
        top:0;
        left:0;
        width:100%;
        height: 100%;
        z-index:1;
        transition: background-color 0.3s ease;
        pointer-events: none;

        @include animation(
            $name: kf-image-show,
            $duration:1.6s,
            $timing-function:ease-in-out,
            $fill-mode: none
        );
    }
    &:hover::before {
        background-color: rgba(0,0,0,0.4);
    }
}

// positionで要素のサイズを決めることもできる
.cover-slide {
    position: relative;
    overflow: hidden;
    &::after {
        content: '';
        position: absolute;
        z-index:2;
        top:0;
        left:0;
        right:0;
        bottom: 0;
        background-color: #ccc;
       
    }
    &.inview {
        &::after {
            @include animation(
            $name:kf-cover-slide,
            $duration:1.4s,
            $timing-function:ease-in-out
            
          );
        }
    }
}

@keyframes kf-cover-slide {
    0% {
        left:0;
        right:100%;
    }
    50% {
        left:0;
        right:0;
    }
    100% {
        left:100%;
        right:0%;
    }
}

@keyframes kf-image-show {
    0% {
        opacity: 0;
        
    }
    50% {
        opacity: 0;
       
    }
    50.1% {
        opacity: 1;
        transform: scale(1.5);
    }
    100% {
        opacity: 1;
    }
}

</style>