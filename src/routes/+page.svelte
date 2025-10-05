<script lang='ts'>
  
  const columns = [
    {
      field: 'selected',
      label: 'Check',
      //content: (checked:string) => `<input type="checkbox" ${checked}>`,
      //html: true
    },
    { field: 'rank', label: 'Rank' },
    { field: 'name', label: 'Name' },
    {
      field: 'countryCode',
      label: 'Country',
      //content: (code:string) => `<img src="https://flagcdn.com/w40/${code}.png">`,
      //html: true
    }
  ];

  const data = [
    { selected: 'checked', rank: 1, name: 'Carlos Alcraz', countryCode: 'es' },
    { selected: '', rank: 2, name: 'Novak Djokovic', countryCode: 'rs' },
    { selected: 'checked', rank: 3, name: 'Daniil Medvedev', countryCode: 'ru' },
    { selected: '', rank: 4, name: 'Holger Rune', countryCode: 'dk' },
  ];

//   const data = [
//     { '&#9745;':"<Checkbox checked=true/>", rank: 1, name: 'Carlos Alcraz', country: 'Spain' },
//     { '&#9745;':false, rank: 2, name: 'Novak Djokovic', country: 'Serbia' },
//     { '&#9745;':false, rank: 3, name: 'Daniil Medvedev', country: 'Russia' },
//     { '&#9745;':false, rank: 4, name: 'Holger Rune', country: 'Danemark' },
//   ];

    let noTaskInProgress = 12;
    let statusType = "InProgress";
    let dateFilter = "Date Up";

    let showModal = false;
</script>

<svelte:head>
    <title>Dobrodošli!</title>
</svelte:head>

<h3>TODO APP</h3>

<div class="grid"> 
  <div style=" display: flex; flex-direction: row;">

    <div style="width: 75%;">
      <h4>Tasks</h4>

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
      
      <div style="width: 25%;">
        <h4>Chart</h4>
        dfgdgf
      </div>
      
   </div>
 
</div>


 