<script lang="js">
  export let url;
  
  function handleButtonClick(event) {
    location.href = url;
  }
</script>

<button on:click={handleButtonClick}>
  <slot></slot>
</button>


<style>
button {
  font-family: HK Grotesk;
  padding-left: 1rem;
  padding-right: 1rem;
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
  font-size: 1.1rem;
  line-height: 1rem;
  font-weight: 500;
  align-items: center;
  display: inline-flex;
  cursor: pointer;
  background: #FFFFFF;
  border: 1px solid #000000;
  box-sizing: border-box;
  border-radius: 4px;
  color: #000;
  text-decoration: none;
  transition: background-color 0.5s ease;
}

button:hover {
  background-color: #D0FFF1;
}

button img {
  margin-right: 0.5rem;
}

button {
  margin-right: 1rem;
}
</style>