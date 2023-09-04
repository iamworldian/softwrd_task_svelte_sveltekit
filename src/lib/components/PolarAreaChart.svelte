
<script>
    import Chart from 'chart.js/auto';
    import {beforeUpdate, onMount} from 'svelte';
   
    /**
	 * @type {import("chart.js/auto").ChartItem}
	 */
    
    export let countries;

    let mostPopulatedCountries , labels , values,ctx;
    
    let myChart = new Chart(ctx , {});

   
    beforeUpdate(() => {
        
        // @ts-ignore
        // @ts-ignore
        mostPopulatedCountries = Object.entries($countries).sort(function (c1 , c2) {
            return c2[1].population - c1[1].population;
        }).slice(0 , 10);
        
        console.log('lebels 1', mostPopulatedCountries);
        labels = mostPopulatedCountries.map(v => v[1].name.common);
        values = mostPopulatedCountries.map(v => v[1].population);
        console.log('lebels',labels,values);
        
        myChart.destroy();
        // @ts-ignore
        myChart = new Chart(ctx, 
        {
            type: 'polarArea',
            data: {
                labels: [
                    ...labels
                ],
                datasets: [{
                    label: 'Population',
                    data: [...values],
                    backgroundColor: [
                    '#eceff1',
                    '#cfd8dc',
                    '#b0bec5',
                    '#90a4ae',
                    '#78909c',
                    '#607d8b',
                    '#546e7a',
                    '#455a64',
                    '#37474f',
                    '#263238'
                    ]
                }]
                },
            options: {
                plugins: {
                    title: {
                        display: true,
                        text: 'Top 10 over populated countries',
                        padding: {
                            top: 10,
                            bottom: 10
                        },
                        font: {
                                size: 22
                        }
                        
                    },
                    subtitle: {
                        display: true,
                        text: 'Where the most people live',
                        font: {
                                size: 20
                        },
                        padding: {
                            top: 10,
                            bottom: 10
                        },
                    },
                    legend: {
                        display: true,
                        labels: {
                            color: 'black',
                            font: {
                                size: 14
                            },
                        
                            usePointStyle: true,
                            pointStyle: 'circle',
                            
                        },
                        position: 'bottom',
                    }
                }
            }
        });
    });


   

    onMount(() =>{

      

        
    })
</script>

<canvas width="500" height="500" bind:this={ctx}></canvas>

