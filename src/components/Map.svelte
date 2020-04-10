<script>
  import { onMount } from 'svelte';

  import Offices from './Offices.svelte';
   // import mapStyles from './map-styles'; // optional

  let container;
  let map;
  let zoom = 16;
  let parañaque = {lat: 14.486942, lng: 121.043405};
  let cainta = {lat: 14.616807, lng: 121.101018};
  let center = parañaque;
  let current = 'parañaque';

  const parañaqueMarker = new google.maps.Marker({
    position: parañaque,
    map: map
  });

  const caintaMarker = new google.maps.Marker({
    position: cainta,
    map: map
  });

  function goParañaque() {
    current = 'parañaque';
    map.setCenter(parañaque);
  }

  function goCainta() {
    current = 'cainta';
    map.setCenter(cainta);
  }

  onMount(async () => {
    map = new google.maps.Map(container, {
      zoom,
      center
    });
    parañaqueMarker.setMap(map);
    caintaMarker.setMap(map);
  });
</script>

<style>
  .isMap {
    max-width: 100vw;
    /*position: relative;*/
    /*margin-bottom: 40px;*/
    overflow-x: hidden;
  }

  .griido {
    display: grid;
    grid-template-columns: 100vw;
    height: 80vh;
  }

  .griido div {
    grid-row-start: 1;
    grid-column-start: 1;
  }

  .isTheMap {
    width: 100%;
    height: 100%;
    z-index: 0;
    overflow-x: hidden;
    filter: grayscale(99%); /*grayscale fx*/
  }

  .isOverlay {
    width: 100%;
    height: 100%;
    z-index: 100;
  }

  .isBlocks {
    display: flex;
  }

  .isBlock {
    border-right: solid .5px darkgray;
    grid-area: block;
    height: 80vh;
    width: 25vw;
  }

  .isBlock:last-of-type {
    border: none;
  }

  .isOu {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40vh;
    width: 100%;
    background-color: palevioletred;
  }

  .isOu h5 {
    font-size: 1.8rem;
    font-weight: 400;
    color: white;
    border-bottom: solid 1px white;
    display: inline-block;
    padding-bottom: 15px;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    margin-bottom: 15px;
  }

  .isOu h4, h5, p, span {
    text-align: center;
    margin: 0;
  }

  button {
    font-size: 100%;
    font-family: inherit;
    font-weight: 300;
    border: 0;
    padding: 0;
  }

  button:hover {
    color: white;
  }

  a {
    text-decoration: none;
    color: inherit;
  }

  a:hover {
    color: white;
  }

  .active {
    color: white;
  }
</style>

<section class="isMap">
  <div class="griido">
    <div class="isTheMap" bind:this={container}></div>

    <div class="isOverlay">
      <div class="isBlocks">
        <div class="isBlock"></div>
        <div class="isBlock"></div>
        <div class="isBlock"></div>
        <div class="isBlock">
          <div class="isOu">
            <div class="isKontenner">
              <h5>ou?</h5>
              <h4>
                <button
                  class:active="{current === 'parañaque'}"
                  on:click="{goParañaque}">
                  parañaque
                </button>
                -
                <button
                  class:active="{current === 'cainta'}"
                  on:click="{goCainta}">
                  cainta
                </button>
              </h4>
              <p><a href="">- & -<br/>
                chez vous!</a></p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <Offices
    on:mapToCainta={goCainta}
    on:mapToParañaque={goParañaque}
    current = {current}/>
</section>
