<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <!-- <h1>{{ header }}</h1>
      <p>{{ text }}</p> -->
      <slot></slot>
      <div class="action">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  margin: 100px auto;
  padding: 20px;
  background: #fff;
  border-radius: 10px;
}

.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.sale {
  background: rgb(209, 104, 122);
  color: #fff;
}
</style>
