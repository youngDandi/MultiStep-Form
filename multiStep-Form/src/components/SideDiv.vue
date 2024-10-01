<script>
import minhaImagem from '../assets/background.jpg';

export default {
    name: 'SideDiv',
    data() {
        return {
            backgroundImage: `https://uigaint.com/demo/html/anfraa/job-1/assets/images/bg/job-bg.jpg`
        };
    }
}
</script>

<template >
  <div class="side-div" :style="{ backgroundImage: 'url(' + backgroundImage + ')' }">
    <div class="Sside-div">
      <img src="https://uigaint.com/demo/html/anfraa/job-1/assets/images/logo.png" id="logo"/>
      <div class="Info-side-div">
          <h1 id="title">We are creative agency<br/> Let's Join with us !</h1>
          <h3 id="subtitle">Nor again is there anyone who loves or pursues or desires to obtein pain  of itself, because it is pain but because.</h3>
      </div>
      <h3 id="rights">Copyright © 2024 Luís Gomes. All Rights Reserved</h3>
    </div>
    
  </div>
</template>

<style scoped>
.side-div {
    width: 705px;
    height: 115vh;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    gap: 10px;
    
}

.Sside-div{
  
  margin-left: 10%;
  margin-top: 5%;
  
}

.Info-side-div{
  margin-top: 20%;
  
}

#title{
  color: white;
  font-size: 2.5rem;
  font-weight: 700;
  font-family: "Roboto", sans-serif;
  margin-bottom: 30px;
  line-height: 1.3;
  display: block;
    
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    
    unicode-bidi: isolate;
}

#subtitle{
  color: white;
  font-family: "Roboto", sans-serif;
  font-size: 1.0rem;
  font-weight: 400;
  line-height: 1.85;
}

#logo{
  display: flex;
  
}

#rights{
  margin-top: 25%;
  color: white;
  font-family: "Roboto", sans-serif;
  font-size: 0.9rem;
  font-weight: 400;
  line-height: 1.85;
}

@media (max-width: 1199px) {
    .side-div .Sside-div .Info-side-div {
        padding-left: 100px;
    }
}
@media (max-width: 1439px) {
    .side-div .Sside-div .Info-side-div {
        padding-right: 60px;
    }
}
</style>
