<template>
  <div class="body" :class="{'menu-open': hasMenuOpen}">
      <button class="mobile-menu-icon" @click="onClick" >
          <span></span>
          <span></span>
          <span></span>
      </button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            
            hasMenuOpen: false
        }
    },
    methods: {
        onClick() {
            // クリックによってセレクターを脱着する
            this.hasMenuOpen = !this.hasMenuOpen
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/style/animation.scss';

*{
    margin:0;
    padding:0;
}
.mobile-menu-icon {
    //透明
    background-color: transparent;
    border:none;
    outline: none !important;
    cursor: pointer;
    & > span {
        background-color: $cblack;
        width:35px;
        height: 2px;
        display: block;
        margin-bottom: 9px;
        transition: transform 0.7s;

        &:last-child {
            margin-bottom: 0;
        }
    }
}

.body {
    width:100%;
    height: 20vh;
}
.menu-open {
    background-color: $cblack;

    .mobile-menu-icon {

        & > span {
            background-color: white;

            &:nth-child(1) {
                transform: translateY(11px) rotate(135deg);
            }
            &:nth-child(2) {
                transform: translateX(-18px) scaleX(0);
            }
            &:nth-child(3) {
                transform: translateY(-11px) rotate(-135deg);
            }
        }
    }
}
</style>