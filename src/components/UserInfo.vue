<template>
  <section>
    
    <base-card>
  <template v-slot:header>
      <div>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </div>
    </template>
      <p>{{ infoText }}</p>
    </base-card>  
  </section>
</template>

<script>
export default {
  props: ['fullName', 'infoText', 'role'],
};
</script>

<style scoped>



section header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>