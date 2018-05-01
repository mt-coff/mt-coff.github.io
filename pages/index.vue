<template lang="pug">
  section.main
    introduction

    div.left
      icon

      link-group
</template>

<script>
export default {
  components: {
    'link-group': require("~/components/linkGroup.vue").default,
    'icon': require("~/components/icon.vue").default,
    'introduction': require("~/components/introduction.vue").default
  }
}
</script>

<style lang="sass">
  .main
    min-height: 100%
    display: flex
    flex-direction: row-reverse
    flex-wrap: wrap-reverse
    justify-content: space-around
    align-items: center
    background-color: #242424

  .left
    display: flex
    margin: 0 auto
    flex-direction: column
    align-items: center
    justify-content: space-around

  .link-group
    width: 20rem
    background-color: #fff
    box-shadow: 0 0 4px 1px #232323
    opacity: 0
    animation: fade-in 2.0s linear 1.5s forwards

  .introduction
    width: 60%
    min-height: 300px
    margin: 0.5rem auto
    box-shadow: 0 4px 5px 2px #242424

  @keyframes slidein-links
    to
      transform: translateY(0)

  .icon
    margin: 2.0rem auto
    opacity: 0
    animation: fade-in 2.0s linear 1.5s forwards

  @keyframes fade-in
    to
      opacity: 1
</style>
