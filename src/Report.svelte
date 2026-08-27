<script>
  let { kmom } = $props()

  let questions = $state([])

  $effect(() => {
    fetch(`https://me-api.jsramverk.se/reports/${kmom}`)
      .then(res => res.json())
      .then(data => { questions = data.data })
  })
</script>

<main>
  <h2>{kmom}</h2>
  {#each questions as question, i (i)}
    <div class="question">
      <p><strong>{question.question}</strong></p>
      <p>{question.answer}</p>
    </div>
  {/each}
</main>

<style>
  h2 { text-transform: uppercase; }
  .question { margin-bottom: 2em; }
</style>
