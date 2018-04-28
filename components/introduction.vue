<template lang="pug">
  section.introduction
    span.btn.close
    span.btn.minimize
    span.btn.open

    p.cmd
      span.line1 >
      span.whoami whoami
        span.cursor1 _

    p.result
      span.whoami mt_coff

    p.cmd
      span.line2 >
      span.like like
        span.cursor2 _

    p.result
      span.like {{ likes }}

    p.cmd
      span.line3 >
        span.cursor3 _
</template>

<script>
  export default {
    name: 'introduction',

    data () {
      return {
        likes: ["coffee", "Game", "Vue.js", "Vim"]
      }
    }
  }
</script>

<style lang="sass" scoped>
  @mixin typing-animation($duration: 5s, $steps: 5, $delay: 0s)
    animation: typing $duration steps($steps, end) $delay forwards

    @keyframes typing
      0%
        width: 0
      100%
        width: 5em

  @mixin command()
    display: inline-block
    vertical-align: middle
    white-space: nowrap
    overflow: hidden

  @mixin blink($end: 1s, $mode: infinite)
    animation: blink 0.5s $end 4 $mode

    @keyframes blink
      0%
        opacity: 0
      20%
        opacity: 0
      50%
        opacity: 1
      80%
        opacity: 1
      100%
        opacity: 0

  @mixin show($delay: 0s)
    animation: show 0s linear $delay forwards

    @keyframes show
      100%
        opacity: 1

  p, span
    color: #242424

  .introduction
    border-top: 20px solid #c7cbd3
    border-radius: 8px
    background-color: #fff
    font-family: monospace
    padding: 0.5rem 1rem
    color: #fff
    position: relative

  .btn
    position: absolute
    top: -16px
    height: 0.8rem
    width: 0.8rem
    border-radius: 50%

  .close
    left: 8px
    background-color: red

  .minimize
    left: 28px
    background-color: orange

  .open
    left: 48px
    background-color: green

  .cmd
    .whoami
      width: 0em
      @include typing-animation(1.5s, 6, 0s)
      @include command

    .like
      width: 0em
      @include command
      @include typing-animation(1.0s, 6, 2.4s)

  .cursor1
    @include blink(0.1s, forwards)

  .cursor2
    @include blink(1.6s, forwards)

  .cursor3
    animation: blink 0.5s infinite

    @keyframes blink
      0%
        opacity: 0
      20%
        opacity: 0
      50%
        opacity: 1
      80%
        opacity: 1
      100%
        opacity: 0

  .result
    .whoami
      opacity: 0
      @include show(1.8s)

    .like
      opacity: 0
      @include show(3.4s)

  .line2
    opacity: 0
    @include show(1.6s)

  .line3
    opacity: 0
    @include show(3.4s)
</style>
