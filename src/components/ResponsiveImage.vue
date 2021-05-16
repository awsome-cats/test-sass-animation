<template>
  <div>
      <h3>レスポンス画像</h3>
      <div style="height:500px;">
          <picture>
              <source v-for="(img,i) in image" :key="i" :media="`(min-width:${img.minWidth})`" :srcset="require(`@/assets/images/${img.src}`)" />
              <img :src="defaultImg.src" alt="">
          </picture>
      </div>
  </div>
</template>

<script>
export default {
    props: {
        image: {
            type: Array
        },
        defaultImg: {
            type: Object
        }
    },
    // data() {
    //     return {
    //         img: 
    //             {
    //                 minWidth:'960px',
    //                 src: '1100x550.png'
    //             },
    //         defaultImg : {
    //             src: require('@/assets/images/400x250.png')

    //         }
            
    //     }
    // }
}
</script>

<style lang="scss" scopde>
@import '@/assets/style/animation.scss';
</style>