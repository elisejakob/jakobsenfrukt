<template>
  <main class="home">
    <section class="intro">
      <p class="lead"><span class="name">Jakobsen Frukt &amp; Grønt</span> er et hyggelig, lite designstudio i Oslo som spesialiserer seg på digital design og lager glade ting på internett.</p>
    </section>
    <Latest heading="Dette har skjedd i det siste:" />
  </main>
</template>

<script>
import Latest from '@/components/Latest.vue'

export default {
  name: 'home',
  components: {
    Latest
  }
}
</script>

<style lang="scss" scoped>
@import '../css/variables.scss';
main {
  @include fadeAnimation;
}
.intro {
  .lead {
    font-size: 1.8rem;
    margin: 0 auto;
    text-align: center;

    @media (max-width: $sm) {
      font-size: 1.6rem;
    }
  }
}
.name {
  color: $color-green;
}
.day .name {
  color: $color-black;
}
</style>
