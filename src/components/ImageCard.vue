<template>
  <div>
      <responsive-image :image="image" :defaultImg="defaultImg"/>
      <slide-image :img="img"/>
      <space/>
  </div>
</template>

<script>
import ResponsiveImage from '@/components/ResponsiveImage'
import SlideImage from '@/components/SlideImage'
import Space from './utilities/Space.vue'
export default {
    components: {
        ResponsiveImage,
        SlideImage,
        Space
    },
    data(){
        return {
            image:
            [ 
                {
                    minWidth:'960px',
                    src: '1100x550.png'
                },
                {
                    minWidth:'480px',
                    src: '800x250.png'
                }
            ],
            defaultImg : {
                src: require('@/assets/images/400x250.png')

            },
            img: {
                src:require('@/assets/images/image-1.jpg')
            }
        }
    }
}
</script>

<style>

</style>