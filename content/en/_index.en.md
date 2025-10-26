---
# Leave the homepage title empty to use the site title
title: 'Home'
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
      text: 'Class of 2021, Department of Computer Engineering, Jeonbuk National University'
      # Show a call-to-action button under your biography? (optional)
      button:
        text: About Me
        url: /uploads/resume.pdf
        style: outline
      headings:
        about: 'Kang Seok Min'
        education: 'Jeonbuk National University'
        interests: 'Computer Engineering'
    design:
      # Apply a gradient background
      css_class: hbx-bg-gradient
      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  
  - block: markdown
    content:
      title: 'Website Overview'
      subtitle: 'Portfolio Project 1'
      text: |-
        <div class="slider slider-full" id="home-slider">
          <div class="slides autoplay">
            <div class="slide">
              <img src="/media/slide1.jpg" alt="Slide 1">
              <div class="caption">
                <div class="caption-title">About Me</div>
                <div class="caption-subtitle">Interests / Career / Goals</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide2.jpg" alt="Slide 2">
              <div class="caption">
                <div class="caption-title">Affiliation</div>
                <div class="caption-subtitle">Jeonbuk National University / WHO / Gyeonwoo & Jiknyeo</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide3.jpg" alt="Slide 3">
              <div class="caption">
                <div class="caption-title">Major</div>
                <div class="caption-subtitle">Programming Languages / Web Development / Database / Systems & Cloud</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide4.jpg" alt="Slide 4">
              <div class="caption">
                <div class="caption-title">Experience</div>
                <div class="caption-subtitle">Gifted Class / ESD Creative Talent School / Energy Guardian Angels / Suhyo Sarye Institute</div>
              </div>
            </div>
            <div class="slide">
              <img src="/media/slide5.jpg" alt="Slide 5">
              <div class="caption">
                <div class="caption-title">Projects</div>
                <div class="caption-subtitle">QatarDraw / Galendar / MyBucket</div>
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
            width: 100%;
            max-width: 3000px;
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
        window.addEventListener('load', function() {
          const root = document.getElementById('home-slider');
          if (!root) return;
          const track = root.querySelector('.slides');
          const slides = Array.from(root.querySelectorAll('.slide'));
          const btnPrev = root.querySelector('.prev');
          const btnNext = root.querySelector('.next');
          let index = 0;
          const total = slides.length;
          const intervalMs = 3000;
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

          root.addEventListener('mouseenter', stop);
          root.addEventListener('mouseleave', start);

          update();
          start();
        });
        </script>
    design:
      columns: '1'
---
