
<script>
  import MyDetails  from "./components/deteilsComponent.vue";
  import Build  from "./components/buildComponent.vue";
  export default {
    components:{
      MyDetails, 
      Build
    },
    data(){
      return {
        component:'MyDetails'
      }
    }
  }
  </script>
<template>
  <main class="main-container">
    <div class="container">
      <div class="header">
        <h1>Починка авто</h1>
        <p>Здесь будет какая-то информация</p>
      </div>
      <div class="header_content">
      <div class="transport_info">
        <img src="/src/components/icons/car.svg" alt="">
        <div class="info">
          <p>автомобиль</p>
        <span>Mitsubishi Lancer X</span>
        </div>
       
      </div>
      <div class="transport_price">
        <p class="price_info">стоимость продажи
        <br>
        <span class="price">17000</span>
        </p>
        <button type="submit" class="transport_delete">Утилизовать</button>
      </div>
    </div>
    <div class="buttons">
        <button
          type="button"
          @click="component='MyDetails'"
          :class="{ active: component === 'MyDetails' }"
          class="deteils"
         
        >
          Детали
        </button>
        <button
          type="button"
          @click="component='Build'"
          :class="{ active: component === 'Build' }"
          class="build"
        >
          Сборки
          
        </button>
      </div>
    </div>
    <component :is="component" ></component >
  </main>

</template>

<style scoped>

.transport_info{
  display: flex;
  align-items: center;

 
}
.transport_delete{
  margin-left: 1.3889vh;
}
.transport_info img {
  width: 6.2037vh;
}
.info{
  margin-left: 1.1111vh;
}


.price_info{
color: rgba(255, 255, 255, 0.55);
}
.price{
  display: flex;
    justify-content: end;
    color: white;
}
.transport_price{
  align-items: center;
}
.info p{
  color: rgba(255, 255, 255, 0.55);
}
.info span{
  color: white;
}

.door,.seller,.colvo{
  height: fit-content;
}
.buttons{
  height: 3.7037vh;
  display: flex;
}
.deteils{
  border-radius: 0.5556vh 0px 0px 0.5556vh;
  font-size: 1.2963vh;
}
.build{
  border-radius: 0px 0.5556vh 0.5556vh 0px;
  font-size: 1.2963vh;
}
</style>
