<h1>Muzer</h1>
This project includes both frontend and backend services with Docker support, Redis, PostgreSQL, and Prisma.

<h2>Installation</h2>

<h2>With Docker</h2>

1.Clone the repository:
`git clone https://github.com/your-username/muzer.git`

2.Navigate to the project directory:
`cd muzer`

3.Set up environment files:
Create a .env file based on the .env.example in both the next-app and ws folders.

4.Start the app with Docker:
`docker compose up -d`


<h3>Without Docker</h3>

1.Clone the repository:
`git clone https://github.com/your-username/muzer.git`

2.Navigate to the project directory:
`cd muzer`

3.Install dependencies:
`cd next-app
npm install
cd ../ws
npm install`

4.Set up environment files:
Create a .env file based on the .env.example in both the next-app and ws folders.

5.Run PostgreSQL using Docker:
`docker run -d \
  --name muzer-db \
  -e POSTGRES_USER=myuser \
  -e POSTGRES_PASSWORD=mypassword \
  -e POSTGRES_DB=mydatabase \
  -p 5432:5432 \
  postgres`

6.Run Redis Stack using Docker:
`docker run -d \
  --name muzer-redis \
  -e REDIS_USERNAME=admin \
  -e REDIS_PASSWORD=root \
  -e REDIS_PORT=6379 \
  -e REDIS_HOST="127.0.0.1" \
  -e REDIS_BROWSER_STACK_PORT=8001 \
  redis/redis-stack:latest`
  
7.Post-install steps:
`cd next-app
pnpm postinstall
cd ../ws
pnpm postinstall`

8.Start the development servers:
`cd next-app
pnpm dev
cd ../ws
pnpm dev`

<h3>Usage</h3>

🌐 Open the app: http://localhost:3000

📊 Access Redis Stack UI: http://localhost:8001/redis-stack/browser

🔍 Open Prisma Studio:
`cd next-app
pnpm run prisma:studio
URL: http://localhost:5555`
