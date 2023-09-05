<script>
    export let country;
</script>

<tr class="text-ellipsis">
    <td class="text-2xl">{country[1].flag}</td>
    <td>{country[1].name.common}</td>
    <td>{country[1].population}</td>
    <td>{country[1].cioc}</td>
    <td>{#if country[1].unMember === true}
            <p class="p-2 bg-emerald-300 w-10 rounded-lg">YES</p>
        {:else}
            <p class="p-2 bg-red-200 w-10 rounded-lg">NO</p>    
        {/if}
    </td>
    <td>{country[1].currencies != null ? Object.keys(country[1].currencies)[0] : 'Undefined'}</td>
    <td class="">{country[1].languages != null ? Object.values(country[1].languages) : [].join(',')}</td>
</tr>

<style>
      td{
        padding : 0.5em;
        border-bottom: 0.002em solid rgb(206, 206, 206);
        min-width: 100px;
        font-size: 0.7em;
        max-width: 1em;
        text-overflow: ellipsis;
    }
   
</style>