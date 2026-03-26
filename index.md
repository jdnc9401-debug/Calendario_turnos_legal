---
layout: home
title: "Calendario_turnos_legal"

---
<style>
  h1 {
    font-size: 2.4rem;
    font-weight: 700;
    margin-bottom: 1rem;
  }
  h2 {
    margin-top: 2rem;
    font-size: 1.6rem;
    font-weight: 600;
  }
  body, p, li {
    font-size: 1.05rem;
    line-height: 1.6;
  }
  ul {
    margin-top: 1rem;
  }
</style>

<script>
  const params = new URLSearchParams(window.location.search);
  const base = "/Calendario_turnos_legal";

  // Si la app o un enlace envía ?lang=xx&doc=yy → redirigir al documento correcto
  if (params.has("lang") && params.has("doc")) {
    const lang = params.get("lang").toLowerCase();
    const doc = params.get("doc").toLowerCase(); // "privacy" o "terms"
    window.location.href = `${base}/${lang}/${doc}.html`;
  }

  // Si vienes desde "Volver al inicio" → NO redirigir automáticamente
  else if (params.has("from")) {
    console.log("Mostrando index sin redirección automática");
  }

  // Si viene solo ?doc=privacy o ?doc=terms → autodetectar idioma y redirigir
  else if (params.has("doc")) {
    const doc = params.get("doc").toLowerCase();
    const lang = navigator.language.substring(0, 2).toLowerCase();
    const supported = ["es", "en", "fr", "de", "pt", "it"];
    const finalLang = supported.includes(lang) ? lang : "en";

    window.location.href = `${base}/${finalLang}/${doc}.html`;
  }

  // Si no hay parámetros → autodetección normal (privacy por defecto)
  else {
    const lang = navigator.language.substring(0, 2).toLowerCase();
    const supported = ["es", "en", "fr", "de", "pt", "it"];
    const finalLang = supported.includes(lang) ? lang : "en";

    window.location.href = `${base}/${finalLang}/privacy.html`;
  }
</script>



# Calendario – Documentación Legal

Bienvenido a la sección legal de Calendario de turnos. Si no eres redirigido automáticamente, selecciona tu idioma:

### 🌐 Selecciona tu idioma:
