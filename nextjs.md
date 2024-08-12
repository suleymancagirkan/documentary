# Next.js 14 Özeti (React Framework)
Bu doküman, Next.js 14'ün temel özelliklerini ve önemli kavramlarını kapsamaktadır.

## 1. Kurulum ve Proje Oluşturma
Next.js 14 projesi oluşturmak için:

```bash
npx create-next-app@latest
```

Bu komut, interaktif bir kurulum süreci başlatacaktır.

## 2. Proje Yapısı
Temel Next.js 14 proje yapısı:

```
my-app/
  ├── app/
  │   ├── layout.js
  │   ├── page.js
  │   └── globals.css
  ├── public/
  ├── package.json
  └── next.config.js
```

## 3. Routing
Next.js 14, dosya sistemi tabanlı routing kullanır.

### Temel Routing
- `app/page.js`: Ana sayfa
- `app/about/page.js`: `/about` rotası

### Dinamik Rotalar
```javascript
// app/blog/[slug]/page.js
export default function Post({ params }) {
  return <div>Post: {params.slug}</div>
}
```

### Catch-all Rotalar
```javascript
// app/shop/[...slug]/page.js
export default function Category({ params }) {
  const { slug } = params
  // slug bir dizi olacaktır
}
```

## 4. Layouts
Sayfa düzenlerini tanımlamak için `layout.js` dosyaları kullanılır.

```javascript
// app/layout.js
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```

## 5. Data Fetching
Next.js 14'te veri çekme için üç yöntem bulunur:

### Server Components içinde
```javascript
async function getData() {
  const res = await fetch('https://api.example.com/data')
  return res.json()
}

export default async function Page() {
  const data = await getData()
  return <main>{/* data kullanımı */}</main>
}
```

### Client Components içinde
```javascript
'use client'

import { useState, useEffect } from 'react'

export default function Page() {
  const [data, setData] = useState(null)

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(res => res.json())
      .then(setData)
  }, [])

  return <main>{/* data kullanımı */}</main>
}
```

### Route Handlers
```javascript
// app/api/route.js
export async function GET() {
  const res = await fetch('https://api.example.com/data')
  const data = await res.json()
  return Response.json({ data })
}
```

## 6. Server ve Client Components
Next.js 14, server ve client components'i destekler.

### Server Component
```javascript
// Varsayılan olarak tüm componentler server component'tir
export default function ServerComponent() {
  return <div>Bu bir server component</div>
}
```

### Client Component
```javascript
'use client'

import { useState } from 'react'

export default function ClientComponent() {
  const [count, setCount] = useState(0)
  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  )
}
```

## 7. API Routes
API rotaları, `/app/api` dizini altında tanımlanır.

```javascript
// app/api/hello/route.js
export async function GET(request) {
  return new Response('Hello, Next.js!')
}
```

## 8. Image Optimization
Next.js'in yerleşik Image componenti ile görsel optimizasyonu:

```javascript
import Image from 'next/image'

export default function Page() {
  return (
    <Image
      src="/profile.jpg"
      alt="Profile"
      width={500}
      height={500}
    />
  )
}
```

## 9. Font Optimization
Next.js 14'te font optimizasyonu:

```javascript
import { Inter } from 'next/font/google'

const inter = Inter({ subsets: ['latin'] })

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={inter.className}>
      <body>{children}</body>
    </html>
  )
}
```

## 10. Static Site Generation (SSG)
Statik sayfalar oluşturmak için:

```javascript
// app/blog/[slug]/page.js
export async function generateStaticParams() {
  const posts = await getPosts()
  return posts.map((post) => ({
    slug: post.slug,
  }))
}

export default function Post({ params }) {
  return <div>Post: {params.slug}</div>
}
```

## 11. Incremental Static Regeneration (ISR)
ISR için `revalidate` seçeneğini kullanın:

```javascript
export const revalidate = 60 // Her 60 saniyede bir yeniden doğrula

export default async function Page() {
  const data = await fetchData()
  return <main>{/* data kullanımı */}</main>
}
```

## 12. Environment Variables
`.env.local` dosyasında tanımlanan ortam değişkenleri:

```
DB_HOST=localhost
DB_USER=myuser
DB_PASS=mypassword
```

Kullanım:
```javascript
console.log(process.env.DB_HOST)
```

## 13. Middleware
Özel middleware oluşturma:

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(request) {
  return NextResponse.redirect(new URL('/home', request.url))
}

export const config = {
  matcher: '/about/:path*',
}
```

## 14. Error Handling
Özel hata sayfaları oluşturma:

```javascript
// app/error.js
'use client'

export default function Error({ error, reset }) {
  return (
    <div>
      <h2>Bir şeyler yanlış gitti!</h2>
      <button onClick={() => reset()}>Tekrar dene</button>
    </div>
  )
}
```

## 15. Internationalization (i18n)
Next.js 14'te çoklu dil desteği:

```javascript
// next.config.js
module.exports = {
  i18n: {
    locales: ['en', 'fr', 'de'],
    defaultLocale: 'en',
  },
}
```

@suleymancagirkan
