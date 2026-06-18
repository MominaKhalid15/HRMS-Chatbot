# HRMS Help Chatbot Backend

## Description

NestJS backend for an HRMS help chatbot. User questions are answered with OpenAI using context retrieved from Markdown files in the `dataset/` folder.

No Docker and no separate vector database are required: embeddings are built in memory when the app starts.

---

## Project Setup

```bash
cp .env.example .env
# Set OPENAI_API_KEY in .env

npm install
```

Add or edit HRMS documentation as `.md` files under `dataset/` (for example `dataset/hrms-guide.md`).

Restart the server after changing files so chunks are re-embedded.

---

## Compile and Run the Project

### Development

```bash
npm run start
```

### Watch Mode

```bash
npm run start:dev
```

### Production Mode

```bash
npm run build && npm run start:prod
```

---

## Chat API (Swagger / Postman / curl)

### Swagger UI

```text
http://localhost:3000/api
```

Try `POST /chat` directly from the Swagger UI.

### Chat Endpoint

```http
POST http://localhost:3000/chat
```

(or your configured PORT)

### Request Body

```json
{
  "message": "How do I apply for leave?"
}
```

### Response

```json
{
  "response": "..."
}
```

---

## Screenshots

### Swagger UI

![Swagger UI](screenshots/swagger-ui.png)

### Chat Request

![Chat Request](screenshots/chat-request.png)

### Chat Response

![Chat Response](screenshots/chat-response.png)

> Add your screenshots to a `screenshots/` folder in the repository and update the filenames if needed.

---

## Run Tests

### Unit Tests

```bash
npm run test
```

### E2E Tests

```bash
npm run test:e2e
```

### Test Coverage

```bash
npm run test:cov
```

---

## Deployment

When you're ready to deploy your NestJS application to production, there are some key steps you can take to ensure it runs as efficiently as possible.

If you are looking for a cloud-based platform to deploy your NestJS application, check out Mau, the official platform for deploying NestJS applications on AWS.

```bash
npm install -g @nestjs/mau
mau deploy
```

With Mau, you can deploy your application in just a few clicks, allowing you to focus on building features rather than managing infrastructure.

---

## License

Nest is MIT licensed.
