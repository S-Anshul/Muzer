<h2>Muzer</h2>

Installation
With Docker
Clone the repository:

bash
Copy
Edit
git clone https://github.com/your-username/muzer.git
Navigate to the project directory:

bash
Copy
Edit
cd muzer
Create a .env file based on the .env.example file and configure everything in both the next-app and ws folders.

Start the application with Docker:

bash
Copy
Edit
docker compose up -d
Without Docker
Clone the repository:

bash
Copy
Edit
git clone https://github.com/your-username/muzer.git
Navigate to the project directory:

bash
Copy
Edit
cd muzer
Install the dependencies:

bash
Copy
Edit
cd next-app
pnpm install
cd ..
cd ws 
pnpm install
Create a .env file based on the .env.example file and configure everything in both the next-app and ws folders.

For PostgreSQL, run:
bash
Copy
Edit
docker run -d \
--name muzer-db \
-e POSTGRES_USER=myuser \
-e POSTGRES_PASSWORD=mypassword \
-e POSTGRES_DB=mydatabase \
-p 5432:5432 \
postgres
For Redis Stack, run:
bash
Copy
Edit
docker run -d \
--name muzer-redis \
-e REDIS_USERNAME=admin \
-e REDIS_PASSWORD=root \
-e REDIS_PORT=6379 \
-e REDIS_HOST="127.0.0.1" \
-e REDIS_BROWSER_STACK_PORT=8001 \
redis/redis-stack:latest 
Post-install setup:

bash
Copy
Edit
cd next-app
pnpm postinstall
cd ..
cd ws 
pnpm postinstall
Start the application:

bash
Copy
Edit
cd next-app
pnpm dev
cd ..
cd ws
pnpm dev
Usage
Open the app in your browser: http://localhost:3000

Access Redis Stack: http://localhost:8001/redis-stack/browser

Open Prisma Studio:

bash
Copy
Edit
cd next-app
pnpm run prisma:studio
Prisma Studio URL: http://localhost:5555
