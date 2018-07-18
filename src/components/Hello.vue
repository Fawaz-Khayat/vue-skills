<template>
  <div class="hello">
    <h1>Hello {{ person_name.charAt(0).toUpperCase() + person_name.slice(1) }}</h1>
  </div>
</template>

<script>
export default {
    data() {
        return {
            person_name: this.$route.params.name
        }
    }
}
</script>