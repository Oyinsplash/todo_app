<template>
  <header class="header">
      <h1>Todo List</h1>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
  </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
    .header {
        background: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
    }

    .header a {
        color: #fff;
        padding: 2.5px 5px;
        text-decoration: none;
    }

    .header a:hover {
        border:1px solid #fff;
    }
</style>