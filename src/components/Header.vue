<template>
  <header class="header">
    <h1>Cooking Masterclass</h1>

    <div class="wishlist">
      Wishlist: {{ wishlistCount }}
    </div>
  </header>
</template>

<script>
export default {
  props: ["wishlistCount"]
};
</script>

<style scoped>
.header {
  background: #0f6a04;
  color: white;
  padding: 20px 30px;

  display: flex;
  justify-content: space-between;
  align-items: center;
}

.wishlist {
  font-size: 18px;
  font-weight: bold;
}
</style>