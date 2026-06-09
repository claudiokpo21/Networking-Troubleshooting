# Networking Troubleshooting

Guía interactiva de troubleshooting de redes — OSI, TCP/IP, VLAN, switching, routing, telecom (radioenlaces, VHF/UHF, satélite) y un wizard paso a paso. 100% client-side, sin backend, un solo deploy estático.

## Contenido

| Sección | Qué hay |
|---|---|
| **Home** | Hero + stats (10 secciones, 23 casos, 50 preguntas, 200+ comandos) |
| **Modelo OSI** | Las 7 capas con detalle expandible, animación de paquete |
| **TCP / IP** | Suite, puertos, three-way handshake, flags |
| **VLAN & Segmentación** | Switching, trunks, STP, inter-VLAN routing |
| **Calculadora Subredes** | IPv4 (CIDR/classful) + VLSM + IPv6 + wildcard |
| **Troubleshooting Wizard** | Asistente interactivo bottom-up con 7 rutas de diagnóstico |
| **Casos Reales (23)** | Escenarios de producción con topología, síntomas, diagnóstico paso a paso, comandos Cisco, prevención |
| **Quiz / Examen** | 50 preguntas CCNA + CCNP, con explicación, score, racha, persistencia |
| **Cheatsheet** | Comandos Cisco/Linux/Windows de referencia rápida |
| **Telecom** | Radio PTP, PMP, VHF/UHF, satelital (VSAT, LEO, GEO, MEO) |

## Stack

- HTML + CSS + JS vanilla, sin frameworks
- Sin backend, sin build step
- Datos en JSON (`quiz-data.json`, `casos-data.json`) cargados via `fetch()`
- Progreso del quiz persistido en `localStorage`

## Estructura

```
Networking-Troubleshooting/
├── troublesheet.html    # UI completa, 1500+ líneas
├── quiz-data.json       # 50 preguntas CCNA+CCNP
├── casos-data.json      # 23 escenarios reales
├── README.md
└── vercel.json          # (opcional) cache config
```

## Cómo usar

### Local

```powershell
python -m http.server 8000
```

Después abrí `http://localhost:8000/troublesheet.html` en el navegador.

> ⚠️ **No abrir con doble click** (`file://`) — los `fetch()` a los JSON no andan. Necesita un server local.

### Deploy en Vercel

Opción 1 — desde GitHub (recomendada):
1. Subí el repo a GitHub
2. Andá a [vercel.com/new](https://vercel.com/new) → "Import Project" → elegí el repo
3. Vercel detecta automáticamente que es estático, no hace falta config
4. Deploy. Te da una URL del estilo `https://networking-troubleshooting.vercel.app`

Opción 2 — CLI de Vercel (deploy directo sin Git):
```powershell
npm i -g vercel
cd Networking-Troubleshooting
vercel
```
Sigue los pasos, te logueás y en 30 segundos tenés la URL.

### Deploy en cualquier static host

Funciona en cualquier lado: GitHub Pages, Netlify, Cloudflare Pages, S3, etc. Solo serví los 3 archivos como estáticos.

## Créditos

Creado por **Hernandez Claudio** · 2026
OSI/TCP-IP/VLAN: CCNA/CCNP curriculum + experiencia de campo NOC.
Casos: troubleshooting real de producción, varios a las 3AM 😅.
