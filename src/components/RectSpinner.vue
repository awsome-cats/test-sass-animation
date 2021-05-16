<template>

    <div class="rect-spinner">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </div>
  
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '@/assets/style/animation.scss';

// .rect-spinner {
//     width: 50px;
//     height: 40px;
    
//     letter-spacing: -2px;
//     text-align: center;
//     margin:100px auto;
//     & > div {
//         width: 6px;
//         height: 100%;
//         display: inline-block;
//         background-color: black;
//     }
// }

.rect-spinner {
    width:50px;
    height: 40px;
    text-align: center;
    display: flex;
    justify-content: space-between;

    & > div {

        width:3px;
        height: 100%;
        background-color: black;
        letter-spacing: -2px;
        display: inline-block;
        @include animation(
            $name: rect-bounce,
            $iteration-count:infinite,
            $timing-function:ease-in-out,
            $duration: 1.2s
        );

        @for $i from 1 through 5 {
            &:nth-child(#{$i}) {
                animation-delay: -1.3s + $i * 0.1s;
            }
        }
    }
}

@keyframes rect-bounce {
    0%,
    40%,
    100% {
        transform: scaleY(0.4);
    }

    20% {
        transform: scaleY(1);
    }
    // 100%{
    //     transform: scaleY(0);
    // }
}

</style>