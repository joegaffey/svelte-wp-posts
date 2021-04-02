<script>
  import { spring } from 'svelte/motion';
  
  /* Make sure to take prefers-reduced-motion into account */
  function prefersReducedMotion() {
    const mediaQueryList = window.matchMedia('(prefers-reduced-motion: reduce)');
    return mediaQueryList.matches;
  }
  
  const transformSpring = spring(0, { stiffness: 0.1, damping: 0.1 });
  const toggleTransform = () => {
    return prefersReducedMotion() ? null : transformSpring.update(val => (val ? 0 : 10));
  }
</script>

<img
     src="https://glitch-hello-website.glitch.me/public/illustration.svg" 
     style="transform: translateX({$transformSpring}px)"
     on:mouseover={toggleTransform}
/>
<style>
img {
  max-width: 100%;
  max-height: 400px;
  cursor: pointer;
  padding-left: 3.5rem;
}
</style>