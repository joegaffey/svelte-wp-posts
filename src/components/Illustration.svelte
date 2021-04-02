<script>
  import { spring } from 'svelte/motion';
  
  let coords = spring({ x: 50, y: 50 }, {
		stiffness: 0.1,
		damping: 0.25
	});

	let size = spring(10);
  
</script>

<img cx={$coords.x} 
     cy={$coords.y} 
     r={$size} 
     src="https://glitch-hello-website.glitch.me/public/illustration.svg" />

<style>
img {
  max-width: 100%;
  max-height: 400px;
  cursor: pointer;
  padding-left: 3.5rem;
}
</style>