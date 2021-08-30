<template>
  <div>
    <div class="area-border">
      {{ text }}
    </div>
  </div>
</template>

<script>
  export default {
    props:['text']
  }
</script>

<style>
area-border:{
  border: 1px soild white;
}
</style>