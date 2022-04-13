<template>
  <header>
    <div>
      <Header/>
    </div>
  </header>
  <main>
    <Footer/>
  </main>
  
</template>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@500;700&display=swap');
  *{
    font-family: 'Nunito', sans-serif;
  }
  :root{
    --primary:#216190;
    --line-detail:rgba(33,97,144,0.75);
    --footerBackground:rgba(204,204,204,0.22);
  }
</style>
<script>
  import Header from './components/HeaderBox/HeaderBox.vue';
  import Footer from './components/Footer/Footer.vue';
  import './assets/tailwind.css';  
  
  export default{
      name:'App',
      components:{
        Header,
        Footer
      }
    };
</script>