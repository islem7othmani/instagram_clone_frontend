<script>

          export let eletoupdate ;
          export let captionofelement;

          const updateData = {
      caption: '',
    };

function formHandler(event) {
    event.preventDefault()
    captionofelement = updateData.caption ;
    fetch(`http://localhost:8000/post/update/${eletoupdate}`,{
      method:  'PUT',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        caption : updateData.caption,
      })
    })
      .then(response => response.json())
      .then(result => console.log(result))
      window.location.reload();
  }
  

</script>

<div class="z-50 flex gap-4 ml-4">
    <input type="text" bind:value={updateData.caption} placeholder={captionofelement} class="outline-none">
    <button on:click="{formHandler}" class="text-blue-300 py-2 px-4 hover:text-blue-500">Update</button>
</div>