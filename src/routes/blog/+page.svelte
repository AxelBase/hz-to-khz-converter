<script lang="ts">
  import { base } from '$app/paths';
  import { fly } from 'svelte/transition';

  const posts = [
    { 
      href: '/blog/posts/post1', 
      tag: 'Basics',
      title: 'Understanding Hertz and Kilohertz', 
      description: 'Learn the fundamental relationship between Hz and kHz and why the simple factor of 1000 matters in real-world measurements.',
      time: '3 min read'
    },
    { 
      href: '/blog/posts/post2', 
      tag: 'Precision',
      title: 'The Importance of Five-Decimal Precision', 
      description: 'Discover why displaying results to exactly five decimal places prevents rounding errors in engineering and audio.',
      time: '5 min read'
    },
    { 
      href: '/blog/posts/post3', 
      tag: 'Technical',
      title: 'How Live Bidirectional Conversion Works', 
      description: 'A technical look at real-time updating: how typing in either field instantly reflects the accurate converted value.',
      time: '4 min read'
    },
    { 
      href: '/blog/posts/post4', 
      tag: 'Usage',
      title: 'Practical Applications of Hz to kHz', 
      description: 'Explore where precise frequency conversion is essential—from audio engineering to signal processing.',
      time: '6 min read'
    },
    { 
      href: '/blog/posts/post5', 
      tag: 'Guide',
      title: 'Avoiding Common Pitfalls in Conversion', 
      description: 'Learn how small mistakes in handling decimals can lead to inaccurate results and how this tool prevents them.',
      time: '4 min read'
    },
    { 
      href: '/blog/posts/post6', 
      tag: 'Math',
      title: 'Floating-Point Precision in Browsers', 
      description: 'Understand how JavaScript handles the math behind the conversion to deliver mathematically exact results.',
      time: '7 min read'
    },
    { 
      href: '/blog/posts/post7', 
      tag: 'Tips',
      title: 'Tips for Accurate Frequency Measurements', 
      description: 'Best practices for using the converter effectively, including handling large values and interpreting results.',
      time: '3 min read'
    }
  ];
</script>

<svelte:head>
  <title>Blog | AxelBase Insights</title>
  <meta name="description" content="In-depth articles on frequency conversion, precision, and practical use of the AxelBase converter." />
</svelte:head>

<div class="blog-container py-5">
  <div class="container">
    <header class="text-center mb-5" in:fly={{ y: -20, duration: 600 }}>
      <span class="badge rounded-pill bg-primary bg-opacity-10 text-primary px-3 py-2 mb-3">AXELBASE JOURNAL</span>
      <h1 class="display-4 fw-bold bubble-title">Converter Insights</h1>
      <p class="subtitle mx-auto">
        Practical guides, technical explanations, and tips on accurate frequency conversion between Hertz and Kilohertz.
      </p>
    </header>

    <div class="posts-grid">
      {#each posts as post, i}
        <div in:fly={{ y: 20, duration: 600, delay: i * 100 }}>
          <a href="{base}{post.href}" class="card post-card h-100 text-decoration-none">
            <div class="card-body d-flex flex-column p-4">
              <div class="d-flex justify-content-between align-items-center mb-3">
                <span class="post-tag">{post.tag}</span>
                <span class="read-time">{post.time}</span>
              </div>
              <h2 class="post-title">{post.title}</h2>
              <p class="post-description flex-grow-1">{post.description}</p>
              <div class="read-more-wrapper">
                <span class="read-more">Read Article</span>
                <span class="arrow">→</span>
              </div>
            </div>
          </a>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .blog-container {
    background: radial-gradient(circle at 10% 20%, rgba(99, 102, 241, 0.03) 0%, transparent 50%);
  }

  .bubble-title {
    background: linear-gradient(45deg, #1e293b, #6366f1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: clamp(2.5rem, 5vw, 3.5rem);
  }

  .subtitle {
    color: #64748b;
    max-width: 650px;
    font-size: 1.1rem;
    line-height: 1.6;
  }

  .posts-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 2rem;
  }

  .post-card {
    background: rgba(255, 255, 255, 0.7);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.5);
    border-radius: 24px;
    box-shadow: 0 10px 30px -5px rgba(0,0,0,0.04);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  }

  .post-card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 20px 40px -10px rgba(99, 102, 241, 0.15);
    background: #fff;
    border-color: rgba(99, 102, 241, 0.2);
  }

  .post-tag {
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    color: var(--brand-primary);
    background: rgba(99, 102, 241, 0.08);
    padding: 4px 12px;
    border-radius: 50px;
    letter-spacing: 0.5px;
  }

  .read-time {
    font-size: 0.8rem;
    color: #94a3b8;
    font-weight: 500;
  }

  .post-title {
    font-size: 1.4rem;
    font-weight: 700;
    line-height: 1.3;
    color: #1e293b;
    margin-bottom: 1rem;
    transition: color 0.3s ease;
  }

  .post-card:hover .post-title {
    color: var(--brand-primary);
  }

  .post-description {
    font-size: 0.95rem;
    color: #64748b;
    line-height: 1.6;
    margin-bottom: 1.5rem;
  }

  .read-more-wrapper {
    display: flex;
    align-items: center;
    gap: 8px;
    font-weight: 600;
    color: var(--brand-primary);
  }

  .arrow {
    transition: transform 0.3s ease;
  }

  .post-card:hover .arrow {
    transform: translateX(8px);
  }

  @media (max-width: 768px) {
    .posts-grid {
      grid-template-columns: 1fr;
    }
  }
</style>