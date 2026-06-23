<template>
  <div id="app">
    <Header :wishlistCount="wishlistCount" />

    <main class="course-grid">
      <CourseCard v-for="course in courses" :key="course.id" :course="course" @save-course="addToWishlist" />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import CourseCard from "./components/CourseCard.vue";
import braaiSnoek from "./assets/Braaied Snoek.jpg";
import malvaPudding from "./assets/Malva Pudding.jpg";
import bunnyChow from "./assets/Bunny Chow.jpg";
import traditionalDurbanMuttonCurry from "./assets/Traditional Durban Mutton Curry.jpg";

export default {
  components: {
    Header,
    CourseCard
  },

  data() {
    return {
      wishlistCount: 0,

      courses: [
        {
          id: 1,
          title: "Braai Snoek",
          chef: "Chef Heston Blumenthal",
          level: "Beginner",
          price: 199,
          available: true,
          image: braaiSnoek
        },
        {
          id: 2,
          title: "Malva Pudding",
          chef: "Chef Wolfgang Puck",
          level: "Intermediate",
          price: 250,
          available: false,
          image: malvaPudding
        },
        {
          id: 3,
          title: "Bunny Chow",
          chef: "Chef Jamie Oliver",
          level: "Advanced",
          price: 399,
          available: true,
          image: bunnyChow
        },
        {
          id: 4,
          title: "Traditional Durban Mutton Curry",
          chef: "Alice Waters",
          level: "Intermediate",
          price: 379,
          available: true,
          image: traditionalDurbanMuttonCurry
        }
      ]
    };
  },

  methods: {
    addToWishlist() {
      this.wishlistCount++;
    }
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #f8f4ef;
  font-family: Arial, sans-serif;
}

.course-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
  padding: 30px;
}
</style>