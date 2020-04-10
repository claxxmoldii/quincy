<script type="text/javascript">
  import AvecCui from './cubeys/AvecCui.svelte';
  import PorQui from './cubeys/PorQui.svelte';
  import Quoi from './cubeys/Quoi.svelte';
  import Qui from './cubeys/Qui.svelte';

  let isSecondTierBgImage = 'images/sabri-tuzcu-wunVFNvqhfE-unsplash.jpg';
  let isThirdTierBgImage = 'images/thought-catalog-505eectW54k-unsplash.jpg';
</script>

<style type="text/css">
  .landing {
    max-width: 100vw;
    overflow-x: hidden;
  }

  .isGrid {
    display: grid;
  }

  .isTitleBlock {
    grid-template-columns: 1fr 1fr;
    height: 50vh;
    background-color: gainsboro;
  }

  .isTitleBlock div {
    height: 100%;
    width: 100%;
    display: grid;
    place-items: center center;
  }

  .isTitleBlock .description {
    width: 400px;
  }

  .isTitleBlock div:nth-of-type(2n) {
    border-left: solid .5px darkgray;
  }

  .isTitle {
    font-family: 'Cinzel', serif;
  }

  .isTitle * {
    margin: 0;
    color:  indianred;
    font-weight: bold;
  }

  .isTitle h1 {
    font-size: 3rem;
  }

  .isTitle h3 {
    font-size: 2rem;
  }

  .isDescription {
    width: 400px;
  }

  .isDescription span {
    font-weight: bold;
  }

  .hasBgImage {
    background: no-repeat center center;
    background-size: cover;
  }

  .isSecondTier {
    height: 80vh;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: 40vh, 40vh;
    grid-template-areas:
      ". empty empty avecQui"
      ". pourQui quoi aVos";
  }

  .isCubey {
    display: grid;
    background-color: whitesmoke;
    border-left: solid .5px darkgray;
    place-items: center center;
    text-align: center;
  }

  .isAvecCui {
    grid-area: avecQui;
  }

  .isPourQui {
    grid-area: pourQui;
  }

  .isQuoi {
    grid-area: quoi;
  }

  .isaVos {
    grid-area: aVos;
    background-color: palevioletred;
  }

  .isaVos h3 {
    font-size: 2rem;
    color: #eee;
  }

  .isaVos span {
    font-size: 5rem;
    font-weight: 700;
  }

  .isEmpty {
    grid-area: empty;
  }

  .isEmpty.isCubey {
    background-color: transparent;
  }

  .isThirdTier {
    height: 80vh;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: 40vh, 40vh;
    grid-template-areas:
      "qui quote . ."
      "block block . ."
  }

  .isCounterCubey {
    display: grid;
    background-color: whitesmoke;
    /*border: solid 1px crimson;*/
    border-right: solid .5px darkgray;
    /*border-left: solid .5px crimson;*/
    place-items: center center;
    text-align: center;
  }

  .isQui {
    grid-area: qui;
    height: 40vh;
  }

  .isQuote {
    grid-area: quote;
    background-color: palevioletred;
    height: 40vh;
    color: white;
  }

  .isQuote q:before {
  color: white;
  content: open-quote;
  font-size: 4em;
  line-height: 0.1em;
  margin-right: 0.25em;
  vertical-align: -0.4em;
}

  .isBlock {
    grid-area: block;
    background-color: gainsboro;
    height: 40vh;
    /*width: 25%;*/
    border-right: solid .5px darkgray;
  }

  .isBufferBlock {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: 10vh;
    /*background-color: pink;*/
  }

  .isBufferBlockBlock {
    border-right: solid .5px darkgray;
  }

  .isBufferBlockBlock:last-of-type {
    border: none;
  }
</style>


<section class="landing">
  <div class="isGrid isTitleBlock">
    <div>
      <header class="isTitle">
        <h1>betts/</h1>
        <h1>trillana</h1>
        <h3>& associates</h3>
      </header>
    </div>
    <div>
      <p class="isDescription">
        <span>Corporate communications – Web presence</span> → an independent content strategy firm with offices in Parañaque and Cainta, our operation provides solutions for mostly technology firms, focusing on corporate communications to build stronger brands.
      </p>
    </div>
  </div>

  <div class="isGrid isSecondTier hasBgImage" style="background-image: url({isSecondTierBgImage});">

    <div class="isAvecCui isCubey isLink">
      <AvecCui />
    </div>

    <div class="isPourQui isCubey isLink">
      <PorQui />
    </div>

    <div class="isQuoi isCubey isLink">
      <Quoi />
    </div>


    <div class="isaVos isCubey">
      <div>
        <h3>established<br/>
            -<br/>
            <span>2010</span><br/>
          p'que - cainta</h3>
      </div>
    </div>
    <div class="isEmpty isCubey"></div>
    <div class="isEmpty isCubey"></div>
  </div>

  <div class="isGrid isThirdTier hasBgImage" style="background-image: url({isThirdTierBgImage});">



    <div class="isQui isCubey isLink">
      <Qui />
    </div>



    <div class="isQuote isCounterCubey">
      <div>
        <q>
          our firm is at your side in all stages of your campaign, its creation, its development, its deployment.
        </q>
      </div>
    </div>
    <div class="isBlock"></div>
    <div class="isBlock"></div>
  </div>

  <div class="isBufferBlock">
    <div class="isBufferBlockBlock"></div>
    <div class="isBufferBlockBlock"></div>
    <div class="isBufferBlockBlock"></div>
    <div class="isBufferBlockBlock"></div>
  </div>
</section>

