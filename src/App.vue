<template>
  <header>
    <div>
      <Header/>
    </div>
  </header>
  <main class="mx-auto">
    <CardsBox/>
  </main>
    <footer>
      <Footer/>
    </footer>
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
  main{
    padding:35px 0 70px 0;
    width:70vw;
  }
</style>
<script>
  import Header from './components/HeaderBox/HeaderBox.vue';
  import Footer from './components/Footer/Footer.vue';
  import CardsBox from './components/CardsBox/CardsBox.vue';
  import './assets/tailwind.css';  
  
  export default{
      name:'App',
      components:{
        Header,
        Footer,
        CardsBox
      }
    };
</script>