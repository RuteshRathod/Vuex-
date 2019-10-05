<template>
  <div class="User">
    <h1>This is {{ username }}'s Page</h1>
  </div>
</template>
<script>
export default {
  props: ["username"]
};
</script>
