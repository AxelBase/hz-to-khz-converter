<script>
  import { fly } from 'svelte/transition';
  
  let hz = '';
  let khz = '';

  function updateFromHz() {
    if (hz === '' || isNaN(Number(hz))) {
      khz = '0.00000';
    } else {
      const value = Number(hz) / 1000;
      khz = value.toFixed(5);
    }
  }

  function updateFromKhz() {
    if (khz === '' || isNaN(Number(khz))) {
      hz = '0.00000';
    } else {
      const value = Number(khz) * 1000;
      hz = value.toFixed(5);
    }
  }
</script>

<section id="converter" class="py-5 mt-4" in:fly={{ y: 30, duration: 800 }}>
  <div class="container text-center mb-5">
    <h1 class="display-4 fw-bold mb-3 bubble-text">Frequency Converter</h1>
    <p class="text-muted mx-auto" style="max-width: 600px;">
      A professional-grade, real-time bidirectional frequency tool.
    </p>
  </div>

  <div class="row justify-content-center px-3">
    <div class="col-12 col-md-8 col-lg-5">
      <div class="card p-4 p-md-5">
        
        <div class="mb-4">
          <label for="hz-input" class="form-label fw-bold">Hertz (Hz)</label>
          <input
            id="hz-input"
            type="number"
            class="form-control form-control-lg text-center"
            placeholder="0.00000"
            bind:value={hz}
            on:input={updateFromHz}
          />
        </div>

        <div class="text-center my-2">
          <div class="swap-icon">⇅</div>
        </div>

        <div class="mb-4">
          <label for="khz-input" class="form-label fw-bold">Kilohertz (kHz)</label>
          <input
            id="khz-input"
            type="number"
            class="form-control form-control-lg text-center"
            placeholder="0.00000"
            bind:value={khz}
            on:input={updateFromKhz}
          />
        </div>

        <div class="info-tag text-center mt-3">
          <span class="badge rounded-pill bg-light text-primary p-2 px-3">1 kHz = 1000 Hz</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="container mb-5">
    <hr class="opacity-10 my-5">

<section id="about" class="py-5">
  <div class="container">
    <h2 class="fw-bold mb-4 text-center">About the Hz to kHz Converter</h2>
    <div class="row justify-content-center">
      <div class="col-lg-10">
        <div class="card p-5 shadow-sm border-0">
          <p>The <strong>Hz to kHz Converter</strong> is a minimalist, high-precision web utility designed for anyone who needs fast and accurate frequency conversion between Hertz and Kilohertz. Built as a completely client-side static application, it delivers live bidirectional updates with results shown to exactly five decimal places.</p>

          <p>Frequency measurements are fundamental in audio engineering, radio communications, signal processing, electronics, and scientific research. Whether you are tuning audio filters, calibrating oscillators, analyzing waveforms, or verifying laboratory data, small differences in frequency values can have a significant impact. This tool eliminates manual calculation errors by providing instant, mathematically precise conversion the moment you type.</p>

          <p>Unlike traditional calculators or complex software, this converter runs entirely in your browser. No data is sent to any server, no accounts are required, and the tool works offline after the initial page load. The strict focus on simplicity and accuracy aligns with the core principle of delivering reliable results without unnecessary features or distractions.</p>

          <p>The converter supports real-time typing in either field. Enter a value in Hertz and watch the Kilohertz equivalent appear instantly, or start in Kilohertz and see the Hertz value update live. Empty or invalid inputs gracefully default to 0.00000, ensuring the interface remains stable and user-friendly at all times.</p>

          <p>Precision to five decimal places was chosen deliberately. It provides enough resolution for professional technical work while keeping numbers readable. The underlying calculations use full floating-point precision before final formatting, minimizing rounding errors that commonly occur with repeated manual conversions.</p>

          <p>This tool is ideal for students learning electronics, hobbyists building audio projects, engineers working on radio equipment, and researchers handling vibration or electromagnetic measurements. Its clean interface and responsive design work smoothly on both desktop and mobile devices.</p>

          <p>By removing friction from frequency unit conversion, the Hz to kHz Converter helps users focus on their actual work — whether designing circuits, adjusting sound systems, or analyzing signals — with confidence in the accuracy of every result.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="how-to-use" class="py-5 bg-light">
  <div class="container">
    <h2 class="fw-bold mb-4 text-center">How to Use the Hz to kHz Converter</h2>
    <div class="row g-4">
      <div class="col-md-4">
        <div class="card p-4 h-100 shadow-sm border-0">
          <h5 class="fw-bold mb-3">1. Enter Your Value</h5>
          <p class="text-muted">Simply click into either the Hertz (Hz) or Kilohertz (kHz) input field and start typing. The large, centered input boxes make it easy to enter both small fractions and large frequency values. You can begin in whichever unit feels most natural for your current task.</p>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card p-4 h-100 shadow-sm border-0">
          <h5 class="fw-bold mb-3">2. Watch Live Conversion</h5>
          <p class="text-muted">As you type, the opposite field updates instantly. Type in Hz and the kHz value appears immediately. Switch to the kHz field and the Hz equivalent updates in real time. The bidirectional live sync eliminates the need to press any button or refresh the page.</p>
        </div>
      </div>
      <div class="col-md-4">
        <div class="card p-4 h-100 shadow-sm border-0">
          <h5 class="fw-bold mb-3">3. Copy Precise Results</h5>
          <p class="text-muted">All output is formatted to exactly five decimal places for maximum accuracy. Copy the result directly from the input field and paste it into your documents, spreadsheets, or reports. The tool automatically handles invalid entries by showing 0.00000, keeping your workflow uninterrupted.</p>
        </div>
      </div>
    </div>

    <div class="mt-5">
      <p class="lead text-center">Additional Tips:</p>
      <ul class="list-unstyled text-muted mx-auto" style="max-width: 700px;">
        <li class="mb-2"><strong>Auto-focus:</strong> The Hz field receives focus automatically when the page loads.</li>
        <li class="mb-2"><strong>Mobile friendly:</strong> The interface stacks cleanly on phones and tablets.</li>
        <li class="mb-2"><strong>Wide range support:</strong> Works with very small fractions and large frequencies.</li>
        <li><strong>No installation:</strong> Just open the page and start converting — works offline after loading.</li>
      </ul>
    </div>

  </div>
