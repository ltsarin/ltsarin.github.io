---
layout: about
title: about
permalink: /
subtitle: <a href='https://www.unmc.edu/eppley/index.html'>University of Nebraska Medical Center.</a>
profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >

    <p>Omaha, NE, United States </p>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: false # `true` caps the box at 60vw, which on a phone clips items mid-sentence
  limit: 3 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<div class="hero-copy">
  <h1 class="hero-name">Lev Tsarin</h1>
  <p class="hero-tagline">Cancer genomics &amp; computational biology | Mutational signatures and ML for patient stratification</p>

  <p class="hero-lede">
    I'm an incoming PhD student and current research technologist in the <a href="#">Shcherbakova Lab</a> at the
    University of Nebraska Medical Center, working at the intersection of cancer genomics, genome instability,
    and computational biology.
  </p>

  <p class="hero-lede hero-lede-secondary">
    My research focuses on <em>POLE</em>/<em>POLD1</em> tumors and their distinctive mutational signatures. I build
    machine learning tools to characterize these signatures and to stratify cancer patients who might benefit from
    personalized treatment.
  </p>

  <div class="hero-cta">
    <a class="site-btn site-btn-primary" href="{{ '/projects/' | relative_url }}">View Projects</a>
    <a class="site-btn site-btn-outline" href="{{ '/cv/' | relative_url }}">View CV</a>
    <a class="site-btn site-btn-outline" href="mailto:{{ site.email }}">Get in Touch</a>
  </div>
</div>

<section class="site-section site-section-first">
  <h2 class="site-section-title">What I do</h2>
  <div class="interests-grid">
    <div class="interest-card">
      <h3>Cancer genomics</h3>
      <p>Somatic variant analysis in hypermutated and ultramutated tumors, with a focus on the proofreading-deficient <em>POLE</em>/<em>POLD1</em> polymerases.</p>
    </div>
    <div class="interest-card">
      <h3>Mutational signatures</h3>
      <p>Characterizing the signatures that separate genuine polymerase-driven ultramutation from the mutational background around it.</p>
    </div>
    <div class="interest-card">
      <h3>Machine learning</h3>
      <p>Classifiers that work on targeted panel data — the sequencing most patients actually get — not just on whole-exome and whole-genome cohorts.</p>
    </div>
    <div class="interest-card">
      <h3>Databases &amp; tooling</h3>
      <p>Curated resources and reproducible tooling for variant data, built so that someone else's analysis is less painful than mine was.</p>
    </div>
  </div>
</section>

<section class="site-section">
  <header class="site-section-header">
    <h2 class="site-section-title">Featured projects</h2>
    <p class="site-section-desc">Current research projects and ongoing work.</p>
  </header>

  <div class="project-cards">
    {% assign featured_projects = site.projects | sort: "importance" %}
    {% for project in featured_projects limit: 3 %}
      <a class="project-card-link" href="{{ project.url | relative_url }}">
        <article class="project-card">
          <h3 class="project-title">{{ project.title }}</h3>
          {% if project.category %}<p class="project-meta">{{ project.category }}</p>{% endif %}
          <p class="project-description">{{ project.description }}</p>
          <span class="read-more">Read more</span>
        </article>
      </a>
    {% endfor %}
  </div>

  <div class="site-cta">
    <a href="{{ '/projects/' | relative_url }}">View all projects &rarr;</a>
  </div>
</section>

<section class="site-section beyond-note">
  <h2 class="site-section-title">Beyond the dry lab</h2>
  <p>
    I commute year-round on an electric unicycle — one-legged, if the mood strikes. Being a tech &amp; science nerd,
    I have to stay adventurous: hiking, camping, and exploring new places whenever I can.
  </p>
  <p class="languages-note">
    <strong><em>I speak English, Ukrainian, and Russian.</em></strong> <strong>Come talk to me about anything!</strong>
  </p>
</section>

