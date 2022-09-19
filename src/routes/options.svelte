<script>
    export let eletodelete ;

  function formHandler(event) {
    event.preventDefault()

    fetch(`http://localhost:8000/post/delete/${eletodelete}`,{
      method:  'DELETE'
    })
      .then(response => response.json())
      .then(result => console.log(result))};
</script>  

<div class="flex space-x-4">
    <button on:click="{formHandler}" class="block text-red-900 py-2 px-4 max-w-sm bg-gray-100 rounded-lg border border-gray-200 shadow-md hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">Delete</button>
    
</div>
