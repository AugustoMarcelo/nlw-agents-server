# NLW Agents Backend

This is the backend application developed during the NLW Agents event by Rocketseat. It provides a robust API service built with modern TypeScript-first technologies.

## 🚀 Technologies

- [Node.js](https://nodejs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Fastify](https://fastify.io/) - Fast and low overhead web framework
- [PostgreSQL](https://www.postgresql.org/) - Relational database
- [Drizzle ORM](https://orm.drizzle.team/) - TypeScript ORM
- [Zod](https://zod.dev/) - TypeScript-first schema validation
- [Biome](https://biomejs.dev/) - Toolchain for web projects

## 📦 Project Structure

```
src/
├── db/           # Database configurations and migrations
├── http/         # HTTP routes and controllers
└── server.ts     # Main application entry
```

## 🛠️ Setup Instructions

1. Clone the repository
2. Install dependencies:

   ```bash
   npm install
   ```

3. Setup the database:

   - Make sure you have PostgreSQL running
   - Create a `.env` file based on the environment variables needed
   - The project uses Docker Compose for the database:
     ```bash
     docker compose up -d
     ```

4. Run database migrations:

   ```bash
   npx drizzle-kit migrate
   ```

5. Seed the database (optional):

   ```bash
   npm run db:seed
   ```

6. Start the development server:
   ```bash
   npm run dev
   ```

## 🔧 Available Scripts

- `npm run dev` - Start the development server with hot reload
- `npm start` - Start the production server
- `npm run db:seed` - Seed the database with initial data

## 🗄️ Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/database
```

## 📝 API Documentation

The API uses Fastify with TypeScript and Zod for type-safe routes and input validation. Endpoints are organized in the `src/http/routes` directory.
