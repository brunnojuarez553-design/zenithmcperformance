# Zenith Performance & Repair — Web

## Estructura del proyecto

```
zenith-project/
├── api/
│   └── chat.js          ← Proxy seguro para Groq (la API key nunca llega al frontend)
├── public/
│   └── index.html       ← El sitio web completo
├── vercel.json          ← Configuración de Vercel
└── .gitignore
```

## Deploy en Vercel

1. Subir este repositorio a GitHub
2. Importar en [vercel.com](https://vercel.com) → "Add New Project"
3. En **Environment Variables** agregar:
   - `GROQ_API_KEY` = tu API key de Groq (conseguila en [console.groq.com](https://console.groq.com))
4. Click en **Deploy**

## Variable de entorno requerida

| Variable | Descripción |
|----------|-------------|
| `GROQ_API_KEY` | API Key de Groq Cloud |

La key **nunca** queda expuesta en el frontend. El HTML llama a `/api/chat`, que es una Serverless Function privada en Vercel que tiene acceso a la variable de entorno.

## Modelo usado

`llama-3.3-70b-versatile` vía Groq Cloud — rápido, preciso y gratuito en el tier básico.
