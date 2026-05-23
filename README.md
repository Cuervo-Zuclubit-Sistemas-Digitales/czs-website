# czs-website

Sitio web oficial de **Cuervo Zuclubit Sistemas Digitales, S.A.S.**

🌐 **Producción:** https://cuervo-zuclubit.com (pendiente de configurar)
📦 **Stack:** [Astro](https://astro.build/) + [Cloudflare Pages](https://pages.cloudflare.com/)
🔐 **Branch protection:** `main` requiere PR aprobado para merge

---

## Estado del proyecto

🚧 **En setup inicial.** Aún no hay sitio publicado. Ver milestones e issues abiertas.

## Cómo empezar (para Juan o cualquier dev nuevo)

### Prerrequisitos

- Node.js 20 o superior ([nvm](https://github.com/nvm-sh/nvm) recomendado)
- Git
- Cuenta en GitHub con acceso a este repo (pedir a Cuervo-Zuclubit)
- Editor de tu preferencia (VS Code, Cursor, etc.)

### Clonar y arrancar

```bash
git clone https://github.com/Cuervo-Zuclubit-Sistemas-Digitales/czs-website.git
cd czs-website
npm install
npm run dev
```

El sitio quedará en `http://localhost:4321`.

### Estructura esperada (una vez inicializado Astro)

```
czs-website/
├── src/
│   ├── pages/
│   │   ├── index.astro              # Home
│   │   ├── aviso-de-privacidad.astro
│   │   └── ...
│   ├── components/
│   ├── layouts/
│   └── styles/
├── public/
│   ├── brand/                       # Logo (clonado de czs-compliance)
│   └── favicon.svg
├── astro.config.mjs
├── package.json
└── README.md
```

## Flujo de trabajo

### Convención de ramas

- `feat/<descripcion>` — nuevas features
- `fix/<descripcion>` — bug fixes
- `chore/<descripcion>` — config, docs, refactor

### Convención de commits ([Conventional Commits](https://www.conventionalcommits.org/))

```
feat: agregar página /aviso-de-privacidad
fix: corregir link roto en footer
docs: actualizar README con instrucciones de deploy
chore: bumpear dependencias menores
```

### Ciclo de cambios

1. Crear rama desde `main`: `git checkout -b feat/algo`
2. Hacer commits siguiendo Conventional Commits
3. Push: `git push -u origin feat/algo`
4. Abrir Pull Request hacia `main`
5. Pedir review (asignar a Cuervo-Zuclubit)
6. Una vez aprobado, mergear via GitHub (squash merge preferido)
7. Borrar la rama local: `git branch -d feat/algo`

⚠️ **No se permite push directo a `main`.** Branch protection está activa.

## Deploy

### Cloudflare Pages

Pendiente de configurar. Cuando se conecte:

1. Cloudflare Pages detecta cada push a `main` y lanza un build automático.
2. PRs generan deployments preview accesibles en `<branch>.czs-website.pages.dev`.
3. Producción se sirve desde `cuervo-zuclubit.com` (requiere apuntar DNS).

### Pasos para conectar Cloudflare Pages (pendiente)

1. Cuervo-Zuclubit entra a https://dash.cloudflare.com/?to=/:account/pages
2. **Create a project** → **Connect to Git** → seleccionar `Cuervo-Zuclubit-Sistemas-Digitales/czs-website`
3. **Build settings:**
   - Framework preset: **Astro**
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Root directory: (vacío)
   - Node version: 20
4. **Save and Deploy**
5. Después, en **Custom domains** → agregar `cuervo-zuclubit.com` y `www.cuervo-zuclubit.com`
6. Cloudflare te dará registros DNS para apuntar en el registrar del dominio.

## Documentos legales fuente

El contenido del Aviso de Privacidad **NO** se escribe directo en este repo. La fuente única de verdad vive en `czs-compliance/docs/legal/aviso_privacidad_czs.md`.

Para publicar:
1. Pull request abre issue en este repo solicitando actualización.
2. Dev importa o copia el `.md` y lo renderiza en `/aviso-de-privacidad`.
3. La página debe coincidir **palabra por palabra** con el `.md` de `czs-compliance`.

## Soporte

- **Issues técnicas:** abrir issue en este repo
- **Cambios al contenido legal:** referir a `czs-compliance`
- **Brand y diseño:** ver `czs-compliance/brand/`
- **Contacto:** equipos@cuervo-zuclubit.com
