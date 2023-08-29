<template>  
  <section v-for="i in items" :key="i.id">
    
    <div class=" bg-gray-200 mt-5 p-7">
      <p class="text-red-700">{{ i.category }}</p>
      <h1 class="text-3xl font-medium mb-2">{{ i.news_title }}</h1>
      <div class="flex gap-x-2.5">
        <div class="w-5/12"><img :src="i.news_image" alt=""></div>
        <h5 class="w-5/12 text-stone-600 	px-1.5" >{{ i.news_subtitle }}</h5> 
      </div> 
    </div>      
    <div v-if="loading" class="loading-message">Carregando...</div>
    <!-- <div v-if="reachedLimit" class="loading-message">Fim da lista</div>      -->
    
  </section>

    
  
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      items: [],
      page: 1,
      loading: false,     
      // items2:[],
      // reachedLimit: false,
      // maxItems: 15,
    };
  },
  async mounted() {
    window.addEventListener('scroll', this.handleScroll);
    await this.carregarMais();
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    async carregarMais() {
      if (this.loading) return; 

      this.loading = true;
      const response = await axios.get(`https://www.megasistema.app.br/api/diario-fm/news?page=${this.page}`);   
      
      this.items = this.items.concat(response.data.data);
      this.page++; 
      this.loading = false;     
     
    }, 
    
    handleScroll(){  
      
      const scrollY = window.scrollY;
      const windowHeight = window.innerHeight;
      const contentHeight = document.body.offsetHeight;

      if (scrollY + windowHeight >= contentHeight - 100) {
        this.carregarMais()  
      }
    }
    
  },
  
};

</script>

<style>
.loading-message {
  text-align: center;
  padding: 10px;
}
</style>