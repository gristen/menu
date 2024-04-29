<template>
      <div class="wrapper">
      <div class="card_wrapper">
<div class="card" v-for="index in 10 " >
         
  <div class="card_info">
    <div class="door">
      <div class="door_img">
        <img src="/src/components/icons/car_door_sfi21l9ahqn6 2.svg" alt="">
      </div>
      <div class="door_info">
        <h3>дверь</h3> <br>
      <p>передняя правая</p>
      </div>
     
  </div>
 

  </div>
  <div class="actions">
    <div class="colvo">
    <p>0\6</p>
  </div>
    <button class="delivery">
         <img 
         src="/src/components/icons/Vector (3).svg"
          alt=""> Установить</button>
 </div>
</div>
</div>
</div>
</template>

<style scoped>
.card_wrapper::-webkit-scrollbar
{
	width: 0.1852vh;

}
.card_wrapper::-webkit-scrollbar-track
{
  border-radius: 0.0926vh;
	background-color: rgba(217, 217, 217, 10%);
}
.card_wrapper::-webkit-scrollbar-thumb
{
  border-radius: 0.0926vh;
  background-color: #F5F5F5;
}
.actions{
    display: flex;
    align-items: center;
}
.colvo {
  background-color: rgba(255, 255, 255, 0.03);
  display: flex;
  align-items: center;
  justify-content: center;
  width: 4.2593vh;
  height: 2.8704vh;
  border-radius: 0.463vh;
  margin-right: 0.7407vh;
}
.colvo p {
    font-size: 1.2963vh;
    color: rgba(255, 255, 255, 0.55);
}
.card_wrapper {
  padding-right: 1.7593vh;
  max-height: 60.2593vh;
  overflow-y: auto;
  position: relative; /* добавлено */
}
.wrapper{
  margin-top: 1.8519vh;
}
.card{
  
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: linear-gradient(90deg, rgba(255, 255, 255, 0.05) -2.67%, rgba(255, 255, 255, 0) 90.2%);

  border-radius: 0.7407vh;
  padding: 1.4815vh 1.6667vh 1.6667vh 2.037vh;
  margin-bottom: 1.2037vh;
  height: 4.2963vh;
  position: relative;
  
  
}
.delivery img {
  width: 1.2037vh;
}
.delivery{
  width: 11.5741vh;
  height: 2.8704vh;
  border-radius: 0.463vh;
  background: linear-gradient(178.9deg, #F7C901 0.94%, #846B00 197.18%);
  color: rgba(92, 75, 0, 1);
  font-size: 1.2963vh;
  /* background-image: url("/src/components/icons/delivery.svg"); */
  border:none
}
.card_info{
  display: flex;
  justify-content: space-between;
}
.door{
  display: flex;
  align-items: center;
}
.install{
    background: linear-gradient(178.9deg, #F7C901 0.94%, #846B00 197.18%);
    width: 11.5741vh;
    height: 2.8704vh;
    border-radius: 0.463vh;
}
.door_info{
  line-height: 1.0185vh;


  
}

.card_info h3{
  font-size: 1.4815vh;
}
.card_info p{
  font-size: 1.4815vh;
}
.card h3{
  color: rgba(255, 255, 255, 0.35);
}
.delivery img{
  margin-right: 0.2778vh;
}
.door_img{
  margin-right: 2.2222vh;
  width: 3.2407vh;
  height: 3.1194vh;
  display: flex;
}
.door_img img {
  width: 100%;
}

</style>