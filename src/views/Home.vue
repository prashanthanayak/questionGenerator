<template>
  <div class="container">
    <div class="section">
      <div>
        <div class="header">Random Question Generator</div>
        <router-link to="/register">
          <button type="button" class="qustn-generator" to="/register">Generate question</button>
        </router-link>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
}
.container {
  background: linear-gradient(rgba(69, 23, 113, 0.92), rgba(69, 23, 113, 0.92));
  display: flex;
  height: 100vh;
  justify-content: center;
  .section {
    align-items: center;
    display: flex;
    justify-content: center;
    text-align: center;
    .header {
      color: #ffffff;
      font-size: 60px;
      margin-bottom: 30px;
    }
  }
}
</style>
