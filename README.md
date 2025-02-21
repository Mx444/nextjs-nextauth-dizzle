# Progetto di Autenticazione Next.js 🚀

Questo progetto è un'applicazione Next.js che implementa funzionalità di autenticazione, tra cui login, registrazione, reset della password e autenticazione a due fattori.

## Funzionalità ✨

- Registrazione utente 📝
- Login utente con email e password 🔐
- Reset della password via email 📧
- Funzionalità di cambio password 🔄
- Autenticazione a due fattori con Google Authenticator 🔑
- Rotte protette per utenti autenticati 🔒
- Notifiche toast per feedback agli utenti 📢

## Tecnologie Utilizzate 🛠️

- Next.js
- React
- TypeScript
- Tailwind CSS
- Drizzle ORM
- Neon Database
- bcryptjs per hashing delle password
- nodemailer per l'invio di email
- zod per la validazione degli schemi
- next-auth per l'autenticazione

## Struttura del Progetto 📂

```
/app
    ├── (logged-in)
    │   ├── change-password
    │   │   ├── change-password-form
    │   │   │   ├── actions.ts
    │   │   │   └── index.tsx
    │   │   └── page.tsx
    │   ├── layout.tsx
    │   ├── logout-button
    │   │   ├── actions.ts
    │   │   └── index.tsx
    │   ├── my-account
    │   │   ├── page.tsx
    │   │   └── two-factor-auth-form
    │   │       ├── actions.ts
    │   │       └── index.tsx
    ├── (logged-out)
    │   ├── layout.tsx
    │   ├── login
    │   │   ├── actions.ts
    │   │   └── page.tsx
    │   ├── password-reset
    │   │   ├── actions.ts
    │   │   └── page.tsx
    │   ├── register
    │   │   ├── actions.ts
    │   │   └── page.tsx
    │   ├── update-password
    │       ├── page.tsx
    │       └── update-password-form
    │           ├── actions.ts
    │           └── index.tsx
    ├── api
    │   └── auth
    │       └── [...nextauth]
    │           └── route.ts
    ├── globals.css
    ├── layout.tsx
    └── page.tsx
/components
    ├── ui
    │   ├── button.tsx
    │   ├── card.tsx
    │   ├── form.tsx
    │   ├── input-otp.tsx
    │   ├── input.tsx
    │   ├── label.tsx
    │   ├── toast.tsx
    │   ├── toaster.tsx
    │   └── use-toast.ts
/db
    ├── drizzle.ts
    ├── passwordResetTokensSchema.ts
    ├── schema.ts
    └── usersSchema.ts
/lib
    ├── email.ts
    └── utils.ts
/validation
    ├── passwordMatchSchema.ts
    └── passwordSchema.ts
```

## Iniziare 🚀

### Prerequisiti 📋

- Node.js
- npm o yarn
- Database PostgreSQL

### Installazione 💻

1. Clona il repository:

   ```sh
   git clone https://github.com/your-username/next-js-auth.git
   cd next-js-auth
   ```

2. Installa le dipendenze:

   ```sh
   npm install
   # oppure
   yarn install
   ```

3. Configura le variabili d'ambiente:
   Crea un file `.env.local` nella directory principale e aggiungi le seguenti variabili:

   ```env
   NEON_DATABASE_URL=your_neon_database_url
   RESEND_API_KEY=your_resend_api_key
   SITE_BASE_URL=http://localhost:3000
   ```

4. Esegui le migrazioni del database:

   ```sh
   npx drizzle-kit generate:pg
   ```

5. Avvia il server di sviluppo:
   ```sh
   npm run dev
   # oppure
   yarn dev
   ```

## Utilizzo 📖

- Visita `http://localhost:3000` per accedere all'applicazione.
- Registra un nuovo account, effettua il login ed esplora le funzionalità.

## Contributi 🤝

I contributi sono benvenuti! Per favore apri un'issue o invia una pull request per qualsiasi miglioramento o correzione di bug.

## Licenza 📄

Questo progetto è concesso in licenza sotto la Licenza MIT.

## Ringraziamenti 🙏

- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Drizzle ORM](https://github.com/drizzle-team/drizzle-orm)
- [Neon Database](https://neon.tech/)
- [bcryptjs](https://github.com/dcodeIO/bcrypt.js/)
- [nodemailer](https://nodemailer.com/)
- [zod](https://github.com/colinhacks/zod)
- [next-auth](https://next-auth.js.org/)
