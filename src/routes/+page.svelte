<script lang='ts'>
  let openDialog = false;

  function openCloseModal() {
    openDialog = !openDialog;        
  };
</script>

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
           
          <div style="flex-grow: 1; width: 300px;">
             <h4>Chart</h4>
           
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
      <button aria-label="Close" rel="prev" on:click={openCloseModal}></button>
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
 