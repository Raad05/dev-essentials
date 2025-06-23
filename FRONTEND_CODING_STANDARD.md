# 🧑‍💻 Frontend Coding Standard

---

## 🔐 1. Security & Environment Management

Never hardcode sensitive or environment-specific data. Use `.env` files for the following:

- API keys
- Secrets and Credentials

---

## 🔤 2. Naming Conventions

### Folders

- Use `kebab-case`  
  **Example:** `confirmation-modal`, `auth-hooks`

### Components

- Use `kebab-case` for filenames  
  **Example:** `confirmation-modal.tsx`, `login-button.tsx`

### Hooks

- Use `camelCase` prefixed with `use`  
  **Example:** `useAuth()`, `usePaginate()`
- Use `kebab-case` for hook filenames  
  **Example:** `use-paginate.tsx`, `use-auth.tsx`

### Utils

- Use `camelCase` for function names  
  **Example:** `parseUnit()`, `formatString()`
- Use `kebab-case` for file names  
  **Example:** `parse-unit.ts`, `format-string.ts`

### Types & Interfaces

- Use `PascalCase`  
  **Example:** `User`, `ApprovalStatus`

### Constants

- Use `UPPER_SNAKE_CASE`  
  **Example:** `MAX_AMOUNT`, `MIN_AMOUNT`

---

## 🧩 3. Input Validation

Use [Zod](https://zod.dev/) for validating:

- Form inputs
- Data blob

---

## 🔄 6. Data Fetching Standard

Use **React Query** for all async operations:

- `useQuery` → read
- `useMutation` → write (pair with modal feedback)

Configure:

- `refetchInterval`
- `retry`
- `cacheTime`
- `staleTime`

---

## 🔠 7. Types and Interfaces

Use strict types/interfaces for:

- Props, component state
- API responses

Use Zod inference to sync with TypeScript:

```ts
type MyType = z.infer<typeof mySchema>;
```

---

## 🧱 8. Modular Architecture

This architecture uses a **modular, scalable structure** inspired by feature-driven development. It separates global and feature-specific concerns, enhancing maintainability, reusability, and collaboration—ideal for Web3 or modern frontend applications.

```yaml
src/
│
├── app/                  # Application entry (providers, layout)
├── assets/               # Static files (images, fonts)
├── components/           # Shared components (buttons, modals)
├── hooks/                # Shared custom hooks
├── config/               # configurations, env
├── lib/                  # Reusable libraries
├── features/             # Feature-based modules
│   ├── api/              # Feature-specific API
│   ├── assets/           # Feature-specific images/icons
│   ├── components/       # Feature-specific components
│   ├── hooks/            # Feature-specific hooks
│   ├── stores/           # Feature-specific state
│   ├── types/            # Feature-specific types
│   └── utils/            # Feature-specific utilities
├── utils/                # Shared utilities (unit conversions, parsers, etc.)
├── layout/               # Page layouts
├── stores/               # Global state (Zustand)
├── types/                # Shared types/interfaces
├── testing/              # Test utilities and mocks
└── themes/               # Shadcn UI themes
```

## 🧠 9. UX Components

## Custom Button Component

A reusable custom button component should support the following props:

- Add `isLoading`, `isDisabled`, and `variant` props
- Prevent double-click with disabled state while loading

---

## 🗂 10. State Management

Use [Zustand](https://zustand-demo.pmnd.rs/) for global state management.

### Recommended Store Slices

- **UI Preferences**:

  - `darkMode`, `language`, etc.

- **Global States (Cached)**:
  - Useful if not using `react-query`

---

## Maintainers

- **[Yamin Raad](https://github.com/Raad05)**
