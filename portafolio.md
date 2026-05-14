---
title: Portafolio
permalink: /portafolio/
kicker: Casos
subtitle: Selección de proyectos en los que trabajo o trabajé. Más casos próximamente.
---

{% if site.proyectos.size > 0 %}
<div class="grid grid--2">
  {%- for p in site.proyectos -%}
    <a href="{{ p.url }}" class="card" style="text-decoration: none; color: inherit;">
      <h3 class="card__title">{{ p.title }}</h3>
      {%- if p.cliente -%}<p class="text-sm" style="margin-bottom: 0.5rem;">{{ p.cliente }} · {{ p.industria }}</p>{%- endif -%}
      <p class="card__body">{{ p.resumen }}</p>
      <p style="margin-top: 1rem; color: var(--brand-primary, #2b0548); font-size: 0.9rem;">Ver caso →</p>
    </a>
  {%- endfor -%}
</div>
{% else %}
<p class="text-muted">Próximamente. Estoy preparando los primeros casos para mostrar.</p>
{% endif %}

---

¿Necesitas referencias específicas de tu industria? <a href="/contacto/">Cuéntame qué buscas</a> y te paso los casos más cercanos a lo que necesitas.
