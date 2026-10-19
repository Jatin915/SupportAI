# SupportAI

**AI-powered customer support chatbot SaaS**

SupportAI is a multi-tenant SaaS platform that enables businesses to create AI-powered customer support chatbots, configure their knowledge base, and embed chat widgets on their websites.

The goal is to provide businesses with an easy way to automate customer support while allowing owners to manage chatbot settings and review customer conversations from a dashboard.

> **Status:** Under active development.

## Planned Features

- **Business dashboard:** Manage chatbot configuration and business details.
- **Knowledge base:** Configure support information used to generate answers.
- **AI-powered responses:** Generate context-aware answers using Google's Gemini API.
- **Embeddable chat widget:** Add a chatbot to external websites using a script snippet.
- **Persistent conversations:** Allow anonymous visitors to revisit their recent conversations.
- **Conversation history:** Review visitor conversations and message transcripts.
- **Multi-tenant isolation:** Ensure each business can access only its own data.
- **Retrieval-Augmented Generation (RAG):** Improve answer relevance for larger knowledge bases in Stage 2.

These features are planned and will be marked as implemented as development progresses.

## Tech Stack

| Technology | Purpose |
|---|---|
| Next.js App Router | Application framework and API routes |
| TypeScript | Type safety |
| React | Dashboard UI |
| Tailwind CSS | Styling |
| Motion | Dashboard animations |
| MongoDB | Persistent application data |
| Mongoose | MongoDB schemas and data access |
| Scalekit | Authentication |
| Google Gemini API | AI-generated responses |
| Upstash Redis | API rate limiting |
| Vercel | Deployment target |

## Architecture Overview

The application is planned around three main components:

1. **Dashboard:** A private interface for business owners to configure their chatbots and review conversations.
2. **Backend APIs:** Handle authentication, chatbot configuration, conversation persistence, and AI response generation.
3. **Embeddable widget:** A lightweight JavaScript-based chat interface that can run on external websites, isolated using the Shadow DOM.

MongoDB will store chatbot configurations, conversations, and messages. Authentication will identify dashboard owners, while anonymous visitors will use conversation-specific tokens to restore their chat history.

## Getting Started

### Prerequisites

- Node.js
- npm
- MongoDB connection
- Required third-party credentials as their integrations are implemented

### Installation

Clone the repository and enter the project directory:

```bash
git clone https://github.com/Jatin915/SupportAI
cd support-ai
npm install
```

Create your local environment file:

```bash
cp .env.example .env.local
```

Add the required configuration values to `.env.local` when the corresponding integrations are implemented.

Start the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Environment Variables

See `.env.example` for the expected configuration keys.

**Security notes:**
- Never commit `.env.local` or real API credentials.
- Keep database credentials, authentication secrets, and AI API keys on the server.
- Use `NEXT_PUBLIC_` only for values that are safe to expose to the browser.

## Development Roadmap

- [x] Initial Next.js project setup
- [x] Initial environment configuration template
- [ ] Database connection and Mongoose models
- [ ] Scalekit authentication
- [ ] Dashboard layout and chatbot configuration
- [ ] Chatbot configuration APIs
- [ ] Gemini integration
- [ ] Embeddable chat widget
- [ ] Anonymous conversation persistence
- [ ] Conversation history
- [ ] Security testing and rate limiting
- [ ] Production deployment
- [ ] Stage 2: RAG and retrieval evaluation

*Checklist items should be updated as features are implemented and tested.*

## Security Principles

- Derive dashboard ownership from a verified authentication session.
- Never trust client-provided owner IDs for authorization.
- Treat public chatbot identifiers as identifiers, not secrets.
- Validate and limit public API inputs.
- Store only hashed conversation tokens where applicable.
- Keep secrets out of client-side code and version control.

## Project Goals

SupportAI is being developed as a practical full-stack and AI engineering project, with emphasis on secure multi-tenant architecture, API design, conversation persistence, reliable AI integration, and production deployment.

## License

No license has been selected yet.
