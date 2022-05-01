<script context="module">
  export async function load({ fetch, params }) {
    const id = params.id;
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
    const guide = await res.json();

    if (res.ok) {
      return {
        props: {
          guide
        }
      }
    }

    // not ok
    return {
      status: res.status,
      error: new Error('Could not fetch the guide')
    }
  }
</script>

<script>

export let guide;

</script>

<div class="guide">
  <h2>{guide.title}</h2>
  <p>{guide.body}</p>
</div>

<style>
  .guide {
    margin: 40px 0;
    padding: 10px;
    border: 1px solid rgba(255,255,255,0.2);
  }
</style>