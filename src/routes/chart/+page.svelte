
<div>


{#if $loading}
  <Loading/>
{:else if $error}
  <Error message={error.message}/>
{:else}
  <CountryTable countries={data}/>
{/if}

  
</div>
  


<script>
// @ts-nocheck

  import CountryTable from '$lib/components/CountryTable.svelte';
  import fetchStore from '$lib/util/countryDataStore';
  import Loading from '$lib/components/Loading.svelte';
  import Error from '$lib/components/Error.svelte';

let url = "https://restcountries.com/v3.1/all"

const [data, loading, error, get] = fetchStore(url)

  
</script>

