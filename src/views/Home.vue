<template>
  <div class="home">
<section>
    <button @click="bounce =!bounce">Bounce</button>
    <br>
    <transition name="bounce">



    <img alt="Vue logo" src="../assets/logo.png"
    v-if="bounce"/>
    </transition>

  </section>


  <section>
      <button @click="roll =!roll">Roll</button>
      <br>
      <transition name="roll">



      <img alt="Vue logo" src="../assets/logo.png"
      v-if="roll"/>
      </transition>

    </section>

  </div>
</template>

<script>
// @ is an alias to /src


export default {

  name: "Home",
  data(){
    return{
      bounce:false,
      roll:false
    }
  },
  components: {

  }
};
</script>

<style>
section{
  min-height: 200px;

}
.bounce-enter-active{
  animation: bounce-in .5s;

}

.bounce-leave-active{
  animation:bounce-in .5s reverse;
}

.roll-enter-active{
  animation:roll-in .5s;

}

.roll-leave-active{
  animation: roll-in .5s reverse;
}

@keyframes bounce-in {
  0%{
    transform: scale(0);
  }
  50%{
    transform: scale(1.5);
  }
  100%{
    transform: scale(1);
  }
}

  @keyframes roll-in{
    0%{
    transform:scale(0) rotate(0deg) translateX(-250);
    opacity: 0;
    }

    100%{
transform:scale(1) rotate(360deg) translateX(0px);
opacity: 1;
    }
  }


</style>
