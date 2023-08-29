<template>  
    <nav class="col-span-full row-start-3 row-end-3">
      <ul>
        <li><a href="">News</a></li>
        <li><a href="">Músicas</a></li>
        <li><a href="">Categoria</a></li>
      </ul>
      <a href="">Rede Social</a>
    </nav>
 
</template>

<style >
nav{ 
  grid-area: nav;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  background: #000;
}

nav a{
  color: #fff;
}

nav > ul{
  display: flex;
  gap: 20px
}
  
</style>