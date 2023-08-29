<template> 
  <NuxtLayout>
    <Header />
    <NavBar />
    <Aside />
    <Main />    
    <footer>
      <p>footer</p>
    </footer>
  </NuxtLayout>
 
 
</template>





<style>
/* *{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-decoration: 0;
  list-style: none;
} */

img{
  display: block;
  width: 100%;
}

/* body{
  
  grid-template-areas: 
  'header header header'
  'nav nav nav'
  'aside main main'
  'aside main main'
  'footer footer footer';
} */

/* body div{
  margin: 5px;
} */



main{  
  padding: 30px;
}

footer{
  grid-column: 1 / -1;
  text-align: center;
  font-size: 2rem;
  color: #fff;
  background: #000;
}

/* .news::after{
  content: ' ';
  width: 100%;
  height: 10px;
  background: #333;
} */


/* .news{
  position: relative;
} */
/* 
.fade{
  height: 100px;
  margin: 30px 0;
  transform: translateX(0) scale(1); 
   
} */

.fade:hover{  
  height: auto;
  
  /* z-index: 1; */
  /* transform: translateX(0) scale();  */
}

</style>