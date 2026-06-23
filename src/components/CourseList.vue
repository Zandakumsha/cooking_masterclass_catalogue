<template>
  <div class="course-container">
    <div class="course-card" v-for="course in courses" :key="course.id">
      <h2>{{ course.title }}</h2>
      <p>{{ course.description }}</p>
      <p>Instructor: {{ course.instructor }}</p>
      <p>Price: R{{ course.price }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      courses: [
        {
          id: 1,
          title: "Vue.js Fundamentals",
          description: "Learn the basics of Vue.js",
          instructor: "Jane Doe",
          price: 999,
        },
        {
          id: 2,
          title: "Advanced JavaScript",
          description: "Master modern JavaScript concepts",
          instructor: "John Doe",
          price: 1299
        }
      ]
    };
  }
};
</script>