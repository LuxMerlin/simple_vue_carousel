<template>
  <div class="carousel">
      <slot></slot>
      <button @click="next" class="carousel_button next"><span class="iconify" data-icon="ant-design:arrow-right-outlined" style="color: #f3f6f4;" data-width="40" data-height="40"></span></button>
      <button @click="prev" class="carousel_button prev"><span class="iconify" data-icon="ant-design:arrow-left-outlined" style="color: #f3f6f4;" data-width="40" data-height="40"></span></button>
  </div>
</template>

<script>
export default {
    name: 'Carousel',
    methods: {
        next(){
            this.$emit('next')
        },
        prev(){
            this.$emit('prev')
        }
    }
}
</script>

<style>
    .carousel{
        position: relative;
        width: 600px;
        height: 350px;
        overflow: hidden;
    }

    .carousel_button {
        position: absolute;
        height: 40px;
        width: 50px;
        top: calc(50% - 20px);
        background-color: rgba(0,0,0,0.3);
        border: none;
    }

    .carousel_button:focus , .carousel_button:hover{
        outline: none;
        cursor: pointer;
    }

    .next{
        right: 0;
    }

    .prev{
        left: 0;
    }


</style>