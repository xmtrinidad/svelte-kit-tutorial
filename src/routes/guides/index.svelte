<script context="module">
  export async function load({ fetch }) {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts');
    const guides = await res.json();

    if (res.ok) {
      return {
        props: {
          guides
        }
      }
    }

    // not ok
    return {
      status: res.status,
      error: new Error('Could not fetch the guides')
    }
  }
</script>
  
<script>

  export let guides;

</script>

<div class="guides">
  <ul>
    {#each guides as guide}
      <li>
        <a href={`/guides/${guide.id}`}>{guide.title}</a>
      </li>
    {/each}
  </ul>
</div>

<style>
  .guides {
    margin: 24px 0;
  }

  a {
    color: #fff;
  }
</style>