---
layout: page
title: Home
icon: fas fa-home
---

<style>
.portfolio-feature {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(260px, 42%);
  overflow: hidden;
  margin: 0 0 2rem;
  border: 1px solid rgba(127, 127, 127, 0.25);
  border-radius: 1rem;
  background: var(--card-bg, #1d1d1f);
  box-shadow: 0 0.5rem 1.5rem rgba(0, 0, 0, 0.12);
}

.portfolio-feature__content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 1.75rem 2rem;
}

.portfolio-feature__content h2 {
  margin: 0 0 0.65rem;
}

.portfolio-feature__content p {
  margin: 0;
  color: var(--text-muted-color, #8d8d92);
}

.portfolio-feature__meta {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem 1.5rem;
  margin-top: 1.4rem;
  color: var(--text-muted-color, #8d8d92);
  font-size: 0.9rem;
}

.portfolio-feature__image {
  min-height: 220px;
  background: #111;
}

.portfolio-feature__image img {
  display: block;
  width: 100%;
  height: 100%;
  min-height: 220px;
  object-fit: cover;
}

@media (max-width: 700px) {
  .portfolio-feature {
    grid-template-columns: 1fr;
  }

  .portfolio-feature__image {
    order: -1;
    min-height: 190px;
  }

  .portfolio-feature__image img {
    min-height: 190px;
    max-height: 260px;
  }

  .portfolio-feature__content {
    padding: 1.35rem;
  }
}
</style>

<article class="portfolio-feature">
  <div class="portfolio-feature__content">
    <h2>Staff des YTH Cyber Days</h2>
    <p>
      Membre du staff de Youth Technology House pour une activité dédiée à la
      communauté technologique et cybersécurité.
    </p>
    <div class="portfolio-feature__meta">
      <span>Engagement communautaire</span>
      <span>Youth Technology House</span>
    </div>
  </div>
  <div class="portfolio-feature__image">
    <img src="/assets/img/community/yth-cyber-days-staff.png" alt="Staff des YTH Cyber Days">
  </div>
</article>
