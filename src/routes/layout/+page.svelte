<div class="cont m-auto sm-flex md:grid lg:grid">
  <div class="color-blue-400 bg-blue-400"> </div>
  <div class="color-teal-400 bg-teal-400">  </div>
  <div class="color-fuchsia-400 bg-fuchsia-400">  </div>
  <div class="color-rose-100 bg-rose-100">  </div>
  <div class="color-yellow-100 bg-yellow-100 mountain"> 
      <Mountain/>
  </div>
  <div class="color-blue-300 bg-blue-300">  </div>
  <div class="color-emerald-400 bg-emerald-400">  </div>
</div>


<script>
// @ts-nocheck

  import Mountain from "$lib/components/Mountain.svelte";
</script>
<style>
    
    @media screen and (max-width: 767px){
      div{
         min-height: 400px;
      }
    }
    
    .mountain{
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      
    }
    .cont{      
      width: 100%;
      height: 100vh;
      grid-template-columns: repeat(6 , 1fr);
      grid-template-rows: repeat(6 , 1fr);
      grid-template-areas: 
        "color-blue-400 color-rose-100 color-rose-100 color-blue-300 color-blue-300 color-blue-300"
        "color-blue-400 color-rose-100 color-rose-100 color-blue-300 color-blue-300 color-blue-300"
        "color-blue-400 color-rose-100 color-rose-100 color-yellow-100 color-yellow-100 color-emerald-400"
        "color-teal-400 color-rose-100 color-rose-100 color-yellow-100 color-yellow-100 color-emerald-400"
        "color-teal-400 color-rose-100 color-rose-100 color-yellow-100 color-yellow-100 color-emerald-400"
        "color-fuchsia-400 color-fuchsia-400 color-fuchsia-400 color-yellow-100 color-yellow-100 color-emerald-400"  
      ;
    }

    .color-blue-400{
      grid-area: color-blue-400;
      
    }

    .color-teal-400{
      grid-area: color-teal-400;
      
    }

    .color-fuchsia-400{
      grid-area: color-fuchsia-400;
      
    }

    .color-rose-100{
      grid-area: color-rose-100;
    
  
    }

    .color-yellow-100{
      grid-area: color-yellow-100;
     
    }

    .color-blue-300{
      grid-area: color-blue-300;
    }

    .color-emerald-400{
      grid-area: color-emerald-400;
    }

  </style>