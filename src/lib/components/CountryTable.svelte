<div class="relative">
    <div class="table_container overflow-auto bg-orange-50">

        <table class="">
            <thead class="">
              <tr>
                <th>Flag</th>
                <th>Name</th>
                <th>Population</th>
                <th>CIOC</th>
                <th>UN Member <br>Status</th>
                <th>Currencies</th>
                <th>Languages</th>
              </tr>
            </thead>
            <tbody>
                {#each currentPage as country}   
                    <CountryTableRow {country}/>
                {/each}
            </tbody>
          </table>
        
        <div class="controller flex justify-center">
            <select on:change={handlePageSizeChange} class="bg-slate-600 text-white rounded-lg py-5 px-5">
                <option value=10 type="number">10</option>
                <option value=25>25</option>
                <option value=50>50</option>
                <option value=100>100</option>
            </select>
            
            <button on:click={nextPage} class="bg-slate-600 text-white rounded-lg py-5 px-5">
            Next Page</button>
        </div>
        </div>

       
</div>

<script>
    import { beforeUpdate } from "svelte";
    import { getContext } from "svelte";
    import fetchStore from '$lib/util/countryDataStore';
    import CountryTableRow from "./CoutnryTableRow.svelte";
  
     export let countries;
    /**
	 * @type {number}
	 */
    let lengthOfList,pageLength = 10;
    /**
	 * @type {any}
	 */
    // @ts-ignore

    let countriesToDisplay , currentPage , currentIndex = 0;
    $:pages = Math.ceil(lengthOfList / pageLength);


    beforeUpdate(() => {
		lengthOfList = Object.keys($countries).length;
        countriesToDisplay = Object.entries($countries);
        currentPage = CurrentPageGen();
        
	});

    /**
	 * @param {{ target: { value: string; }; }} event
	 */
    function handlePageSizeChange(event) {
        pageLength = parseInt(event.target.value);
    }

    function CurrentPageGen () {
        
        return countriesToDisplay.slice(currentIndex , currentIndex + pageLength);
    }

    function nextPage() {

        
        if(currentIndex < lengthOfList)currentIndex = currentIndex + pageLength;
        else currentIndex = 0;

        currentPage = CurrentPageGen();
        
    }
</script>

<style>

   
    .table_container{
        padding: 0em 1em;
        margin: 0.5em;
        width: 60vw;
        height: 80vh;
        border-radius: 0.5em;
        border: 0.002em solid rgb(206, 206, 206);
        display: flex;
        flex-direction: column;
        position: relative;
    }
    .controller{
        display: flex;
        margin: 1em;
        gap: 1em;
        position: fixed;
        bottom: 0;
        left: 50;

    }

    th{
        font-weight: bold;
        text-align: left;
        padding: 1em;
        font-size: 1em;
    }
  
</style>