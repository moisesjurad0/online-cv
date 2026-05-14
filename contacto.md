---
title: Contacto
permalink: /contacto/
kicker: Conversemos
subtitle: La forma más rápida de empezar es escribirme. Te respondo en menos de 24 horas en días hábiles.
---

## Por dónde escribirme

<div class="grid grid--2" style="margin-bottom: 3rem;">
  <div class="card"
       data-wa-number="{{ site.contact.whatsapp }}"
       data-wa-base="{{ site.whatsapp_messages.contacto }}">
    <div class="card__icon" aria-hidden="true">💬</div>
    <h3 class="card__title">WhatsApp</h3>
    <p class="card__body">{{ site.contact.phone }}</p>
    <form class="wa-form" id="wa-contact-form" onsubmit="return false;">
      <div class="wa-form__field">
        <label for="wa-nombre">Tu nombre</label>
        <input id="wa-nombre" type="text" placeholder="Ej. María García" autocomplete="given-name" maxlength="80">
      </div>
      <div class="wa-form__field">
        <label for="wa-empresa">Empresa o emprendimiento <span style="font-weight:400;text-transform:none;letter-spacing:0">(opcional)</span></label>
        <input id="wa-empresa" type="text" placeholder="Ej. Estudio Nómada" autocomplete="organization" maxlength="80">
      </div>
      <div class="wa-form__submit">
        <button type="submit" class="btn btn--primary" id="wa-open-btn" style="width:100%">
          Abrir conversación →
        </button>
      </div>
    </form>
  </div>

  <a href="mailto:{{ site.contact.email }}" class="card" style="text-decoration: none; color: inherit;">
    <div class="card__icon" aria-hidden="true">✉️</div>
    <h3 class="card__title">Correo</h3>
    <p class="card__body">{{ site.contact.email }}</p>
    <p style="margin-top: 1rem; color: var(--brand-primary, #2b0548); font-size: 0.9rem;">Enviar correo →</p>
  </a>
</div>

## ¿Qué pasa después de escribirme?

1. **Respondo en menos de 24 horas hábiles** con preguntas concretas para entender qué necesitas.
2. **Coordinamos un llamado de 30 minutos** sin compromiso. Te pregunto, tú me preguntas. Si encajamos, seguimos.
3. **Te mando una propuesta por escrito** con alcance, hitos, tiempos y costo. Vigencia 15 días.
4. **Si firmas, arrancamos.** El primer hito se factura para asegurar el cronograma; el resto se libera contra entregas.

<!--
COMENTADO TEMPORALMENTE — re-activar después de completar formalización SUNAT (PNN + RER).
Cuando vuelvas a habilitar esta sección, actualiza el régimen tributario:
- Antes decía: Recibo por Honorarios Electrónico (RHE)
- Va a decir: Factura electrónica vía SEE-SOL bajo Régimen Especial de Renta (RER)

## Datos de facturación

- **Razón social:** Elías Luis Jurado Santos
- **RUC:** {{ site.contact.ruc }}
- **Comprobante:** Factura electrónica SUNAT (Régimen Especial de Renta)
- **Para clientes en el exterior:** exportación de servicios, inafecta de IGV bajo Apéndice V Ley IGV
-->

## Ubicación

{{ site.contact.city }}. Trabajo remoto con clientes de toda LATAM.

<script>
(function () {
  var form   = document.getElementById('wa-contact-form');
  var btn    = document.getElementById('wa-open-btn');
  var card   = form.closest('[data-wa-number]');
  var number = card.dataset.waNumber;
  var base   = card.dataset.waBase;

  btn.addEventListener('click', function () {
    var nombre  = document.getElementById('wa-nombre').value.trim();
    var empresa = document.getElementById('wa-empresa').value.trim();

    var intro = '';
    if (nombre && empresa) {
      intro = 'Hola Elías, soy ' + nombre + ' de ' + empresa + '. ';
    } else if (nombre) {
      intro = 'Hola Elías, soy ' + nombre + '. ';
    }

    var mensaje = intro + base.replace(/^Hola Elías[,.]?\s*/i, '');
    var url = 'https://wa.me/' + number + '?text=' + encodeURIComponent(mensaje);
    window.open(url, '_blank', 'noopener,noreferrer');
  });
})();
</script>
