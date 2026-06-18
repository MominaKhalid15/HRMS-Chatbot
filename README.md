
# HRMS Assistance Chatbot

## Description

An AI-powered HRMS help chatbot built using NestJS, TypeScript, and OpenAI API. The system uses a **Retrieval-Augmented Generation (RAG)** approach to provide context-aware responses based on HRMS documentation.

User queries are answered using OpenAI, with relevant context retrieved from Markdown files stored in the `dataset/` folder.

The application uses an in-memory vector-based retrieval system, where embeddings are generated at startup. No Docker or external vector database is required.

The system supports document updates by reloading embeddings when the server is restarted after changes in the dataset.
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
<br>
<img width="1374" height="950" alt="Screenshot (334)" src="https://github.com/user-attachments/assets/8d0953d5-5ace-45c4-aa59-d80d0e8256a9" />
<br>
<br><br><br>
<img width="1513" height="812" alt="Screenshot (335)" src="https://github.com/user-attachments/assets/fad4373c-2082-46b3-91e3-40af1004c41b" />
<br><br><br><br>
<img width="1477" height="873" alt="Screenshot (336)" src="https://github.com/user-attachments/assets/a67cb663-34e1-4201-b218-79eb7521a643" />
<br><br><br><br>
<img width="1515" height="788" alt="Screenshot (337)" src="https://github.com/user-attachments/assets/eadebb79-58fd-4ade-9452-4dab0bf2241b" />
<br><br><br><br>
<img width="1504" height="866" alt="Screenshot (338)" src="https://github.com/user-attachments/assets/11eb2569-8c19-4630-9714-e36fa60f1e1c" />
<br>

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
