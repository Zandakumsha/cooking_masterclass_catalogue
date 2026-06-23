<template>
  <div class="card">

    <img :src="course.image" :alt="course.title" class="course-image" />

    <div v-if="!course.available" class="sold-out">
      SOLD OUT
    </div>

    <h2>{{ course.title }}</h2>

    <p>
      <strong>Chef:</strong>
      {{ course.chef }}
    </p>

    <p>
      <strong>Level:</strong>
      {{ course.level }}
    </p>

    <p class="price">
      R{{ course.price }}
    </p>

    <button @click="saveCourse" :disabled="!course.available">
      Save to Wishlist
    </button>

  </div>
</template>

<script>
export default {
  props: ["course"],

  methods: {
    saveCourse() {
      this.$emit("save-course");
    }
  }
};
</script>

<style scoped>
.card {
  background: white;
  border-radius: 12px;
  padding: 20px;

  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);

  position: relative;
}

.card h2 {
  margin-bottom: 10px;
  color: #2c7008;
}

.price {
  margin: 15px 0;
  font-size: 22px;
  font-weight: bold;
}

button {
  width: 100%;
  padding: 12px;

  background: #04560b;
  color: white;

  border: none;
  border-radius: 8px;

  cursor: pointer;
}

button:hover {
  background: #2c7008;
}

button:disabled {
  background: gray;
  cursor: not-allowed;
}

.sold-out {
  position: absolute;
  top: 10px;
  right: 10px;

  background: rgb(193, 7, 7);
  color: white;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 12px;
}

.course-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 15px;
}
</style>