</section>

<section id="faq" class="py-5">
  <div class="container">
    <h2 class="fw-bold mb-4 text-center">Frequently Asked Questions</h2>
    <div class="accordion" id="faqAccordion">

      <div class="accordion-item border-0 card mb-3 shadow-sm">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed fw-bold bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#q1">
            Is the Hz to kHz Converter completely free?
          </button>
        </h2>
        <div id="q1" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
          <div class="accordion-body text-muted">
            Yes, the tool is completely free to use with no hidden limits or premium features. It is provided as a public utility for students, engineers, hobbyists, and professionals who need quick and accurate frequency conversion.
          </div>
        </div>
      </div>

      <div class="accordion-item border-0 card mb-3 shadow-sm">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed fw-bold bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#q2">
            Does it really update live as I type?
          </button>
        </h2>
        <div id="q2" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
          <div class="accordion-body text-muted">
            Yes. The converter uses real-time event handling so the opposite field updates instantly with every keystroke. There is no need to click any button. The experience is smooth and responsive on both desktop and mobile browsers.
          </div>
        </div>
      </div>

      <div class="accordion-item border-0 card mb-3 shadow-sm">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed fw-bold bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#q3">
            Why show results to exactly five decimal places?
          </button>
        </h2>
        <div id="q3" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
          <div class="accordion-body text-muted">
            Five decimal places provide the right balance between readability and technical precision. It captures fine differences needed in audio, radio, and scientific work while preventing the small rounding errors common in basic calculators.
          </div>
        </div>
      </div>

      <div class="accordion-item border-0 card mb-3 shadow-sm">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed fw-bold bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#q4">
            Is my data private when using the converter?
          </button>
        </h2>
        <div id="q4" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
          <div class="accordion-body text-muted">
            Absolutely. The entire application runs client-side in your browser. No frequency values you enter are sent to any server, stored, or tracked. Your inputs remain completely private on your device.
          </div>
        </div>
      </div>

      <div class="accordion-item border-0 card mb-3 shadow-sm">
        <h2 class="accordion-header">
          <button class="accordion-button collapsed fw-bold bg-white" type="button" data-bs-toggle="collapse" data-bs-target="#q5">
            Does it work offline?
          </button>
        </h2>
        <div id="q5" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
          <div class="accordion-body text-muted">
            Yes. Once the page has loaded, the converter works fully offline. All calculations are performed locally using JavaScript, making it reliable even in areas with limited internet access.
          </div>
        </div>
      </div>

    </div>

  </div>
</section>

</div>

<style>
  .bubble-text {
    background: linear-gradient(45deg, #1e293b, #6366f1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .swap-icon {
    font-size: 2rem;
    color: var(--brand-primary);
    opacity: 0.5;
    transition: var(--bubbly-transition);
  }

  .card:hover .swap-icon {
    opacity: 1;
    transform: rotate(180deg);
  }

  .accordion-button:not(.collapsed) {
    color: var(--brand-primary);
    background-color: #f8fafc;
    box-shadow: none;
  }

  .accordion-button:focus {
    box-shadow: none;
  }
</style>