---
layout: home
description: "Hendricks County's community winter coat drive. Donate gently used coats through October 11, then pick one up free at the fairgrounds on Saturday, October 17."
---

{% assign event = site.data.event %}

<section class="hero">
  <div class="wrap hero__inner">
    <div class="hero__copy">
      <span class="pill">Hendricks County coat drive</span>
      <h1 class="hero__title">Every kid <em>warm</em> this winter.</h1>
      <p class="hero__lede">We're collecting gently used winter coats through <strong>{{ event.collection_deadline }}</strong>, then giving them away for free at the fairgrounds on <strong>{{ event.giveaway.day }}</strong>.</p>
      <div class="hero__actions">
        <a class="button button--primary" href="#sites">Donate a coat</a>
        <a class="button button--secondary" href="#giveaway">Need a coat? Come {{ event.giveaway.short_date | remove: "Sat, " }}</a>
      </div>
    </div>
    <div class="hero__art">
      <img src="{{ site.baseurl }}/images/beu.png" alt="Cartoon children bundled up in colorful winter coats, hats, and scarves" width="492" height="233">
    </div>
  </div>
</section>

<section class="facts" aria-label="Key dates">
  <div class="wrap facts__grid">
    <div class="fact">
      <div class="eyebrow">Collecting coats</div>
      <div class="fact__value">Until {{ event.collection_deadline }}</div>
      <p>Gently used coats, all sizes, at drop-off sites around the county.</p>
    </div>
    <div class="fact">
      <div class="eyebrow">Free coat giveaway</div>
      <div class="fact__value">{{ event.giveaway.short_date }}</div>
      <div class="fact__sub">{{ event.giveaway.time }}</div>
      <p>Come pick out a coat. No sign-up, no paperwork.</p>
    </div>
    <div class="fact">
      <div class="eyebrow">Where</div>
      <div class="fact__value">{{ event.giveaway.venue }}</div>
      <p>{{ event.giveaway.venue_detail }}, {{ event.giveaway.address }}</p>
    </div>
  </div>
</section>

<section id="giveaway" class="wrap">
  <div class="giveaway">
    <div class="giveaway__copy">
      <h2>Wear a costume. Trick-or-treat indoors.</h2>
      <p>Giveaway day is a party. Bring the kids in costume for indoor trick-or-treating and refreshments while you pick out coats.</p>
      <p class="giveaway__links">
        <a href="https://www.google.com/maps/search/?api=1&query={{ event.giveaway.maps_query | url_encode }}" target="_blank" rel="noopener">Directions to {{ event.giveaway.venue }}</a>
        <a href="{{ event.flyer | prepend: site.baseurl }}">Download the flyer (PDF)</a>
      </p>
    </div>
    <ul class="giveaway__extras">
      <li>
        <svg aria-hidden="true" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2 3 14h8l-1 8 10-12h-8z"></path></svg>
        <span><strong>Energy Assistance Program</strong> information will be available on site.</span>
      </li>
      <li>
        <svg aria-hidden="true" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.7l-1-1.1a5.5 5.5 0 0 0-7.8 7.8L12 21l8.8-8.6a5.5 5.5 0 0 0 0-7.8z"></path></svg>
        <span><strong>IU Health</strong> will provide free blood pressure screenings.</span>
      </li>
    </ul>
  </div>
</section>

<section id="help" class="wrap section">
  <h2 class="section__title">Three ways to help</h2>
  <div class="help-grid">
    <div class="help">
      <svg aria-hidden="true" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M7 4h10l3 5-3 1v10H7V10L4 9z"></path><path d="M12 4v16"></path></svg>
      <h3>Donate a coat</h3>
      <p>Clean, gently used winter coats in any size. Drop them at any site below by {{ event.collection_deadline }}.</p>
    </div>
    <div class="help">
      <svg aria-hidden="true" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 11v2a1 1 0 0 0 1 1h2l5 4V6L6 10H4a1 1 0 0 0-1 1z"></path><path d="M15 9a4 4 0 0 1 0 6"></path><path d="M18 6a8 8 0 0 1 0 12"></path></svg>
      <h3>Spread the word</h3>
      <p>Share this page with your school, church, team, or neighbors.</p>
    </div>
    <div class="help">
      <svg aria-hidden="true" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="8" r="4"></circle><path d="M4 21a8 8 0 0 1 16 0"></path></svg>
      <h3>Come if you need a coat</h3>
      <p>Everyone is welcome on {{ event.giveaway.day | split: ", " | last }}. Bring the whole family.</p>
    </div>
  </div>
</section>

<section id="sites" class="wrap section">
  <div class="section__head">
    <h2 class="section__title">Drop-off sites</h2>
    <p>Drop coats off during each location's regular hours, through {{ event.collection_deadline }}.</p>
  </div>
  <div class="sites">
    {% for town in site.data.locations %}
    <div class="town">
      <h3>{{ town.town }}</h3>
      <ul>
        {% for s in town.sites %}
        {% capture q %}{{ s.name }}, {{ s.address }}, {{ town.town }}, IN{% endcapture %}
        <li>
          <strong>{{ s.name }}</strong>
          <a href="https://www.google.com/maps/search/?api=1&query={{ q | url_encode }}" target="_blank" rel="noopener">{{ s.address }}</a>
        </li>
        {% endfor %}
      </ul>
    </div>
    {% endfor %}
  </div>
</section>
