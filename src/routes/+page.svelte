<script lang='ts'>
  import { BarChartSimple, DonutChart, PieChart } from '@carbon/charts-svelte'
  import '@carbon/charts-svelte/styles.css'
  
  let options =  {
    theme: 'g100',   
    resizable: true,
    legend: {
      position: 'bottom',
      truncation: {
        type: 'none'
      }
    },
    donut: {
      center: {
        label: 'Browsers'
      }
    },
    data: {
      loading: true
    },
    height: '320px',
    width: '320px'
  };

  let data = [
    {
      group: 'Done',
      value: 20000
    },
    {
      group: 'In progress',
      value: 65000
    },
    {
      group: 'Skipped',
      value: 75000
    } 
  ];

  let openDialog = false;

  function openCloseModal() {
    openDialog = !openDialog;        
  };

</script>

<BarChartSimple
	data={[
		{ group: 'Qty', value: 65000 },
		{ group: 'More', value: 29123 },
		{ group: 'Sold', value: 35213 },
		{ group: 'Restocking', value: 51213 },
		{ group: 'Misc', value: 16932 }
	]}
	options={{
		theme: 'g90',
		title: 'Simple bar (discrete)',
		height: '400px',
		axes: {
			left: { mapsTo: 'value' },
			bottom: { mapsTo: 'group', scaleType: 'labels' }
		}
	}} />

  <PieChart {data} options={{
    theme: 'g90',
    title: 'Pie',
    resizable: true,
    height: '400px'}}  />

<svelte:head>
    <title>Dobrodošli!</title>
</svelte:head>

<h3>TODO APP</h3>

<div role="tablist">
  <details open>
    <!-- svelte-ignore a11y_no_redundant_roles -->
    <summary role="" class="outline secondary"><b>Open tasks</b></summary>
    <hr/> 
      <button class="outline" on:click={openCloseModal}>Add new task</button>
      <div class="grid"> 
       <div style="display: flex; flex-direction: row; flex-wrap: wrap">
          <div class="overflow-auto" style="flex-grow: 3;">
           <!-- tasks -->
           <table>
             <thead>
               <tr>
                 <th>+</th>
                 <th scope="col">Task</th>
                 <th scope="col">Type</th>
                 <th scope="col">Notes</th>
                 <th scope="col">Date</th>
                 <th scope="col">Status</th>
               </tr>
             </thead>
             <tbody>
               <tr>
                 <td><input type="checkbox"/></td>
                 <th scope="row">Mercury</th>
                 <td>4,880</td>
                 <td>0.39</td>
                 <td>88</td>
                 <td>Done</td>
               </tr>
               <tr>
                 <td><input type="checkbox"/></td>
                 <th scope="row">Venus</th>
                 <td>12,104</td>
                 <td>0.72</td>
                 <td>225</td>
                 <td>In progress</td>
               </tr>
               <tr>
                 <td><input type="checkbox"/></td>
                 <th scope="row">Earth</th>
                 <td>12,742</td>
                 <td>1.00</td>
                 <td>365</td>
                 <td>Done</td>
               </tr>
               <tr>
                 <td><input type="checkbox"/></td>
                 <th scope="row">Mars</th>
                 <td>6,779</td>
                 <td>1.52</td>
                 <td>687</td>
                 <td>In progress</td>
               </tr>
             </tbody>
             <tfoot>
               <tr>
                 <th scope="row"></th>
                 <th scope="row">Average</th>
                 <td>9,126</td>
                 <td>0.91</td>
                 <td>341</td>
                 <th scope="row"></th>             
               </tr>
             </tfoot>
           </table>
          </div>
           
          <div style="flex-grow: 1; width: 300px; height: auto;">
             <h4>Chart</h4>
             <DonutChart {data} {options} />
          </div>              
        </div>  
      </div>      
  </details>
  <hr/>
  <details>
    <!-- svelte-ignore a11y_no_redundant_roles -->
    <summary role="button" class="outline contrast">Closed tasks</summary>
    <div role="tabpanel">
      <p>Content for Tab 2.</p>
      <div style="display: flex; flex-direction: row; flex-wrap: wrap">
          <div class="overflow-auto" style="flex-grow: 3;">
            <h4>Done tasks</h4>
            <table>
              <thead>
                <tr>
                  <th scope="col">Planet</th>
                  <th scope="col">Diameter (km)</th>
                  <th scope="col">Distance to Sun (AU)</th>
                  <th scope="col">Orbit (days)</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <th scope="row">Mercury</th>
                  <td>4,880</td>
                  <td>0.39</td>
                  <td>88</td>
                </tr>
                <tr>
                  <th scope="row">Venus</th>
                  <td>12,104</td>
                  <td>0.72</td>
                  <td>225</td>
                </tr>
                <tr>
                  <th scope="row">Earth</th>
                  <td>12,742</td>
                  <td>1.00</td>
                  <td>365</td>
                </tr>
                <tr>
                  <th scope="row">Mars</th>
                  <td>6,779</td>
                  <td>1.52</td>
                  <td>687</td>
                </tr>
              </tbody>
              <tfoot>
                <tr>
                  <th scope="row">Average</th>
                  <td>9,126</td>
                  <td>0.91</td>
                  <td>341</td>
                </tr>
              </tfoot>
            </table>
          </div>
            
          <div style="flex-grow: 1;">
            <h4>Chart</h4>
            <b>Donout chart JS</b>            
          </div>              
        </div>  
    </div>
  </details>   
</div>

<dialog open = {openDialog}>
  <article>
    <header>      
      <a href="/" rel="prev" aria-label="Close" on:click={openCloseModal}></a> 
      <p>
        <strong>🗓️ Thank You for Registering!</strong>
      </p>
    </header>
    <p>
      We're excited to have you join us for our
      upcoming event. Please arrive at the museum 
      on time to check in and get started.
    </p>
    <ul>
      <li>Date: Saturday, April 15</li>
      <li>Time: 10:00am - 12:00pm</li>
    </ul>
  </article>
</dialog>
 