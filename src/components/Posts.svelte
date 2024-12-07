<script>
  import { onMount } from 'svelte';

  let posts = [];
  let loading = true;
  let error = null;
  let wordpressUrl = '';
  let showChild = false;

  const fetchPosts = async () => {
    if (!wordpressUrl) return;

    try {
      const response = await fetch(`${wordpressUrl}/wp-json/wp/v2/posts`);
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
      }
      posts = await response.json();
    } catch (err) {
      error = err.message;
    } finally {
      loading = false;
    }
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    showChild = true;
    fetchPosts();
  };
</script>

<style>
  .posts {
    font-family: Arial, sans-serif;
  }
  .post {
    border-bottom: 1px solid #ccc;
    padding: 1em 0;
  }
  .post:last-child {
    border-bottom: none;
  }
  .error {
    color: red;
  }
  .form {
    margin-bottom: 1em;
  }
</style>

<form class="form" on:submit={handleSubmit}>
  <label for="input">Enter WordPress URL:</label>
  <input id="input" type="url" bind:value={wordpressUrl} required />
  <button type="submit">Submit</button>
</form>

{#if showChild}

<div class="posts">
  {#if loading}
    <p>Loading posts...</p>
  {:else if error}
    <p class="error">Error: {error}</p>
  {:else if posts.length === 0}
    <p>No posts found.</p>
  {:else}
    {#each posts as post}
      <div class="post">
        <h2>{post.title.rendered}</h2>
        <div>{@html post.excerpt.rendered}</div>
      </div>
    {/each}
  {/if}
</div>

{/if}

