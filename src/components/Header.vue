<template>
  <div id="header">
      <div class="logo">Navita</div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    *{
        padding: 0;
        margin: 0;
    }
    #header{
       -webkit-box-shadow: 0px 8px 8px 0px rgba(58,59,69,.15);
        -moz-box-shadow:    0px 8px 8px 0px rgba(58,59,69,.15);
        box-shadow:         0px 8px 8px 0px rgba(58,59,69,.15);
    }
    .logo{
        background-color:#FFF;
        color:#1CC88A;
        height: 5rem;
        font-size: 1.5rem;
        font-weight: bold;
        display: flex;
        align-items: center;
        padding-left: 5%;
    }
</style>