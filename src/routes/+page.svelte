<script lang='ts'>
  import edit_icon from '$lib/assets/edit_document.svg';
  import { MeterChart } from '@carbon/charts-svelte'  
  
  let options =  {
    theme: 'g100',
    resizable: true,
    legend: {      
      position: 'bottom',     
    },
    data: {
      loading: false
    },
    title: 'Task Meter Chart',
    height: '180px',
    meter: {
      proportional: {
        total: 350,
        unit: 'tasks'
      },
      showLabels: true,
    }
  };

  let data = [
    {
      group: 'Done',
      value: 200
    },
    {
      group: 'In progress',
      value: 65
    },
    {
      group: 'Skipped',
      value: 75
    } 
  ];

  let openDialog = false;

  function openCloseModal() {
    openDialog = !openDialog;        
  };

  function addNewTask() {
    openDialog = !openDialog;        
  };

</script>

<svelte:head>
    <title>SvleteKit TODO</title>
</svelte:head>

<h3>TODO APP&nbsp;<img src='../src/lib/assets/list_alt.svg' alt="Edit"></h3>

<div role="tablist">
  <details open>
    <!-- svelte-ignore a11y_no_redundant_roles -->
    <summary role="" class="outline secondary"><b>Open tasks</b></summary>
    <hr/> 
      <button class="outline" onclick={openCloseModal}><img src='../src/lib/assets/add_notes.svg' alt="Edit">&nbsp;Add new task</button>
      <div class="grid"> 
       <div style="display: flex; flex-direction: row; flex-wrap: wrap">
          <div class="overflow-auto" style="flex-grow: 3;">
           <!-- tasks -->
           <table>
             <thead>
               <tr>
                 <th>Edit</th>
                 <th scope="col">Task</th>
                 <th scope="col">Type</th>
                 <th scope="col">Notes</th>
                 <th scope="col">Date</th>
                 <th scope="col">Status</th>
               </tr>
             </thead>
             <tbody>
               <tr>
                 <td><a href="/" onclick={openCloseModal}><img src={edit_icon} alt="Edit"></a></td>
                 <th scope="row">Mercury</th>
                 <td>4,880</td>
                 <td>0.39</td>
                 <td>88</td>
                 <td>Done</td>
               </tr>
               <tr>
                 <td><a href="/" onclick={openCloseModal}><img src={edit_icon} alt="Edit"></a></td>
                 <th scope="row">Venus</th>
                 <td>12,104</td>
                 <td>0.72</td>
                 <td>225</td>
                 <td>In progress</td>
               </tr>
               <tr>
                 <td><a href="/" onclick={openCloseModal}><img src={edit_icon} alt="Edit"></a></td>
                 <th scope="row">Earth</th>
                 <td>12,742</td>
                 <td>1.00</td>
                 <td>365</td>
                 <td>Done</td>
               </tr>
               <tr>
                 <td><a href="/" onclick={openCloseModal}><img src={edit_icon} alt="Edit"></a></td>
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
          <MeterChart {data} {options} />
           
          <!-- <div style="flex-grow: 1; width: 300px; height: auto;">
             <h4>Chart</h4>             
          </div>-->
        </div>  
      </div>      
  </details>
  <hr/>
  <details>
    <!-- svelte-ignore a11y_no_redundant_roles -->
    <summary role="button" class="outline contrast">Closed tasks</summary>
    <div role="tabpanel">      
      <div style="display: flex; flex-direction: row; flex-wrap: wrap">
          <div class="overflow-auto" style="flex-grow: 3;">           
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
            
          <MeterChart {data} {options} />
           
          <!-- <div style="flex-grow: 1; width: 300px; height: auto;">
             <h4>Chart</h4>             
          </div>-->
        </div>  
    </div>
  </details>   
</div>

<dialog open = {openDialog}>
  <article>
    <header>      
      <a href="/" rel="prev" aria-label="Close" onclick={openCloseModal}></a> 
      <p>
        <strong>🗓️ Add new task</strong>
      </p>
    </header>
    <form>
      <fieldset>
        <label>
          Task name
          <input
            name="first_name"
            placeholder="Task name"
            autocomplete="given-name"
          />
        </label>
        <label>
          Type
          <input            
            name="type"
            placeholder="Type"
            autocomplete="given-name"
          />
        </label>
        <label>
          Notes
          <textarea           
            rows="4"
            name="type"
            placeholder="Additional notes..."
            autocomplete="given-name"
          ></textarea>
        </label>
      </fieldset>

      <input
        type="submit"
        value="Add new task"
        onclick="{addNewTask}"
      />
    </form>
  </article>
</dialog>
 