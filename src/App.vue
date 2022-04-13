<template>
  <header>
    <div>
      <Header/>
    </div>
  </header>
  <main>

  </main>
  
</template>
<style>
  :root{
    --primary:#216190;
    --line-detail:rgba(33,97,144,0.75);
  }
</style>
<script>
  import Header from './components/HeaderBox/HeaderBox.vue';
  import './assets/tailwind.css';  
    export default{
      name:'App',
      components:{
        Header
      }
    };
</script>