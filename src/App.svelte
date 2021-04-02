<script type="js">
  import SEO from './components/Seo.svelte';
  import Button from './components/Button.svelte';
  import Illustration from './components/Illustration.svelte';
</script>

<SEO/>

<main>
  <h1>Hello Svelte!</h1>
  <Illustration />
</main>
<footer>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
    </ul>
  </nav>
  <Button url="https://glitch.com/~ivy-gratis-eagle">
    Remix on Glitch
  </Button>
</footer>

<style>
:root {
  --color-bg: rgba(92, 201, 245, 1.00);
  --color-text-main: #2800FF;
  --color-primary: #AFECE0;
}

@font-face {
  font-family: HK Grotesk;
  src: url("https://cdn.glitch.com/a9975ea6-8949-4bab-addb-8a95021dc2da%2FHKGrotesk-Regular.otf?v=1602782380076")
    format("opentype");
}

@font-face {
  font-family: HK Grotesk;
  font-weight: bold;
  src: url("https://cdn.glitch.com/a9975ea6-8949-4bab-addb-8a95021dc2da%2FHKGrotesk-Bold.otf?v=1602782484249")
    format("opentype");
}

:global(body,html) {
  font-family: HK Grotesk;
  background-color: var(--color-bg);
  height: 100%;
  margin: 0;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1 0 auto;
  padding: 1rem;
}

h1 {
  color: var(--color-text-main);
  font-style: normal;
  font-weight: bold;
  font-size: 120px;
  line-height: 105%;
}


/* Footer Navigation grid */
footer {
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  padding: 1rem;
  width: 90%;
}

footer ul {
  display: flex;
  justify-content: space-between;
}


footer li {
  list-style-type: none;
  padding: .5rem 1rem;
  border-right: 1px solid black;
}

footer li:last-of-type {
  border: none;
}

footer a {
  font-style: normal;
  font-weight: normal;
  font-size: 1.1rem;
  color: #000;
  text-decoration: none;
  border-style: none;
} 
</style>