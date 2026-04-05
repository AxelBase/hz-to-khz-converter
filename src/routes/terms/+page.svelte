<script lang="ts">
  import { base } from '$app/paths';
</script>

<svelte:head>
  <title>Terms and Conditions | Hz to kHz Converter</title>
  <meta name="description" content="Terms and Conditions for using the Hz to kHz Converter web utility." />
  <meta property="og:title" content="Terms and Conditions | Hz to kHz Converter" />
  <meta property="og:description" content="Terms and Conditions for using the Hz to kHz Converter web utility." />
  <meta property="og:url" content="{base}/terms" />
  <meta property="og:type" content="article" />
  <meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<div class="container fade-in post-layout">
  <div class="breadcrumbs">
    <a href="{base}/">Home</a>
    <span>/</span>
    <p>Terms and Conditions</p>
  </div>

  <article class="prose">
    <h1>Terms and Conditions</h1>

    <p class="post-meta">Effective Date: April 06, 2026</p>

    <h2>1. Introduction</h2>
    <p>Welcome to the <strong>Hz to kHz Converter</strong>. These Terms and Conditions govern your use of this free, client-side web utility. By accessing or using the tool, you agree to be bound by these terms. If you do not agree, please discontinue use immediately.</p>

    <h2>2. Description of Service</h2>
    <p>The Hz to kHz Converter is a simple, static, browser-based utility that performs live bidirectional conversion between Hertz (Hz) and Kilohertz (kHz) with five-decimal-place precision. All processing occurs locally in your browser. The tool is provided <strong>free of charge</strong> and <strong>as is</strong>.</p>

    <h2>3. Acceptable Use</h2>
    <p>You may use the converter for personal, educational, or professional purposes. You agree not to:</p>
    <ul>
      <li>Attempt to reverse engineer, modify, or redistribute the tool.</li>
      <li>Use the tool for any unlawful purpose.</li>
      <li>Remove or alter any copyright or attribution notices.</li>
    </ul>

    <h2>4. Accuracy and Limitations</h2>
    <p>While we strive for high accuracy using standard browser floating-point arithmetic, <strong>we make no warranties</strong> regarding the completeness, reliability, or suitability of the conversion results for any specific purpose. Results are provided for informational and convenience purposes only. You are responsible for verifying critical calculations independently.</p>

    <h2>5. No Data Collection</h2>
    <p>As a fully client-side application, we do not collect, store, or transmit any data you enter. Your inputs remain private on your device. Please refer to our <a href="{base}/privacy" style="color: var(--brand-blue);">Privacy Policy</a> for full details.</p>

    <h2>6. Intellectual Property</h2>
    <p>The design, layout, and code of the Hz to kHz Converter are protected by copyright. You may not copy, modify, or create derivative works without explicit permission, except for personal, non-commercial use.</p>

    <h2>7. Disclaimer of Warranties</h2>
    <p>The tool is provided <strong>“as is”</strong> and <strong>“as available”</strong> without any warranties of any kind, either express or implied. We do not guarantee uninterrupted or error-free operation.</p>

    <h2>8. Limitation of Liability</h2>
    <p>To the fullest extent permitted by law, we shall not be liable for any indirect, incidental, special, or consequential damages arising from your use of the converter.</p>

    <h2>9. Changes to Terms</h2>
    <p>We may update these Terms and Conditions at any time. Continued use of the tool after changes are posted constitutes your acceptance of the new terms.</p>

    <h2>10. Governing Law</h2>
    <p>These terms are governed by the laws of the jurisdiction in which you reside, without regard to conflict of law principles.</p>

    <h2>11. Contact</h2>
    <p>If you have any questions about these Terms and Conditions, please refer to the project on GitHub.</p>

    <p class="italic-note">By using the <strong>Hz to kHz Converter</strong>, you acknowledge that you have read, understood, and agreed to these Terms and Conditions.</p>
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