<script>
  let mobileMenuOpen = false;

  function toggleMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
</script>

<nav class="nav">
  <div class="nav-container">
    <div class="nav-content">
      <!-- Logo -->
      <div class="nav-brand">
        <img
          src="https://cloudassetskita.com/uploads/23709lfny-statue-color-on-black-2648fc67.png"
          alt="Paul's Live From New York Pizza Logo"
          class="nav-logo"
          width="56"
          height="56"
          loading="eager"
        />
        <a href="/" class="nav-title">Paul's Live From NY Pizza</a>
      </div>

      <!-- Desktop Menu -->
      <div class="nav-links">
        <a href="/" class="nav-link">Home</a>
        <a href="/menu" class="nav-link">Menu</a>
        <a href="/locations" class="nav-link">Locations</a>
        <a href="/about" class="nav-link">About</a>
        <a href="/contact" class="nav-link">Contact</a>
        <a
          href="https://paulslivefromnewyorkpizza.com/"
          target="_blank"
          rel="noopener noreferrer"
          class="nav-cta"
        >
          Order Online
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <button
        class="mobile-menu-btn"
        on:click={toggleMenu}
        aria-label="Toggle mobile menu"
        aria-expanded={mobileMenuOpen}
      >
        {#if mobileMenuOpen}
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="28"
            height="28"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <line x1="18" y1="6" x2="6" y2="18"></line>
            <line x1="6" y1="6" x2="18" y2="18"></line>
          </svg>
        {:else}
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="28"
            height="28"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <line x1="3" y1="12" x2="21" y2="12"></line>
            <line x1="3" y1="6" x2="21" y2="6"></line>
            <line x1="3" y1="18" x2="21" y2="18"></line>
          </svg>
        {/if}
      </button>
    </div>

    <!-- Mobile Menu -->
    {#if mobileMenuOpen}
      <div class="mobile-menu">
        <a href="/" class="mobile-link" on:click={toggleMenu}>Home</a>
        <a href="/menu" class="mobile-link" on:click={toggleMenu}>Menu</a>
        <a href="/locations" class="mobile-link" on:click={toggleMenu}
          >Locations</a
        >
        <a href="/about" class="mobile-link" on:click={toggleMenu}>About</a>
        <a href="/contact" class="mobile-link" on:click={toggleMenu}>Contact</a>
        <a
          href="https://paulslivefromnewyorkpizza.com/"
          target="_blank"
          rel="noopener noreferrer"
          class="mobile-cta"
        >
          Order Online
        </a>
      </div>
    {/if}
  </div>
</nav>

<style>
  .nav {
    background-color: var(--color-pizza-dark);
    color: white;
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  }

  .nav-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .nav-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
  }

  .nav-brand {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .nav-logo {
    height: 56px;
    width: auto;
  }

  .nav-title {
    font-family: var(--font-heading);
    font-size: 1.25rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: white;
  }

  @media (max-width: 768px) {
    .nav-title {
      font-size: 1rem;
    }
  }

  .nav-links {
    display: flex;
    align-items: center;
    gap: 2rem;
  }

  @media (max-width: 900px) {
    .nav-links {
      display: none;
    }
  }

  .nav-link {
    font-weight: 700;
    transition: color 0.15s ease;
  }

  .nav-link:hover {
    color: var(--color-pizza-red);
  }

  .nav-cta {
    background-color: var(--color-pizza-red);
    color: white;
    padding: 0.5rem 1.25rem;
    border-radius: 4px;
    font-size: 0.875rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    transition: background-color 0.15s ease;
  }

  .nav-cta:hover {
    background-color: var(--color-pizza-red-dark);
  }

  .mobile-menu-btn {
    display: none;
    background: none;
    border: none;
    color: white;
    cursor: pointer;
    padding: 0.5rem;
  }

  @media (max-width: 900px) {
    .mobile-menu-btn {
      display: block;
    }
  }

  .mobile-menu {
    display: flex;
    flex-direction: column;
    padding: 1rem;
    gap: 1rem;
    background-color: #111;
    border-top: 1px solid #333;
    text-align: center;
  }

  .mobile-link {
    font-weight: 700;
    padding: 0.5rem;
    transition: color 0.15s ease;
  }

  .mobile-link:hover {
    color: var(--color-pizza-red);
  }

  .mobile-cta {
    background-color: var(--color-pizza-red);
    color: white;
    padding: 0.75rem;
    border-radius: 4px;
    font-weight: 700;
    text-transform: uppercase;
  }
</style>
