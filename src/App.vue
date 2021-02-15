<template>
  <div id="app">
    <Header/>
    <Cars/>
    <Footer/>
  </div>
</template>

<script>
   import Header from './components/Header'
   import Cars from './components/Cars'
   import Footer from './components/Footer' 

export default {
  name: 'App',
  components:{
    Header,
    Cars,
    Footer,
  } 
}
</script>


