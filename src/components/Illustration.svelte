<script>
  import { spring } from 'svelte/motion';
  
  const transformSpring = spring(0, { stiffness: 0.2, damping: 0.1 });
  const toggleTransform = () => transformSpring.update(val => (val ? 0 : 500));
</script>

<img
     src="https://glitch-hello-website.glitch.me/public/illustration.svg" 
     style="transform: translateX({$transformSpring}px)"
     on:hover={toggleTransform}
/>
<style>
img {
  max-width: 100%;
  max-height: 400px;
  cursor: pointer;
  padding-left: 3.5rem;
}
</style>