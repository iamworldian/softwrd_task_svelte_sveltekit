
<div class="cont">


{#if $loading}
  <Loading/>
{:else if $error}
  <Error message={error.message}/>
{:else}
  <CountryTable countries={data}/>
{/if}
  

  <div class="graph bg-orange-50">
    <PolarAreaChart countries={data}/>
  </div>

</div>
  


<script>
// @ts-nocheck

  import CountryTable from '$lib/components/CountryTable.svelte';
  import fetchStore from '$lib/util/countryDataStore';
  import Loading from '$lib/components/Loading.svelte';
  import Error from '$lib/components/Error.svelte';
  import PolarAreaChart from '$lib/components/PolarAreaChart.svelte';
  import { setContext } from 'svelte';
	import { writable } from 'svelte/store';

let url = "https://restcountries.com/v3.1/all"

const [data, loading, error, get] = fetchStore(url);



</script>

<style>

   .cont {
        display: flex;
        justify-content: center;
        align-items: flex-start;
        width: 100vw;
       
        
    }

    .graph{
        height: 80vh;
        padding: 0em 1em;
        margin: 1em;
        border-radius: 0.5em;
        border: 0.002em solid rgb(206, 206, 206);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items:flex-start;
    }
</style>