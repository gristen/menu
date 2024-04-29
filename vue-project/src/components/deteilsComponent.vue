<script>
import { ref, onMounted,computed } from 'vue';
import axios from 'axios';

export default {
  setup() {
    const details = ref([]);

    onMounted(async () => {
      try {
        const { data } = await axios.get('https://77c5a6fe3757e543.mokky.dev/details');
       details.value  =data
       console.log(data)
      } catch (error) {
        console.error(error);
      }
    });

    const toggleStar = async (id) => {
  try {
    const index = details.value.findIndex(detail => detail.id === id);
    const detail = details.value[index];
    const response = await axios.patch(`https://77c5a6fe3757e543.mokky.dev/details/${id}`, {
      isStarred: !detail.isStarred
    });
   
    details.value[index] = response.data;
    console.log("response", response.data);

  } catch (error) {
    console.error(error);
  }
};

const sortedDetails = computed(() => {
  const starredDetails = details.value.filter(detail => detail.isStarred);
  const unstarredDetails = details.value.filter(detail => !detail.isStarred);
  return [...starredDetails, ...unstarredDetails];
});
    return {
      details,
      toggleStar,
      sortedDetails 
    };
  }
}
</script>
<template>
  <div class="wrapper">

 
  <div class="card_wrapper">
    <div class="card" v-for="(detail, index) in sortedDetails" :key="detail.id">
         <div class="favorite_wrapper">
          <img
      :src="detail.isStarred ? '/src/components/icons/Star 5 (3).svg' : '/src/components/icons/Star.svg'"
      alt=""
      @click="toggleStar(detail.id)"
    >
    </div>
  <div class="card_info">
    <div class="door">
      <div class="door_img">
        <img src="/src/components/icons/car_door_sfi21l9ahqn6 2.svg" alt="">
      </div>
      <div class="door_info">
        <h3>дверь {{ detail.id }}</h3> <br>
      <p>передняя правая</p>
      </div>
     
  </div>
  <div class="seller">
    <h3>Продовец</h3>
    <p>Source Unknown</p>
  </div>
  <div class="colvo">
    <h3>Количество</h3>
    <p>1344</p>
  </div>
  </div>

  <div class="actions">
    <div class="price">
      <p>1200 000</p>
      <img src="/src/components/icons/dollar.svg" alt="">
    </div>
   
      <div class="bottons">
        <button class="navigation"><img src="/src/components/icons/navigation.svg" alt="">Навигация</button>
        <button class="delivery"> <img src="/src/components/icons/delivery.svg" alt=""> купить с доставкой</button>

    
    </div>
  </div>
</div>
</div>
</div>
<div class="test"></div>
</template>
<style scoped>

/* .test {
background-color: #F5F5F5;
opacity: 0.5;
  width: 60.6667vh;
  height: 13.7593vh;
  position: absolute;
  bottom: 1.8519vh
} */
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

.card:last-child{
  margin-bottom: 0vh;
}

.card{
  background: rgba(255, 255, 255, 0.05);
  border-radius: 0.7407vh;
  padding: 1.4815vh 1.7593vh 1.8519vh 3.8889vh;
  margin-bottom: 1.2037vh;
  height: 10.763vh;
  position: relative;
  
  
}
.favorite_wrapper img{
  position: absolute;
  top: 1.0185vh;
  left: 1.0185vh;
  background-color: rgba(255, 255, 255, 0.05);
  padding: 0.1852vh;
  border-radius: 0.3704vh;
  width: 1.8519vh;
 
}

.bottons{
  display: flex;
}
.wrapper{
  margin-top: 1.8519vh;
}
.card_wrapper {
  padding-right: 1.7593vh;
  max-height: 60.2593vh;
  overflow-y: auto;
  position: relative; /* добавлено */
}

.delivery img {
  width: 1.2037vh;
}

.price{
  display: flex;
  align-items: center;
  
}
.price p {
  color: rgba(151, 240, 62, 1);
  font-weight: 500;
  font-size: 1.4815vh;
}
.price img{
  width: 1.4815vh;
  margin-left: 0.9259vh;
}
.hr{
  border: 0.0926vh solid;
  margin-top: 1.4815vh;
  border: 0.0926vh solid;
color: rgba(255, 255, 255, 0.05);

}

.actions{
  display: flex;
  justify-content: space-between;
  margin-top: 3.6111vh;


 
}

.door_info{
  line-height: 1.0185vh;

  
}


.navigation img{
  width: 0.9259vh;
  margin-right: 0.1852vh;
}
.card h3{
  color: rgba(255, 255, 255, 0.35);
}
.delivery img{
  margin-right: 0.2778vh;
}
.card_info{
  display: flex;
  justify-content: space-between;
  

  
}
.card_info h3{
  font-size: 1.4815vh;
}
.card_info p{
  font-size: 1.4815vh;
}
.door{
  display: flex;
  align-items: center;
}
.navigation{
  width: 10.9259vh;
  height: 2.8704vh;
  background: linear-gradient(178.9deg, #F7C901 0.94%, #846B00 197.18%);
  border-radius: 0.463vh;
  font-size: 1.2963vh;
  color: rgba(92, 75, 0, 1);
  margin-right: 0.7407vh;
  border:none
}
.delivery{
  width: 17.7778vh;
  height: 2.8704vh;
  border-radius: 0.463vh;
  background: linear-gradient(180deg, #37CA60 -27.63%, #144622 148.68%);
  color: rgba(255, 255, 255, 1);
  font-size: 1.2963vh;
  /* background-image: url("/src/components/icons/delivery.svg"); */
  border:none
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
