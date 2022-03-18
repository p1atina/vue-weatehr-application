<template>
  <header class="header">
    <h2>Weather Apllication</h2>
    <p>{{ username }}님 반갑습니다.</p>
  </header>
</template>

<script>
export default {
  name: "HeaderDisplay",
  data() {
    return {
      username: 'rudolf',
    }
  }
}
</script>

<style scoped>
.header {
  background: linear-gradient(15deg, #FF416C, #FF4B2B);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1em;
}
.header h2 {
  color: #ffffff;

}

.header p {
  font-size: 12px;
  color: #ffffff;
}

</style>