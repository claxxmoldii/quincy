<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  export let current = 'paris';

  let paris = true;
  let lyon = false;

  function goParis() {
    current = 'paris';
    dispatch('mapToParis');
  }

  function goLyon() {
    current = 'lyon';
    dispatch('mapToLyon');
  }
</script>

<style type="text/css">
  .isOffices {
    display: grid;
    grid-template-columns: 50vw 50vw;
  }

  .isOffices div:nth-of-type(1n) {
    border-right: solid .5px darkgray;
  }

  .isOffice {
    text-align: center;
    padding: 25px 0;
    position: relative;
  }

  .isOffice * {
    margin: 0;
  }

  .isHighlight {
    position: absolute;
    top: 0;
    height: 0;
    width: 100%;
    border-top: 4px solid palevioletred;
    opacity: 0;
  }

  .isOffice h4 {
    color: palevioletred;
    font-weight: 400;
  }

  .isOffice h6 {
    color: palevioletred;
    font-weight: 400;
    line-height: 1.8rem;
  }

  .isOffice h6:last-of-type {
    padding-bottom: 1.5rem;
  }

  .isAddress {
    font-size: .8em;
  }

  .isTel {
    padding-top: 1.5rem;
    font-size: 1.8rem
  }

/* --- helpers --- */
  .isDivider {
    font-family: 'Raleway', sans-serif;
    font-size: 3rem;
    font-weight: 100;
    color: dimgray;
  }

  .isOffice .isHighlight {
    animation: in .5s 1;
    animation-fill-mode: forwards;
  }

  .isOffice .isActive.isHighlight {
    animation: none;
  }

  .isActive {
    position: absolute;
    top: 0;
    height: 0;
    width: 100%;
    border-top: 4px solid palevioletred;
    opacity: 1;
  }

  @keyframes out {
    0% { opacity: 1; }
    100% { opacity: 0; }
  }

  @keyframes in {
    0% { opacity: 0; }
    100% { opacity: 1; }
  }
</style>

<div class="isOffices">
  <div class="isOffice"
    on:click="{goParis}"
    on:mouseenter="{() => paris = true}"
    on:mouseleave="{() => paris = false}"
    >
    <div class=""
      class:isActive="{current === 'paris'}"
      class:isHighlight="{paris}"
      ></div>
    <h4>Paris</h4>
      <span class="isDivider">—</span>
    <h6>Barreau de Paris</h6>
    <h6>8e arrondissement</h6>
    <p class="isAddress">17 rue du Colisée</p>
    <p class="isAddress">75008 PARIS</p>
    <p class="isTel">T. —> 01 42 25 42 30</p>
  </div>

  <div class="isOffice"
    on:click="{goLyon}"
    on:mouseenter="{() => lyon = true}"
    on:mouseleave="{() => lyon = false}">
    <h4>Lyon</h4>
    <div class=""
      class:isActive="{current === 'lyon'}"
      class:isHighlight="{lyon}"></div>
      <span class="isDivider">—</span>
    <h6>barreau de lyon</h6>
    <h6>Bureau Principal</h6>
    <p class="isAddress">PARC D'AFFAIRES DE CRÉCY, 17 avenue Charles de Gaulle</p>
    <p class="isAddress">69771 SAINT DIDIER AU MONT D'OR</p>
    <p class="isTel">T. —> 04 72 53 14 90F. —> 04 72 53 14 99</p>
  </div>
</div>
