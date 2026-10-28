<script setup>
import { computed, ref } from 'vue'

const menuOpen = ref(false)
const activeFilter = ref('All')
const filters = ['All', 'Weddings', 'Pre-Wedding', 'Events', 'Portraits']
const services = [
  { icon: '♡', title: 'Weddings', text: 'Honest moments, beautiful details and cinematic wedding stories.' },
  { icon: '∞', title: 'Pre-Wedding', text: 'Creative couple sessions in places that mean something to you.' },
  { icon: '✦', title: 'Events', text: 'Engagements, birthdays, celebrations and corporate events.' },
  { icon: '◎', title: 'Portraits', text: 'Personal, family, maternity and little-one portraits.' },
]
const portfolio = [
  { title: 'The Wedding Story', category: 'Weddings', image: 'https://images.unsplash.com/photo-1583939003579-730e3918a45a?auto=format&fit=crop&w=900&q=85', shape: 'portrait' },
  { title: 'Golden Hour', category: 'Pre-Wedding', image: 'https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=900&q=85', shape: 'wide' },
  { title: 'A Night to Remember', category: 'Events', image: 'https://images.unsplash.com/photo-1511795409834-ef04bbd61622?auto=format&fit=crop&w=900&q=85', shape: 'wide' },
  { title: 'Little Moments', category: 'Portraits', image: 'https://images.unsplash.com/photo-1511895426328-dc8714191300?auto=format&fit=crop&w=900&q=85', shape: 'portrait' },
  { title: 'Forever Begins', category: 'Weddings', image: 'https://images.unsplash.com/photo-1537633552985-df8429e8048b?auto=format&fit=crop&w=900&q=85', shape: 'wide' },
  { title: 'Together, Always', category: 'Pre-Wedding', image: 'https://images.unsplash.com/photo-1529636798458-92182e662485?auto=format&fit=crop&w=900&q=85', shape: 'portrait' },
]
const visiblePortfolio = computed(() => activeFilter.value === 'All' ? portfolio : portfolio.filter(item => item.category === activeFilter.value))
const whatsappUrl = 'https://wa.me/918073301126?text=' + encodeURIComponent('Hello Kanasu Creatives! I would like to enquire about your photography packages.')
const instagramUrl = 'https://www.instagram.com/kanasu_creatives_2026/'
</script>

<template>
  <main>
    <section id="home" class="hero" :style="{ '--hero-image': 'url(https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=2000&q=90)' }">
      <header class="site-header wrap">
        <a class="brand" href="#home" aria-label="Kanasu Creatives home" @click="menuOpen = false">
          <span class="brand-mark">◎</span>
          <span class="brand-copy"><strong>KANASU</strong><small>CREATIVES</small><em>PHOTOGRAPHY & VIDEOGRAPHY</em><span class="brand-founders">
          By Avinash · Pavan Kumar L · Ravi G
        </span></span>
        </a>
        <button class="menu-toggle" aria-label="Toggle navigation" :aria-expanded="menuOpen" @click="menuOpen = !menuOpen">☰</button>
        <nav :class="['nav-links', { 'nav-open': menuOpen }]">
          <a href="#home" @click="menuOpen = false">Home</a>
          <a href="#about" @click="menuOpen = false">About</a>
          <!-- <a href="#team" @click="menuOpen = false">Our Team</a> -->
          <a href="#services" @click="menuOpen = false">Services</a>
          <a href="#portfolio" @click="menuOpen = false">Portfolio</a>
          <a href="#contact" @click="menuOpen = false">Contact</a>
          <a class="nav-cta" href="#contact" @click="menuOpen = false">Get a Quote <span>↗</span></a>
        </nav>
      </header>

      <div class="hero-content wrap">
        <p class="eyebrow">FRAMES THAT FEEL LIKE YOU</p>
        <h1>Kanasu Creatives</h1>
        <h2>Photography <span>&</span> Videography</h2>
        <p class="hero-description">We capture real moments, beautiful stories and timeless memories for your most special occasions.</p>
        <div class="hero-actions">
          <a class="button button-gold" href="#portfolio">View Our Work <span>→</span></a>
          <a class="button button-outline" href="#contact">Get a Quote</a>
        </div>
        <p class="hero-note">YOUR MOMENTS. OUR FRAME. MEMORIES FOREVER.</p>
      </div>
      <a class="scroll-cue" href="#services"><span></span> SCROLL TO EXPLORE</a>
    </section>

    <section id="about" class="intro section-light">
      <div class="wrap intro-grid">
        <div class="section-heading">
          <p class="eyebrow eyebrow-muted">A LITTLE ABOUT US</p>
          <h2>Every picture<br />has a <i>feeling.</i></h2>
          <span class="gold-rule"></span>
        </div>
        <div class="intro-copy">
          <p>At Kanasu Creatives, we believe the best photographs do more than show how a day looked — they bring back how it felt.</p>
          <p>From the quiet moments before “I do” to the joyful chaos of a family celebration, our three-member team captures your story with care, creativity and a cinematic eye.</p>
          <a class="text-link" href="#contact">LET'S CREATE SOMETHING MEANINGFUL <span>↗</span></a>
        </div>
      </div>
    </section>

    
