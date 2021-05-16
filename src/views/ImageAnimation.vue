<template>
  <div>
       <button @click="onClick" class="btn">クリック</button>
    <div class="appear right" :class="{'inview': hasInview}">
        <!-- <div class="item"><img src="@/assets/images/image-1.jpg" width="200px"></div> -->
        <div v-for="(img, i) in image" :key="i" class="section-img">
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
            <div class="item"><img :src="img.src" alt="画像"></div>
        </div>
    </div>
  </div>
</template>

<script>
export default {

    data() {
        return {
            hasInview: false,
            image: [
                {
                    id: 1,
                    src: require('@/assets/images/image-1.jpg')
                }
            ]
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


</style>