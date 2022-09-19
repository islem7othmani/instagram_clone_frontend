<script >
    import {createEventDispatcher} from 'svelte';
    let dispach = createEventDispatcher();
    
    function redirect(e){
        let res = e
          dispach('routes',res)
    };
 
</script>


<div class="flex justify-between mx-24 mt-8">
    <div class="w-36"><img src="1200px-Instagram_logo.svg.jpg" alt="logo" ></div>
    <div>
        <input type="text" placeholder="recherche" class="outline-none mt-1 bg-gray-200 py-2 px-10 rounded-lg">
    </div>
    <div>
        <div class="flex justify-around space-x-6 mt-2">
           
            <button on:click="{()=>redirect("1")}">Home</button>
            <button on:click="{()=>redirect("2")}">add post</button>
            <button>Profile</button>
            <button>Profile</button>
            <button on:click="{()=>redirect("3")}">Profile</button>

        </div>    
    </div>

</div> 