<!-- <section id="team" class="team-section section-light">
  <div class="wrap">
    <div class="center-heading">
      <p class="eyebrow eyebrow-muted">THE PEOPLE BEHIND THE LENS</p>
      <h2>Meet our <i>team</i></h2>
      <p class="team-intro">
        Three creative minds, one shared passion —
        capturing your moments beautifully.
      </p>
    </div>

    <div class="team-grid">
      <article class="team-card">
        <div class="team-avatar">R</div>
        <h3>Ravi G</h3>
        <p>Photography & Creative Direction</p>
      </article>

      <article class="team-card">
        <div class="team-avatar">A</div>
        <h3>Avinash</h3>
        <p>Photography & Videography</p>
      </article>

      <article class="team-card">
        <div class="team-avatar">P</div>
        <h3>Pavan Kumar</h3>
        <p>Cinematic Films & Visual Stories</p>
      </article>
    </div>
  </div>
</section> -->


    <section id="services" class="services section-light">
      <div class="wrap">
        <div class="center-heading">
          <p class="eyebrow eyebrow-muted">WHAT WE DO</p>
          <h2>Made for your <i>moments</i></h2>
        </div>
        <div class="service-grid">
          <article v-for="service in services" :key="service.title" class="service-card">
            <div class="service-icon">{{ service.icon }}</div>
            <h3>{{ service.title }}</h3>
            <p>{{ service.text }}</p>
          </article>
        </div>
      </div>
    </section>

    <section id="portfolio" class="portfolio section-dark">
      <div class="wrap">
        <div class="portfolio-top">
          <div class="section-heading">
            <p class="eyebrow">SELECTED STORIES</p>
            <h2>Our <i>work</i></h2>
            <span class="gold-rule"></span>
          </div>
          <div class="filters" aria-label="Filter portfolio">
            <button v-for="filter in filters" :key="filter" :class="['filter-button', { active: activeFilter === filter }]" @click="activeFilter = filter">{{ filter }}</button>
          </div>
        </div>
        <div class="gallery-grid">
          <article v-for="item in visiblePortfolio" :key="item.title" class="gallery-item">
            <img :src="item.image" :alt="item.title" loading="lazy" />
            <div class="gallery-overlay"><span>{{ item.category }}</span><h3>{{ item.title }}</h3></div>
          </article>
        </div>
        <p class="gallery-note">Portfolio images are sample placeholders. Replace them with your own client work before publishing.</p>
      </div>
    </section>

    <section class="quote-band">
      <div class="wrap quote-inner">
        <p class="eyebrow">THE BEST STORIES ARE SHARED</p>
        <h2>Your day. Your people.<br /><i>Your story, beautifully told.</i></h2>
        <a class="button button-dark" href="#contact">Plan Your Shoot <span>→</span></a>
      </div>
    </section>

    <section id="contact" class="contact section-light">
      <div class="wrap contact-grid">
        <div class="section-heading">
          <p class="eyebrow eyebrow-muted">LET'S TALK</p>
          <h2>Let's make<br /><i>memories.</i></h2>
          <span class="gold-rule"></span>
          <p class="contact-copy">Tell us what you're celebrating. We'll help you find the right package for your day.</p>
        </div>
        <div class="contact-card">
          <p class="contact-label">START A CONVERSATION</p>
        
        
