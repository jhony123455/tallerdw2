 <template>
   <div>
      <header class="content">
        <h1>Pokemón</h1>
      </header>

      <MainComp></MainComp>
   </div>       
   </template>
     
     <script>
     import MainComp from '@/components/MainComp.vue';
     export default {
      name:'PokeView',
      components:{MainComp}
     }
     </script>
     
     <style>
     .content{
        background: #000;
        align-items: center;
     }

     .content h1{

        color: yellow;
     }
     </style>