<template>
  <div class="hello">
    <div>Hello</div>
    <i>{{notice}}</i>
  </div>
</template>

<script>
export default {
  name: 'Hello',
  data() {
    return {
      sure: false,
      notice: `Can't level`,
    }
  },
  beforeRouteLeave (to, from, next) {
    if (this.sure) return next();
    this.sure = true;
    this.notice = 'Just bye';
    next(false);
  }
}
</script>

<style>
.hello {
  background: yellow;
}
</style>