<a
  class="contact-line social-contact email-contact"
  href="mailto:info@kanasucreatives.com"
>
  <svg viewBox="0 0 24 24" aria-hidden="true">
    <rect
      x="3" y="5" width="18" height="14" rx="2"
      fill="none"
      stroke="currentColor"
      stroke-width="1.7"
    />
    <path
      d="m4 7 8 6 8-6"
      fill="none"
      stroke="currentColor"
      stroke-width="1.7"
      stroke-linecap="round"
      stroke-linejoin="round"
    />
  </svg>
  <span>info@kanasucreatives.com</span>
  <span class="social-arrow">↗</span>
</a>

          
          
<a
  class="contact-line social-contact whatsapp-contact"
  :href="whatsappUrl"
  target="_blank"
  rel="noopener noreferrer"
>
  <svg viewBox="0 0 24 24" aria-hidden="true">
    <path
      d="M20.5 11.8a8.4 8.4 0 0 1-12.4 7.4L3 20.5l1.4-5a8.4 8.4 0 1 1 16.1-3.7Z"
      fill="none"
      stroke="currentColor"
      stroke-width="1.7"
      stroke-linejoin="round"
    />
    <path
      d="M8.5 7.8c.3-.4.6-.4.9-.1l1.1 1.6c.2.3.1.5-.2.8l-.6.6c.5 1.1 1.4 2 2.6 2.6l.6-.7c.2-.3.5-.3.8-.1l1.6 1.1c.3.2.3.6.1.9-.4.7-1.1 1-1.8.9-2.8-.5-5.5-3.2-6-6-.1-.6.2-1.2.9-1.6Z"
      fill="currentColor"
    />
  </svg>
  <span>WhatsApp our team</span>
  <span class="social-arrow">↗</span>
</a>

<a
  class="contact-line social-contact instagram-contact"
  :href="instagramUrl"
  target="_blank"
  rel="noopener noreferrer"
>
  <svg viewBox="0 0 24 24" aria-hidden="true">
    <rect
      x="3.2" y="3.2" width="17.6" height="17.6" rx="5"
      fill="none" stroke="currentColor" stroke-width="1.8"
    />
    <circle
      cx="12" cy="12" r="4"
      fill="none" stroke="currentColor" stroke-width="1.8"
    />
    <circle cx="17.6" cy="6.7" r="1.1" fill="currentColor" />
  </svg>
  <span>Follow us on Instagram</span>
  <span class="social-arrow">↗</span>
</a>


          <div class="contact-divider"></div>
          <p class="contact-label">SERVING</p>
          <p class="contact-location">Bengaluru & across Karnataka</p>
          <a class="button button-gold contact-button" :href="whatsappUrl" target="_blank" rel="noreferrer">Enquire on WhatsApp <span>↗</span></a>
          <p class="small-note">Update the contact number and service area to match your business before launch.</p>
        </div>
      </div>
    </section>

    <!-- <footer class="footer">
      <div class="wrap footer-inner">
        <a class="brand footer-brand" href="#home"><span class="brand-mark">◎</span><span class="brand-copy"><strong>KANASU</strong><small>CREATIVES</small><em>PHOTOGRAPHY & VIDEOGRAPHY</em><span class="brand-founders">By Avinash. · Pavan Kumar · Ravi G</span></span></a>
        <p>Dream it. Capture it.</p>
        <span class="copyright">© {{ new Date().getFullYear() }} Kanasu Creatives</span>
      </div>
    </footer> -->
    
<footer class="footer">
  <div class="wrap footer-inner">
    <a class="brand footer-brand" href="#home">
      <span class="brand-mark">◎</span>
      <span class="brand-copy">
        <strong>KANASU</strong>
        <small>CREATIVES</small>
        <em>PHOTOGRAPHY & VIDEOGRAPHY</em>
        <span class="brand-founders">
          By Avinash · Pavan Kumar L · Ravi G
        </span>
      </span>
    </a>

    <div class="footer-middle">
      <p> Dream it. Capture it.</p>
      <p class="website-credit">
        Website designed &amp; developed by
        <strong>RAVI G</strong>
        <span>9620607130</span>
      </p>
    </div>

    <span class="copyright">
      © {{ new Date().getFullYear() }} Kanasu Creatives
    </span>
  </div>
</footer>

  </main>
</template>
