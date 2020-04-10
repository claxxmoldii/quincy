<script>
  import Landing from './components/Landing.svelte';
  import Questions from './components/Questions.svelte';
  import Map from './components/Map.svelte';
  import Contact from './components/Contact.svelte';

  export let ready;
</script>

<svelte:head>
  <script async defer src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD5Q0YlpqyE1q2XOTn7bkCmzBK0DtdcUPc&callback=initMap">
  </script>
</svelte:head>

<style>
  :global(body) {
    padding: 0;
  }

  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<Landing/>
<Questions/>

{ #if ready }
<Map></Map>
{/if}

<Contact/>

