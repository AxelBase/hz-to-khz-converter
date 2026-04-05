<script lang="ts">
  import { base } from '$app/paths';
</script>

<svelte:head>
  <title>Privacy Policy | Hz to kHz Converter</title>
  <meta name="description" content="Our Privacy Policy explains how the Hz to kHz Converter protects your privacy with a complete no-data-collection approach." />
  <meta property="og:title" content="Privacy Policy | Hz to kHz Converter" />
  <meta property="og:description" content="Our Privacy Policy explains how the Hz to kHz Converter protects your privacy with a complete no-data-collection approach." />
  <meta property="og:url" content="{base}/privacy" />
  <meta property="og:type" content="article" />
  <meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<div class="container fade-in post-layout">
  <div class="breadcrumbs">
    <a href="{base}/">Home</a>
    <span>/</span>
    <p>Privacy Policy</p>
  </div>

  <article class="prose">
    <h1>Privacy Policy</h1>

    <p class="post-meta">Effective Date: April 06, 2026</p>

    <h2>1. Introduction</h2>
    <p>Welcome to the <strong>Hz to kHz Converter</strong>, a simple, client-side web utility. This Privacy Policy explains how we handle your information when you use our tool. We are committed to protecting your privacy and operate on a strict <strong>privacy-first principle</strong>.</p>

    <p>Because the converter runs entirely in your browser, <strong>we do not collect, store, or process any personal data</strong>. All calculations happen locally on your device. This policy is designed to be transparent about our zero-data-collection approach.</p>

    <h2>2. Information We Do Not Collect</h2>
    <p>The Hz to kHz Converter does not collect any of the following:</p>
    <ul>
      <li><strong>Personal Identifiable Information (PII)</strong> — names, email addresses, or any contact details.</li>
      <li><strong>Usage Data</strong> — IP addresses, browser type, device information, or location data.</li>
      <li><strong>Input Data</strong> — any frequency values you enter in Hz or kHz fields.</li>
      <li><strong>Analytics or Tracking Data</strong> — we do not use cookies, Google Analytics, pixels, or any tracking technologies.</li>
    </ul>
    <p>All conversion operations are performed <strong>client-side only</strong>. Your entered values never leave your device.</p>

    <h2>3. How the Tool Works</h2>
    <p>When you use the converter:</p>
    <ul>
      <li>You type values directly into the input fields.</li>
      <li>Real-time bidirectional conversion happens instantly using JavaScript in your browser.</li>
      <li>Results are displayed to five decimal places without any data being sent to external servers.</li>
      <li>The tool is completely <strong>stateless</strong> — no data is saved between sessions.</li>
    </ul>
    <p>Your frequency inputs remain private at all times.</p>

    <h2>4. Third-Party Services</h2>
    <p>We do not integrate any third-party services that collect data. The site uses Bootstrap via CDN for styling only. No analytics, advertising, or tracking scripts are present. Any interaction with the page stays entirely on your device.</p>

    <h2>5. Cookies and Tracking</h2>
    <p>The Hz to kHz Converter <strong>does not use cookies</strong> or any tracking technologies. Your session is fully stateless and private.</p>

    <h2>6. Data Security</h2>
    <p>Although we collect no data, we recommend you follow good security practices:</p>
    <ul>
      <li>Use up-to-date browsers and operating systems.</li>
      <li>Clear browser data when working with sensitive calculations.</li>
      <li>Avoid using the tool on shared or public computers for confidential work.</li>
    </ul>

    <h2>7. Children’s Privacy</h2>
    <p>This tool is suitable for general audiences and not specifically directed at children under 13. We do not knowingly collect any information from children.</p>

    <h2>8. International Users</h2>
    <p>Since no personal data is collected, the tool complies by design with major privacy regulations including <strong>GDPR</strong>, <strong>CCPA</strong>, and similar laws worldwide.</p>

    <h2>9. Changes to This Policy</h2>
    <p>We may update this Privacy Policy occasionally. Any changes will be posted on this page with a new effective date. Continued use of the tool after changes constitutes acceptance of the updated policy.</p>

    <h2>10. Contact Us</h2>
    <p>If you have any questions about this Privacy Policy, feel free to reach out via the GitHub repository linked in the footer.</p>

    <p class="italic-note">This Privacy Policy reflects our strong commitment to <strong>zero data collection</strong> and user privacy. By using the Hz to kHz Converter, you agree to these practices.</p>
  </article>
</div>

<style>
  .post-layout {
    max-width: 800px;
    padding-top: 2rem;
    padding-bottom: 4rem;
  }

  .breadcrumbs {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    margin-bottom: 1.5rem;
    font-size: 0.9rem;
    color: var(--text-secondary);
  }
  .breadcrumbs a {
    color: var(--accent-secondary);
  }
  .breadcrumbs a:hover {
    text-decoration: underline;
  }
  .breadcrumbs p {
    margin: 0;
  }

  .prose {
    line-height: 1.8;
  }

  .prose .post-meta {
    color: var(--text-secondary);
    font-size: 0.9rem;
    margin-bottom: 2rem;
    border-bottom: 1px solid var(--border-color);
    padding-bottom: 1rem;
  }

  .prose h1, .prose h2 {
    color: var(--brand-blue);
  }

  .prose h1 {
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
  }

  .prose h2 {
    margin-top: 2.5rem;
    border-bottom: 1px solid #dee2e6;
    padding-bottom: 0.5rem;
  }

  .prose p {
    color: var(--text-primary);
  }

  .prose ul {
    list-style-type: '→ ';
    padding-left: 1.5rem;
    color: var(--text-primary);
  }

  .prose .italic-note {
    font-style: italic;
    color: var(--text-secondary);
    text-align: center;
    margin-top: 3rem;
  }
</style>