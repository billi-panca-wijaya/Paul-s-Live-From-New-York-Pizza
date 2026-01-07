<script>
  export let address;
  export let city;
  export let state;
  export let zip;

  let mapLoaded = false;

  $: encodedAddress = encodeURIComponent(
    `${address}, ${city}, ${state} ${zip}`
  );
  $: mapSrc = `https://www.google.com/maps/embed/v1/place?key=AIzaSyBFw0Qbyq9zTFTd-tUY6dZWTgaQzuU17R8&q=${encodedAddress}`;

  function loadMap() {
    mapLoaded = true;
  }
</script>

<div class="map-container">
  {#if mapLoaded}
    <iframe
      src={mapSrc}
      class="map-iframe"
      title={`Map showing ${address}, ${city}`}
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
      allowfullscreen
    ></iframe>
  {:else}
    <button class="map-placeholder" on:click={loadMap}>
      <div class="placeholder-content">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="48"
          height="48"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="1.5"
        >
          <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
          <circle cx="12" cy="10" r="3"></circle>
        </svg>
        <span class="placeholder-text">Click to load map</span>
        <span class="placeholder-address">{address}, {city}</span>
      </div>
    </button>
  {/if}
</div>

<style>
  .map-container {
    width: 100%;
    height: 200px;
    border-radius: 8px;
    overflow: hidden;
    margin-top: 1rem;
  }

  .map-iframe {
    width: 100%;
    height: 100%;
    border: none;
  }

  .map-placeholder {
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #374151 0%, #1f2937 100%);
    border: 2px dashed #4b5563;
    border-radius: 8px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease;
  }

  .map-placeholder:hover {
    background: linear-gradient(135deg, #4b5563 0%, #374151 100%);
    border-color: var(--color-pizza-red);
  }

  .placeholder-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: #9ca3af;
  }

  .map-placeholder:hover .placeholder-content {
    color: white;
  }

  .placeholder-text {
    font-size: 0.875rem;
    font-weight: 600;
  }

  .placeholder-address {
    font-size: 0.75rem;
    opacity: 0.7;
  }
</style>
