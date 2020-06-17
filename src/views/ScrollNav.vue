<template>
  <div class="scroll-nav-container">
    <h1>This is an about ScrollNav</h1>
  </div>
</template>

<script lang='ts'>
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class ScrollNav extends Vue {
 @Prop() private msg!: string;



}

</script>


<style scoped>

  

</style>