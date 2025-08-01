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
- [Google AI (Gemini)](https://ai.google.dev/) - AI model integration

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
- `npm run db:generate` - Generate database migrations
- `npm run db:migrate` - Apply database migrations
- `npm run db:seed` - Seed the database with initial data

## 🗄️ Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/database
GOOGLE_API_KEY=your-google-ai-api-key
```

## 📝 API Documentation

The API uses Fastify with TypeScript and Zod for type-safe routes and input validation. Endpoints are organized in the `src/http/routes` directory.

### Available Endpoints

- `GET /health` - Health check endpoint
- `GET /rooms` - List all rooms
- `POST /rooms` - Create a new room
- `GET /rooms/:roomId/questions` - Get questions for a specific room
- `POST /rooms/:roomId/questions` - Create a question in a room
- `POST /rooms/:roomId/audio` - Upload audio file for processing

All endpoints that accept data use JSON format, except for the upload endpoint which accepts multipart/form-data.
