<template>
    <div ref="about" class="about">
        <div class="about-in">
          About
        </div>
    </div>
</template>

<script>
export default {
  created() {
    this.$gsap.set(this.$refs.about, {
      height: '100%'
    })
  },
  transition: {
    name: 'about',
    mode: '',
    beforeEnter(el) {
      if(!el.classList.contains('about')) {
        return
      }
      this.$gsap.set(el, {
        height: 0,
        bottom: 0,
      })
    },
    enter(el, done) {
      if(!el.classList.contains('about')) {
        return
      }
      this.$gsap.to(el, {
        duration: .5,
        height: '100%',
        clearProps: "bottom"
      })
      done()
    },
    beforeLeave(el) {
      if(!el.classList.contains('about')) {
        return
      }
      this.$gsap.set(el, {
        top: 0,
      })
    },
    leave(el, done) {
      if(!el.classList.contains('about')) {
        return
      }
      this.$gsap.to(el, {
        duration: .5,
        top: 0,
        height: 0,
        clearProps: "top"
      })
      setTimeout(() => {
        done()
      }, 500)
    }
  },
}
</script>

<style lang="scss">
  .about {
    position: fixed;
    left: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgb(169, 169, 255);
    &-in {
      width: 100%;
      min-height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow-y: scroll;
    }
  }
</style>