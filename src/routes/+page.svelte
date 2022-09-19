<script>
	import Post from "./post.svelte" ;
	import  Header from "./header.svelte";
import Addpost from "./addpost.svelte";
import Register from "./register.svelte";
	let num;
function routes(e){
     num = e.detail;
	 console.log(num)
};
   
</script>
<header>
<div>
	<Header on:routes={routes}/>
</div>
</header>
{ #if num === "1"}
<Post/>
{:else if num === "2"}
<Addpost/>
{:else if num === "3"}
<Register/>
{/if}


