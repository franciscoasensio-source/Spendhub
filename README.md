# SpendHub — Prototipo Humand

Prototipo interactivo del módulo de gestión de gastos de Humand. Incluye vista Admin y vista Colaborador, con el design system de Humand aplicado (colores, tipografía, espaciado).

## Vistas incluidas

| Ruta | Vista | Descripción |
|------|-------|-------------|
| `/` | Landing | Selector de rol (Admin / Colaborador) |
| `/admin/gastos` | Admin – Gestión de Gastos | Tabla de solicitudes con filtros, detalle y acciones (Aprobar / Rechazar / Pagar) |
| `/admin/config` | Admin – Configuración | Categorías con reglas de aprobación (WorkflowBuilder) + Políticas |
| `/colaborador/gastos` | Colaborador – Mis Gastos | Lista personal + flujo "Nueva solicitud" en 3 pasos |

---

## Cómo correr localmente

```bash
# 1. Instalar dependencias
npm install

# 2. Levantar servidor de desarrollo
npm run dev

# 3. Abrir en el browser
# → http://localhost:5173
```

## Cómo hacer build

```bash
npm run build
# El output queda en /dist
```

---

## Deploy en Vercel (1 clic)

### Opción A — Desde GitHub

1. Subí este proyecto a un repo de GitHub
2. Entrá a [vercel.com](https://vercel.com) → **Add New Project**
3. Importá el repo
4. Vercel detecta Vite automáticamente. Dejá los defaults:
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`
5. Click **Deploy** → listo 🚀

### Opción B — Vercel CLI

```bash
npm i -g vercel
vercel
# Seguí los pasos interactivos
```

---

## Stack

- **React 18** + **TypeScript**
- **Vite 5** (bundler)
- **React Router v6** (SPA routing)
- **Tailwind CSS 3** (con tokens del design system Humand)
- **lucide-react** (iconos)

## Design System

Los colores, tipografía y espaciado siguen exactamente las foundations de Humand:

- **Fuente:** Roboto 400 / 600
- **Color primario:** `#496be3` (Humand 500)
- **Fondo de página:** `#f5f6f8` (Neutral 50)
- **Texto principal:** `#303036` (Neutral 950)
- **Sombras:** 4dp y 8dp tokens

---

## Estructura del proyecto

```
src/
├── data/
│   ├── types.ts          # Todos los tipos TypeScript
│   └── mock.ts           # Datos de prueba
├── components/
│   ├── ui/
│   │   ├── Avatar.tsx    # Avatar + AvatarStack
│   │   └── Badge.tsx     # StatusBadge, CountBadge, CategoryChip
│   └── layout/
│       ├── Sidebar.tsx   # Navegación estilo Humand
│       └── AppLayout.tsx # Layout con sidebar + PageHeader
└── pages/
    ├── Landing.tsx
    ├── admin/
    │   ├── GestionGastos.tsx        # Tabla de solicitudes
    │   └── ConfiguracionSpendHub.tsx # Categorías + Políticas
    └── colaborador/
        └── MisGastos.tsx            # Vista personal + Nueva solicitud
```