<style>
  /* ---------------------------------------------------------------------------
     Homepage styling. Deliberately kept inline rather than in assets/css/main.scss:
     PurgeCSS (see purgecss.config.js) only rewrites `_site/assets/css/*.css`, so
     inline page styles cannot be stripped by the deploy pipeline.

     The `about` layout is gem-owned and renders, in order:
       .post-header (h1 + subtitle) -> .profile (float) -> content -> news
       -> selected papers -> social
     We hide .post-header and rebuild the hero inside the content so the name sits
     beside the floated profile image, the way the reference layout does.
     --------------------------------------------------------------------------- */

  .post > .post-header {
    display: none;
  }

  /* --- Hero ---------------------------------------------------------------- */

  .hero-name {
    font-family: var(--site-font-brand);
    font-size: clamp(2.25rem, 5.5vw, 3.5rem);
    font-weight: 600;
    line-height: 1.05;
    margin: 0 0 0.5rem;
    letter-spacing: -0.02em;
  }

  .hero-tagline {
    font-family: var(--site-font-brand);
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--global-theme-color);
    margin: 0 0 1.5rem;
    line-height: 1.4;
  }

  .hero-lede {
    font-size: 1.05rem;
    line-height: 1.65;
    margin: 0 0 1rem;
  }

  .hero-lede-secondary {
    color: var(--global-text-color-light);
  }

  .hero-cta {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    margin: 1.75rem 0 0;
  }

  .site-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-height: 44px;
    padding: 0.55rem 1.15rem;
    border-radius: 0;
    border: 1px solid var(--global-theme-color);
    font-family: var(--site-font-brand);
    font-size: 0.875rem;
    font-weight: 500;
    text-decoration: none;
    transition:
      transform var(--site-sweep),
      background-color var(--site-sweep),
      color var(--site-sweep);
  }

  .site-btn:hover {
    transform: translateY(var(--site-lift));
    text-decoration: none;
  }

  .site-btn-primary {
    background-color: var(--global-theme-color);
    color: var(--global-hover-text-color);
  }

  .site-btn-primary:hover {
    background-color: var(--global-hover-color);
    border-color: var(--global-hover-color);
    color: var(--global-hover-text-color);
  }

  .site-btn-outline {
    background-color: transparent;
    color: var(--global-text-color);
  }

  .site-btn-outline:hover {
    background-color: var(--global-theme-color);
    color: var(--global-hover-text-color);
  }

  /* --- Sections ------------------------------------------------------------ */

  .site-section {
    clear: both; /* drop below the floated .profile image */
    margin: 4rem 0 0;
  }

  .site-section-first {
    padding-top: 3rem;
    border-top: 1px solid var(--global-divider-color);
  }

  .site-section-header {
    margin-bottom: 1.75rem;
  }

  .site-section-title {
    font-family: var(--site-font-brand);
    font-size: 1.5rem;
    font-weight: 600;
    margin: 0 0 0.35rem;
  }

  .site-section-desc {
    color: var(--global-text-color-light);
    margin: 0;
    font-size: 0.95rem;
  }

  .site-cta {
    margin-top: 1.5rem;
  }

  .site-cta a {
    font-family: var(--site-font-brand);
    font-size: 0.875rem;
    font-weight: 500;
  }

  /* --- "What I do" grid ---------------------------------------------------- */

  /* 2x2 rather than `auto-fit`: at the 930px content width auto-fit gives 3+1,
     which leaves a lone narrow card stranded on the second row. */
  .interests-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
    margin-top: 1.75rem;
  }

  @media (max-width: 575px) {
    .interests-grid {
      grid-template-columns: 1fr;
    }
  }

  .interest-card {
    padding: 1.25rem;
    border: 1px solid var(--site-border);
    border-radius: var(--site-radius);
    background-color: var(--site-surface);
  }

  .interest-card h3 {
    font-family: var(--site-font-brand);
    font-size: 1rem;
    font-weight: 600;
    margin: 0 0 0.5rem;
  }

  .interest-card p {
    margin: 0;
    font-size: 0.9rem;
    line-height: 1.55;
    color: var(--global-text-color-light);
  }

  /* --- Project cards ------------------------------------------------------- */

  .project-cards {
    display: grid;
    gap: 1rem;
  }

  .project-card-link,
  .project-card-link:hover {
    text-decoration: none;
    color: inherit;
  }

  .project-card {
    padding: 1.4rem;
    border: 1px solid var(--site-border);
    border-radius: var(--site-radius);
    background-color: var(--site-surface);
    box-shadow: var(--site-shadow);
    transition:
      transform var(--site-sweep),
      box-shadow var(--site-sweep),
      border-color var(--site-sweep);
  }

  .project-card-link:hover .project-card {
    transform: translateY(var(--site-lift));
    box-shadow: var(--site-shadow-hover);
    border-color: var(--global-theme-color);
  }

  .project-title {
    font-family: var(--site-font-brand);
    font-size: 1.1rem;
    font-weight: 600;
    margin: 0 0 0.3rem;
  }

  .project-meta {
    font-family: var(--site-font-brand);
    font-size: 0.8rem;
    font-weight: 600;
    color: var(--global-theme-color);
    margin: 0 0 0.6rem;
    text-transform: lowercase;
  }

  .project-description {
    margin: 0 0 0.8rem;
    font-size: 0.95rem;
    line-height: 1.6;
    color: var(--global-text-color-light);
  }

  .read-more {
    font-family: var(--site-font-brand);
    font-size: 0.825rem;
    font-weight: 500;
    color: var(--global-theme-color);
  }

  .read-more::after {
    content: " \2192";
  }

  .beyond-note {
    padding-top: 3rem;
    border-top: 1px solid var(--global-divider-color);
  }

  .beyond-note p {
    margin: 0 0 0.75rem;
    line-height: 1.65;
  }

  .languages-note {
    margin: 0;
  }

  /* --- Restyle the layout-injected news / publications headings ------------- */

  .post article > h2 {
    font-family: var(--site-font-brand);
    font-size: 1.5rem;
    font-weight: 600;
    margin: 4rem 0 1.75rem;
    text-transform: capitalize;
  }

  /* --- Phone trims ---------------------------------------------------------
     The theme sizes these for a wide column: `.social .contact-icons` is 4rem
     (icons wrap to two rows and eat vertical space), and `.preview` has no
     max-width, so the stacked bib column stretches it full-width. */

  @media (max-width: 575px) {
    .publications .bibliography img.preview {
      max-width: 120px;
      display: block;
      margin: 0 auto 0.5rem;
    }

    .publications .bibliography .col.col-sm-2.abbr {
      text-align: center;
    }

    .social .contact-icons {
      font-size: 2.4rem;
    }

    .social .contact-icons a img,
    .social .contact-icons a svg,
    .social .contact-icons a svg image {
      width: 2.1rem;
      height: 2.1rem;
      margin-bottom: 0.35rem;
    }

    .hero-cta .site-btn {
      flex: 1 1 100%;
    }
  }
</style>
