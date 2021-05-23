<script lang="ts"> 
	function clickOutside(element, callbackFunction) {
		function onClick(event) {
			if (!element.contains(event.target)) {
				callbackFunction();}
			}	
		document.body.addEventListener('click', onClick);
		
	return {
		update(newCallbackFunction) {
		callbackFunction = newCallbackFunction;},
		destroy() {
				document.body.removeEventListener('click', onClick);}
	}
	}
	let showVideo = false;
	let promptValue = '';
		
	
</script>

<main>
	<div class="card">
		<div class="container">
			<h1>Welcome {promptValue}</h1></div>
</div>

	<div class="card3">
		<button on:click="{() => promptValue = prompt()}">Register</button>			
	</div>	 
	
	
	<div class="card2">
		<div class="container">
				{#if showVideo}
		<div class="Video"
				 use:clickOutside={() => {
				 console.log('clicked outside');
				 showVideo = false;
			   }}>
			<iframe width="560" height="315" src="https://www.youtube.com/embed/75LCg-sT9SQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>				</div>
	{:else}
		<button on:click={(event) => {
			showVideo = true;
			event.stopPropagation();
		}}>Open video</button>
	{/if}		
		</div>
				</div>		  
</main>



<style>
	
	.card {
		box-shadow: 0 4px 8px 0 rgba(236, 127, 3, 0.2);
  		transition: .3s;
  		width: 40%;
  		border-radius: 5px;
		  width: 400px;
	}
	
	.card:hover {
		box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0);
	}
	.card2{
		box-shadow: 0 4px 8px 0 rgba(236, 127, 3, 0.2);
  		transition: .3s;
  		width: 40%;
  		border-radius: 5px;
		  width: 600px;
		  margin-left: 300px;margin-top: 20px;
		  text-align: center;
		  
		  
	}
	.card2:hover{
		box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0);
		

	}
	.card3{
		box-shadow: 0 4px 8px 0 rgba(236, 127, 3, 0.2);
  		transition: .3s;
  		border-radius: 5px;
		  width: 80px;
		  margin-left: 1120px;
		  text-align: right;
		  height: 50px;
		  
	}
	.card3:hover{
		box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0);
		}
	.container {
  padding: 16px 30px;

}

	h1 {
		margin-bottom: 10px;
		color: #ff3e00;
		text-transform: uppercase;font: 1em georgia;
		font-size: 2em;
		font-weight: 100; 
	}
	iframe{
		padding-right: 10px;
		width: 500px;
	}
button {
	
	background-color: rgba(255, 30, 0, 0.959);
	font: bold;
	border-color: rgba(255, 30, 0, 0.959)
	;
	}
	button:hover{
		background-color: darkred;
		border-color: darkred;
		color: crimson;
		border-width: 20px;
		border-block: 10px;
		
	}
	.Video {
		width:500px ;
		padding: 16px;
		border: 10px solid black;
	}
	
	
</style>
	
		

