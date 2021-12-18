<template>
  <div class="cards">
    <InfoCard/>
   <FormCard/>
  </div>
</template>

<script>
import InfoCard from "@/components/InfoCard.vue";
import FormCard from "@/components/FormCard.vue";

export default {
  name: 'Info',
  components: { FormCard, InfoCard },
};
</script>

<style scoped>
</style>
