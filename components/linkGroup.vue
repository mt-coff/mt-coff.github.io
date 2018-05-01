<template lang="pug">
  section.link-group
    a.fa.fa-github(href="https://github.com/mt-coff" target="blank")

    a.fa.fa-edit(href="http://mt-coff.hatenablog.com/" target="blank")

    a.fa.fa-twitter(href="https://twitter.com/mt_coff" target="blank")
</template>

<script>
  export default{
    name: 'link-group'
  }
</script>

<style lang="sass" scoped>
  .link-group
    border: solid 1px black
    border-radius: 16px
    text-align: center
    display: flex
    justify-content: space-around

  a
    text-decoration: none
    color: inherit

  .fa
    border: solid 4px transparent
    font-size: 2.5rem
    line-height: middle

    &:hover
      color: #4156e3
      border-bottom: solid 4px #4156e3
</style>
