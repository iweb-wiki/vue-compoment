<template>
  <div class="demo">
    <h1>This is an about demo</h1>
  </div>
</template>

<script lang='ts'>
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class Demo extends Vue {
 @Prop() private msg!: string;



}

</script>


<style scoped>



</style>