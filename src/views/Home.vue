<template>
  <div class="home">
    <h1>Hello, I'm Jimmy Yeung</h1>
    <h2>iOS Software Engineer with {{ experienceYear }} years of experience in </h2>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
export default {
  name: 'Home',
  setup() {
    const experienceYear = ref(0)
    const calculateExperienceYearsFrom = (date) => {
      const today = new Date()
      const years = today.getFullYear() - date.getFullYear()
      return years
    }

    onMounted(() => {
      experienceYear.value = calculateExperienceYearsFrom(new Date("2016-04-01"))
    })

    return {
      experienceYear,
      calculateExperienceYearsFrom
    }
  },
  components: {
    
  },
}
</script>
