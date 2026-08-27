<script>
  import { onMount } from 'svelte'

  let message = $state('')

  onMount(async () => {
    const res = await fetch('https://me-api.jsramverk.se')
    const data = await res.json()
    message = data.description
  })
</script>

<main>
  <h1>Me</h1>
  <p>{message}</p>
</main>
