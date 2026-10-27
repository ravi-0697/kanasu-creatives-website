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
const whatsappUrl = 'https://wa.me/917411544639?text=' + encodeURIComponent('Hello Kanasu Creatives! I would like to enquire about your photography packages.')
</script>

<template>
  <main>
    <section id="home" class="hero" :style="{ '--hero-image': 'url(https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&w=2000&q=90)' }">
      <header class="site-header wrap">
        <a class="brand" href="#home" aria-label="Kanasu Creatives home" @click="menuOpen = false">
          <span class="brand-mark">◎</span>
          <span class="brand-copy"><strong>KANASU</strong><small>CREATIVES</small><em>PHOTOGRAPHY & VIDEOGRAPHY</em></span>
        </a>
        <button class="menu-toggle" aria-label="Toggle navigation" :aria-expanded="menuOpen" @click="menuOpen = !menuOpen">☰</button>
        <nav :class="['nav-links', { 'nav-open': menuOpen }]">
          <a href="#home" @click="menuOpen = false">Home</a>
          <a href="#about" @click="menuOpen = false">About</a>
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
          <a class="contact-line" href="mailto:info@kanasucreatives.com"><span>✉</span> info@kanasucreatives.com</a>
          <a class="contact-line" :href="whatsappUrl" target="_blank" rel="noreferrer"><span>◉</span> WhatsApp our team</a>
          <div class="contact-divider"></div>
          <p class="contact-label">SERVING</p>
          <p class="contact-location">Bengaluru & across Karnataka</p>
          <a class="button button-gold contact-button" :href="whatsappUrl" target="_blank" rel="noreferrer">Enquire on WhatsApp <span>↗</span></a>
          <p class="small-note">Update the contact number and service area to match your business before launch.</p>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="wrap footer-inner">
        <a class="brand footer-brand" href="#home"><span class="brand-mark">◎</span><span class="brand-copy"><strong>KANASU</strong><small>CREATIVES</small><em>PHOTOGRAPHY & VIDEOGRAPHY</em></span></a>
        <p>Dream it. Capture it.</p>
        <span class="copyright">© {{ new Date().getFullYear() }} Kanasu Creatives</span>
      </div>
    </footer>
  </main>
</template>
