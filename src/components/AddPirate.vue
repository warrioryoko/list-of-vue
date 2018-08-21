<template>
  <form v-on:submit.prevent="handleSubmit">
    <p>
      <label>
        Bike Model Name: <input v-model="name" placeholder="Model Name">
      </label>
    </p>
    <p>
      <label>
        Manufacturer: <input v-model="role" placeholder="Motorcyle Manufacturer">
      </label>
    </p>
    <p>
      <label>
        Engine Size: <input v-model="crew" placeholder="Engine size in CC">
      </label>
    </p>
    <p>
      <button>Add Motorcyle</button>
    </p>
  </form>
</template>

<script>
export default {
  props: {
    onAdd: Function
  },
  data() {
    return {
      name: '',
      role: '',
      crew: '',
    };
  },
  methods: {
    handleSubmit() {
      const newPirate = {
        name: this.name,
        role: this.role,
        crew: this.crew
      };
      this.onAdd(newPirate);
      
      this.name = '';
      this.role = '';
      this.crew = '';
    }
  }
};
</script>

<style>
</style>