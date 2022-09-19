<script>
  
    const postData = {
      caption: '',
      image: ''
    };
  
 function formHandler() {
  fetch('http://localhost:8000/post/addpost',{
    method:  'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      caption: postData.caption,
      image:  postData.image
    })
  })
    .then(response => response.json())
    .then(result => console.log(result));

    
}
</script>
  
  <section>
    <form method="post" class="mx-96 mt-8  border rounded-xl p-4 shadow-2xl space-y-10 py-24 px-16 mt-24">
      <div class="flex justify-center"><img src="instagram.png" alt="instagram" class="w-24 "></div>
      <div class="space-x-4 flex">
        <label for="caption"class="font-mono text-xl whitespace-nowrap	">Enter your caption:</label>
        <input type="text" id="caption" bind:value={postData.caption} class="py-2 px-6 ml-4 outline-none bg-gray-200 rounded-lg">
      </div>
      <div>
        <label for="image" class="font-mono text-xl whitespace-nowrap	">Enter your image: </label>
        <input type="text" id="image" bind:value={postData.image} class="py-2 px-6 ml-4 outline-none bg-gray-200 rounded-lg">
      </div>
      <div class="flex justify-center"><button on:click="{formHandler}" class="bg-pink-500 text-white font-semibold py-2 px-6 rounded-xl hover:bg-pink-300">Create Post</button></div>
    </form>
  </section>
  
  