# 🚧 Проект (без названия)

[![Vue 3](https://img.shields.io/badge/Vue-3.5-42b883.svg?logo=vue.js)](https://vuejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-6.0-3178c6.svg?logo=typescript)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-8.0-646cff.svg?logo=vite)](https://vitejs.dev/)
[![ESLint](https://img.shields.io/badge/ESLint-10.2-4b32c3.svg?logo=eslint)](https://eslint.org/)
[![Vercel](https://img.shields.io/badge/Deployed-Vercel-000000.svg?logo=vercel)](https://vercel.com)

Современное веб-приложение на **Vue 3 + TypeScript + Vite**. Автоматизация через GitHub Actions, деплой на Vercel.

## 🌐 Демо

[https://frontend-vadim.vercel.app/](https://frontend-vadim.vercel.app/)

## 🛠 Технологии

| Технология | Версия |
|------------|--------|
| Vue | 3.5.32 |
| TypeScript | 6.0 |
| Vite | 8.0 |
| ESLint | 10.2 |

# 1. Установите зависимости
npm install

# 2. Запустите сервер для разработки
npm run dev
# Приложение: http://localhost:5173

# 3. Сборка для продакшена
npm run build
# Перед сборкой: vue-tsc -b (проверка типов)

# 4. Предпросмотр собранного проекта
npm run preview

# 5. Проверка и исправление кода
npm run lint           # Проверка ESLint (--max-warnings 0)
npm run lint:fix       # Авто-исправление ошибок
