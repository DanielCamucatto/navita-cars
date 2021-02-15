<template>
  <section>
    <div id="container-cars">
      <h1>Veículos</h1>
      <h2>Marcas</h2>
      <div class="brands">
        <div class="brands-itens title">Marca</div>
        <div class="brands-itens">
            Fiat
          <a @click="findCars(marca.codigo)">
            Ver modelos
          </a>
        </div>
      </div>
    </div>
    <div id="container-models">
      <h2>Modelos</h2>
      <div class="models">
        <div class="models-itens title" > Modelo</div>
        <div class="models-itens" >sei la</div>
        <div class="models-itens">Prisma</div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
export default {
    
  data() {
    return {
      cars: [],
      modelos:[]
    };
  },
  mounted(){
      this.findCars();
  },
  methods: {
    findCars(){
        const self = this;
        axios.get("https://parallelum.com.br/fipe/api/v1/carros/marcas").then((resp)=>{
            console.log(resp)
            if(resp === 200){
                self.cars = resp.data;
            }
        });
    } , 
    selectedLink: () => {
      //const select = event.currentTarget
      //console.log(select)
      const selected = document.querySelectorAll("active");
      //console.log(selected)
      selected.forEach((select) => {
        select.classList.remove("active");
      });
    },
  },
}
</script>

<style>
section {
  background-color: #f7f8fb;
  color: #5a5c69;
  padding: 2%;
}
h1 {
  font-size: 2rem;
  font-weight: 500;
  padding: 2%;
}
#container-cars h2 {
  color: #4e73df;
  background-color: #f7f8fb;
  width: 90%;
  padding: 2%;
  margin: auto;
  border: solid 1px #e3e6f0;
  -webkit-box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
  -moz-box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
  box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
}
.brands {
  background-color: #fff;
  border: solid 1px #e3e6f0;
  box-shadow: rgba(58, 59, 69, 0.15);
  width: 90%;
  padding: 2%;
  margin: auto;
  -webkit-box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
  -moz-box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
  box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
}
.title {
  border-top: solid 1px #e3e6f0;
}
.brands-itens {
  display: grid;
  grid-template-columns: 1fr 2fr;
  border-bottom: solid 1px #e3e6f0;
  padding: 2%;
  font-size: 1.5rem;
}
.brands-itens a {
  text-decoration: none;
  color: #4e73df;
  transition: 2ms;
  text-align: center;
}
.brands-itens a:hover {
  color: #1cc88a;
}
.brands-itens .active {
  color: #1cc88a;
}
#container-models h2 {
  color: #4e73df;
  background-color: #f7f8fb;
  width: 90%;
  padding: 2%;
  margin: 5% auto 0px;
  border: solid 1px #e3e6f0;
  -webkit-box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
  -moz-box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
  box-shadow: 0px -8px 25px 0px rgba(58, 59, 69, 0.15);
}
.models {
  background-color: #fff;
  border: solid 1px #e3e6f0;
  box-shadow: rgba(58, 59, 69, 0.15);
  width: 90%;
  padding: 2%;
  margin: auto;
  -webkit-box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
  -moz-box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
  box-shadow: 0px 8px 25px 0px rgba(58, 59, 69, 0.15);
}
.models-itens {
  border-bottom: solid 1px #e3e6f0;
  font-size: 1.5rem;
  padding: 2%;
}
</style>
