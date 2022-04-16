<template>
  <header>
    <Header @theme="changeTheme"/>
  </header>
  <main class='mx-auto'>
      <CardsBox/>
  </main>
  <footer>
    <Footer/>
  </footer>
</template>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@500;700&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Square+Peg&display=swap');
  *{
    margin:0;
    padding:0;
    box-sizing: border-box;
    font-family: 'Nunito', sans-serif;
  }
  :root{
    --primary:#216190;
    --line-detail:rgba(33,97,144,0.75);
    /*dark style*/ 
    --background-dark:#303030;
    --background-dark-app:#404040;
    --important-texts:#4db8ff;
   /* Geral */
    --white:#fff;
  }
  .darkModeApp{
    background:var(--background-dark-app);
  }
  .darkModeApp section,
  .darkModeApp main section .containerCard,
  .darkModeApp main section #mainCard{
    background:var(--background-dark);
  }
  .darkModeApp main section{
    background: var(--background-dark-app)
  }
  .darkModeApp a,
  .darkModeApp a:hover,
  .darkModeApp p,
  .darkModeApp h2,
  .darkModeApp span{
    color:var(--white);
  }
  .darkModeApp h1{
    color:var(--important-texts);
    text-shadow: 1px 1px 1px white;
  }
  .darkModeApp span.label,
  .darkModeApp h3,
  .darkModeApp h4{
    color:var(--important-texts);
  }
  .darkModeApp input[type='submit'],
  .darkModeApp input[type='button']{
    border:1px solid var(--important-texts);
    color:var(--important-texts);
  }
  .darkModeApp input[type='submit']:hover,
  .darkModeApp input[type='button']:hover{
    background:var(--important-texts);
  }

</style>

<style scoped>
  div{
    background:whitesmoke;
    padding:2px;
    border-radius:10px;
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
  import ChartBitcoin from './components/ChartBitcoin/ChartBitcoin.vue';
  import './assets/tailwind.css';  
  
  export default{
      name:'App',
      components:{
        Header,
        Footer,
        CardsBox,
        ChartBitcoin
      },
      data(){
        return{
          theme:'light'
        }
      },
      methods:{
        changeTheme(){
          const app = document.querySelector('#app');
          if(this.theme === "light"){
            this.theme="dark";
            app.classList.add('darkModeApp')
          }else{
            this.theme="light"
            app.classList.remove('darkModeApp');
          }
        }
      }
  };
</script>