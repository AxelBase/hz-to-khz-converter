<script lang="ts">
  import "../app.css";
  import { base } from '$app/paths';
  import { fly } from 'svelte/transition';

  const currentYear = new Date().getFullYear();
  let isDropdownOpen = false;

  function toggleDropdown() { isDropdownOpen = !isDropdownOpen; }
  function closeDropdown() { isDropdownOpen = false; }

  function clickOutside(node: HTMLElement) {
    const handleClick = (event: MouseEvent) => {
      if (node && !node.contains(event.target as Node)) {
        node.dispatchEvent(new CustomEvent('click_outside'));
      }
    };
    document.addEventListener('click', handleClick, true);
    return {
      destroy() { document.removeEventListener('click', handleClick, true); }
    };
  }
</script>

<header class="sticky-top custom-navbar p-3">
  <nav class="container bubbly-nav d-flex justify-content-between align-items-center py-2 px-4 shadow-sm">
    <div class="d-flex align-items-center gap-4">
      <a href="{base}/" class="d-flex align-items-center text-decoration-none">
        <img src="{base}/AxelLab-Logo.ico" alt="Logo" style="height: 40px;" class="me-2 logo-hover" />
        <span class="fw-bold fs-3 brand-text" style="font-family: 'Poppins', sans-serif;">AxelBase</span>
      </a>

      <div class="position-relative" use:clickOutside on:click_outside={closeDropdown}>
        <button 
          class="bmac-button d-flex align-items-center gap-2 text-white border-0 px-4 py-2 rounded-pill shadow-sm"
          on:click={toggleDropdown}
          aria-label="Support options"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M2,21V19H20V21H2M20,8V5H4V8H20M20,10H4V13C4,14.38 4.5,15.63 5.31,16.58L11.64,19H12.36L18.69,16.58C19.5,15.63 20,14.38 20,13V10M16,2H8V4H16V2Z" />
          </svg>
          <span class="d-none d-sm-inline fw-semibold">Buy me a Coffee</span>
          <span class="d-sm-none fw-semibold">Coffee</span>
        </button>

        {#if isDropdownOpen}
          <div class="bmac-dropdown mt-2" transition:fly={{ y: -10, duration: 250 }}>
            <a href="https://buymeacoffee.com/axelbase" target="_blank" rel="noopener" on:click={closeDropdown}>
              <span class="amount">$3</span> One Coffee
            </a>
            <a href="https://buymeacoffee.com/axelbase" target="_blank" rel="noopener" on:click={closeDropdown}>
              <span class="amount">$5</span> Two Coffees
            </a>
            <a href="https://buymeacoffee.com/axelbase" target="_blank" rel="noopener" on:click={closeDropdown}>
              <span class="amount">$10</span> Three Coffees
            </a>
            <a href="https://buymeacoffee.com/axelbase" target="_blank" rel="noopener" on:click={closeDropdown} class="custom-amount">
              Custom Amount
            </a>
            <a
              href="bitcoin:bc1q3p0e6vt492m4w4fpz5m2cl4zcfuqqkgaj6myc9?label=AxelBase&message=Buy%20me%20a%20coffee"
              on:click={closeDropdown}
              class="custom-amount"
            >
              Buy via Crypto (Bitcoin)
            </a>
          </div>
        {/if}
      </div>
    </div>

    <ul class="d-none d-lg-flex align-items-center gap-4 m-0 list-unstyled">
      <li><a class="nav-link-custom" href="{base}/">Home</a></li>
      <li><a class="nav-link-custom" href="{base}/#about">About</a></li>
      <li><a class="nav-link-custom" href="{base}/#how-to-use">How to Use</a></li>
      <li><a class="nav-link-custom" href="{base}/#faq">FAQ</a></li>
      <li><a class="nav-link-custom blog-link" href="{base}/blog">Blog</a></li>
    </ul>
  </nav>
</header>

<main>
  <slot />
</main>

<footer class="pb-5 mt-5">
  <div class="container">
    <div class="bubbly-footer p-4 px-md-5 shadow-sm d-flex flex-column flex-md-row justify-content-between align-items-center">
      <p class="m-0 text-muted">© {currentYear} <strong>AxelBase</strong> Hz to kHz Converter</p>
      <div class="d-flex gap-4 mt-3 mt-md-0">
        <a href="{base}/privacy" class="footer-link-custom">Privacy Policy</a>
        <a href="{base}/terms" class="footer-link-custom">Terms & Conditions</a>
      </div>
    </div>
  </div>
</footer>

<style>
  /* Bubbly Header & Nav */
  .custom-navbar {
    background: transparent;
  }
  
  .bubbly-nav {
    background: rgba(255, 255, 255, 0.85);
    backdrop-filter: blur(12px);
    border-radius: 50px;
    border: 1px solid rgba(255, 255, 255, 0.3);
  }

  .brand-text {
    color: var(--brand-primary);
    letter-spacing: -0.5px;
  }

  .logo-hover { transition: transform 0.3s ease; }
  .logo-hover:hover { transform: scale(1.1) rotate(5deg); }

  /* Nav Links Styling */
  .nav-link-custom {
    color: #475569;
    font-weight: 600;
    font-size: 0.95rem;
    text-decoration: none;
    transition: var(--bubbly-transition);
  }
  
  .nav-link-custom:hover {
    color: var(--brand-primary);
    transform: translateY(-2px);
  }

  .blog-link {
    background: var(--brand-primary);
    color: white !important;
    padding: 6px 18px;
    border-radius: 50px;
  }

  /* BMAC Button - Sample Styling with Ocean Blue coloring */
  .bmac-button {
    background: var(--brand-primary);
    font-size: 0.95rem;
    transition: var(--bubbly-transition);
  }
  
  .bmac-button:hover {
    background: var(--brand-accent);
    transform: translateY(-2px) scale(1.02);
    box-shadow: 0 8px 20px rgba(29, 51, 74, 0.2);
  }

  /* BMAC Dropdown */
  .bmac-dropdown {
    position: absolute;
    top: 100%;
    left: 50%;
    transform: translateX(-50%);
    width: 240px;
    background: white;
    border-radius: 20px;
    box-shadow: 0 15px 35px rgba(29, 51, 74, 0.15);
    overflow: hidden;
    border: 1px solid rgba(29, 51, 74, 0.05);
    z-index: 1000;
  }

  .bmac-dropdown a {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 14px 20px;
    color: #334155;
    text-decoration: none;
    font-size: 0.95rem;
    transition: all 0.2s ease;
  }

  .bmac-dropdown a:hover {
    background: #f1f5f9;
    color: var(--brand-primary);
    padding-left: 25px;
  }

  .bmac-dropdown .amount {
    font-weight: 700;
    color: var(--brand-success);
    font-size: 1.05rem;
  }

  .bmac-dropdown .custom-amount {
    font-weight: 600;
    color: var(--brand-primary);
    border-top: 1px solid #f1f5f9;
    justify-content: center !important;
  }

  /* Bubbly Footer */
  .bubbly-footer {
    background: rgba(255, 255, 255, 0.8);
    border-radius: 30px;
    border: 1px solid rgba(255, 255, 255, 0.5);
  }

  .footer-link-custom {
    text-decoration: none;
    color: #64748b;
    font-weight: 500;
    font-size: 0.9rem;
    transition: color 0.3s ease;
  }

  .footer-link-custom:hover {
    color: var(--brand-primary);
  }

  main { min-height: 80vh; }
</style>