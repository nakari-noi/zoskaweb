ls = where u at
cd Dokumenty = change diroctory
npx create-next-app@latest
npm run dev = node package manager
npm install @mui/material @emotion/react @emotion/styled
cd .. =posun o jeden hore

npm run build = kotrola chyb

GIT SETUP
git init
git branch -m main
git config user.name "SheenOFTime"
git config user.email "jakub.vaculik.2006@gmail.com"
git remote add remote <url>
git remote -v
git add .
git commit -m "initial commit"


PRISMA:
1. Vercel -> Storage:
    Neon -> Create -> Accept -> Region -> Frankfurt, Germany-(fra1) -> Connect
    in snap-zoska-4h-postgres:
    .env.local -> Show secret -> Copy snippet into your src/.env 

2. NextAuth:
    Get started -> Adapters -> Prisma 
    npm install @prisma/client @auth/prisma-adapter
    npm install prisma --save-dev
    npx prisma init

3. VsCode:
    In .env replace value of DATABASE_URL
    .env
    Create prisma.ts in src/app/api/auth/[...nextauth] -> copy code from NextAuth docs
    Update authOptions.ts -> add:   import { PrismaAdapter } from "@auth/prisma-adapter"
                                    import { prisma } from "./prisma"
                                    adapter: PrismaAdapter(prisma),

    package.json:   "build": "prisma generate && next build",
                    "postinstall": "prisma generate",


4. VsCode terminal:
    npx prisma format
    npx prisma migrate dev --name init
    npx prisma generate
    npx prisma studio