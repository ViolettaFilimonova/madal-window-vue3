<template>
  <div class="backdrop" @click.self="closeModel">
    <div class="modal" :class="{sale: theme === 'sale'}">
      <slot>default content</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    props: ['theme'],
    methods: {
      closeModel(){
        this.$emit('close')
      },
      closeModel2(){
        this.$emit('close')
      }
    }
  }
</script>

<style >
.modal{
  width: 460px;
  padding: 40px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.modal h1{
  color: aqua;
  border-bottom: none;
  padding-bottom: 30px;
}
.backdrop{
  top: 0;
  position: fixed;
  background: rgba(0,0,0,0.5);
  width: 100%;
  height: 100%;
}

.modal .sale h1{
  color: white;
}
.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: #333;
}
.modal .actions a{
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.sale  {
  background: crimson;
  color: white;
}
.sale .actions{
  color: white;
}
.sale .actions a{
  color: white;
}
.sale h1{
  color: white;
}

</style>