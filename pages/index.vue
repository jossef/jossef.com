<template>
    <div class="app">
        <div class="title">
            👋
        </div>
        <a target="_blank" href="https://github.com/jossef">GitHub</a>
        <a target="_blank" href="https://www.linkedin.com/in/jossef">LinkedIn</a>
        <a target="_blank" href="https://www.youtube.com/@jossef12">Youtube</a>
        <a target="_blank" href="https://stackoverflow.com/users/3191896">Stackoverflow</a>
        <a target="_blank" href="https://medium.com/@jossef">Medium</a>
    </div>
</template>

<script>
import {ref, computed, onMounted, onBeforeUnmount} from 'vue';

export default {
    name: 'IndexPage',
    components: {},
    setup() {
        const selectedItem = ref(null)

        onMounted(() => {

        })

        return {
            selectedItem,
        }
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');

$color-background: #fff;
$padding: 8px;

$breakpoint-mobile-small: 360px;
$breakpoint-mobile: 800px;
$breakpoint-tablet-portrait: 1020px;
$breakpoint-tablet-landscape: 1280px;
$breakpoint-small-laptop: 1366px;
$breakpoint-laptop: 1440px;
$container-max-width: 1130px;

$main-background-color: #feffed;
* {
  box-sizing: border-box;
}

@mixin defuse-links($color, $text-decoration: none) {
  text-decoration: $text-decoration;
  color: $color;

  &:active, &:visited, &:link, &:hover {
    color: $color;
  }
}

@mixin responsive($breakpoint) {
  @media (max-width: $breakpoint) {
    @content
  };
}

@mixin container() {
  display: flex;
  flex-direction: column;
  align-items: center;

  padding-left: $padding*4;
  padding-right: $padding*4;
  @include responsive($breakpoint-mobile) {
    padding-left: $padding*2;
    padding-right: $padding*2;
  }

  &__content {
    max-width: $container-max-width;
    display: flex;
    flex-direction: column;
    width: 100%;

    @content
  }
}


html, body {
  padding: 0;
  margin: 0;
  background: $main-background-color;
  font-family: 'Roboto', sans-serif;
  font-size: 14px;
}

a {
  @include defuse-links(#000, underline);

}

.app {
  @include container() {
    background: $color-background;
    min-height: 100vh;
    color: #000;
  }


  .title {
    padding-top: $padding*4;
    font-size: 30px;
    font-weight: 700;
    margin-bottom: 16px;
  }
}

</style>
