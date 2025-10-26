---
# Leave the homepage title empty to use the site title
title: '홈'
date: 2025-10-13
type: Portfolio
image:
  filename: "media/favicon.png"
  focal_point: "center"
  preview_only: false

design:
  # Default section spacing
  spacing: '6rem'

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: '전북대학교 컴퓨터공학부 21학번'
      # Show a call-to-action button under your biography? (optional)
      button:
        text: 자기소개
        url: /uploads/resume.pdf
        style: outline
      headings:
        about: '강석민'
        education: '전북대학교'
        interests: '컴퓨터공학'
    design:
      # Apply a gradient background
      css_class: hbx-bg-gradient
      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  
  - block: markdown
    content:
      title: '홈페이지 소개'
      subtitle: 'PB1'
      text: |-
        <div class="slider slider-full" id="home-slider">
          <div class="slides autoplay">
            <div class="slide">
              <img src="/media/slide1.jpg" alt="Slide 1">
              <div class="caption">
                <div class="caption-title">자기 소개</div>
                <div class="caption-subtitle">관심사/진로/목표</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide2.jpg" alt="Slide 2">
              <div class="caption">
                <div class="caption-title">소속</div>
                <div class="caption-subtitle">전북대학교/WHO/견우직녀</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide3.jpg" alt="Slide 3">
              <div class="caption">
                <div class="caption-title">전공</div>
                <div class="caption-subtitle">컴퓨터공학</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide4.jpg" alt="Slide 4">
              <div class="caption">
                <div class="caption-title">경력</div>
                <div class="caption-subtitle">영재학급/ESD금천창의인재학교/에너지수호천사단/수효사효림원</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide5.jpg" alt="Slide 5">
              <div class="caption">
                <div class="caption-title">프로젝트</div>
                <div class="caption-subtitle">QatarDraw/Galendar/MyBucket</div>
              </div>
            </div>
          </div>
          <button class="nav prev" aria-label="Previous slide">‹</button>
          <button class="nav next" aria-label="Next slide">›</button>
        </div>

        <style>
          .slider {
            overflow: hidden;
            width: 100%;
            height: 600px;
            margin: 0 auto;
            position: relative;
          }
          .slider-full {
            width: 80%;
            max-width: 1200px;
            margin: 0 auto;
          }
          .slides {
            display: flex;
            height: 100%;
            transition: transform 0.6s ease;
          }
          .slides { z-index: 1; }
          .slide {
            flex: 0 0 100%;
            height: 100%;
            position: relative;
          }
          .slider img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
          }
          .caption {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: white;
          }
          .caption-title {
            font-size: 2.5rem;
            font-weight: bold;
            text-shadow: 0 2px 8px rgba(0,0,0,0.7);
            margin-bottom: 0.5rem;
          }
          .caption-subtitle {
            font-size: 1.5rem;
            font-weight: 400;
            text-shadow: 0 1px 5px rgba(0,0,0,0.6);
          }
          .nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 48px;
            height: 48px;
            border: none;
            border-radius: 9999px;
            background: rgba(0,0,0,0.4);
            color: #fff;
            font-size: 32px;
            line-height: 48px;
            text-align: center;
            cursor: pointer;
            transition: background 0.3s ease;
            z-index: 5;
          }
          .nav:hover { background: rgba(0,0,0,0.6); }
          .nav.prev { left: 15px; }
          .nav.next { right: 15px; }
        </style>
        <script>
        (function(){
          const root = document.querySelector('.slider');
          if (!root) return;
          const track = root.querySelector('.slides');
          const slides = Array.from(root.querySelectorAll('.slide'));
          const btnPrev = root.querySelector('.prev');
          const btnNext = root.querySelector('.next');
          let index = 0;
          const total = slides.length;
          const intervalMs = 4000;
          let timer = null;

          function update() {
            track.style.transform = 'translateX(-' + (index * 100) + '%)';
          }
          function next() {
            index = (index + 1) % total;
            update();
          }
          function prev() {
            index = (index - 1 + total) % total;
            update();
          }
          function start() {
            if (timer) clearInterval(timer);
            timer = setInterval(next, intervalMs);
          }
          function stop() {
            if (timer) clearInterval(timer);
            timer = null;
          }

          btnNext && btnNext.addEventListener('click', () => { stop(); next(); start(); });
          btnPrev && btnPrev.addEventListener('click', () => { stop(); prev(); start(); });

          // Pause autoplay on hover
          root.addEventListener('mouseenter', stop);
          root.addEventListener('mouseleave', start);

          // Initialize
          update();
          start();
        })();
        </script>
    design:
      columns: '1'
      
  - block: collection
    id: papers
    content:
      title: Featured Publications
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: article-grid
      columns: 2
      
  - block: collection
    content:
      title: Recent Publications
      text: ''
      filters:
        folders:
          - publications
        exclude_featured: false
    design:
      view: citation
  - block: collection
    id: talks
    content:
      title: Recent & Upcoming Talks
      filters:
        folders:
          - events
    design:
      view: card
  - block: collection
    id: news
    content:
      title: Recent News
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: blog
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ''
        category: ''
        tag: ''
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ''
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: card
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
  - block: cta-card
    demo: true # Only display this section in the Hugo Blox Builder demo site
    content:
      title: 👉 Build your own academic website like this
      text: |-
        This site is generated by Hugo Blox Builder - the FREE, Hugo-based open source website builder trusted by 250,000+ academics like you.

        <a class="github-button" href="https://github.com/HugoBlox/hugo-blox-builder" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star HugoBlox/hugo-blox-builder on GitHub">Star</a>

        Easily build anything with blocks - no-code required!

        From landing pages, second brains, and courses to academic resumés, conferences, and tech blogs.
      button:
        text: Get Started
        url: https://hugoblox.com/templates/
    design:
      card:
        # Card background color (CSS class)
        css_class: 'bg-primary-300'
        css_style: ''
---
