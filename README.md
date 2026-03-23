<div align="center">
  <br />
    <a href="https://one-connect-mprm.vercel.app" target="_blank">
      <img src="https://github.com/adrianhajdin/OneConnect/assets/151519281/a9cd1088-968b-4b1d-b21a-f5f97d0c202b" alt="OneConnect Banner">
    </a>
  <br />

  <div>
    <img src="https://img.shields.io/badge/-Next_JS-black?style=for-the-badge&logoColor=white&logo=nextdotjs&color=000000" alt="nextdotjs" />
    <img src="https://img.shields.io/badge/-MongoDB-black?style=for-the-badge&logoColor=white&logo=mongodb&color=47A248" alt="mongodb" />
    <img src="https://img.shields.io/badge/-Tailwind_CSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=06B6D4" alt="tailwindcss" />
    <img src="https://img.shields.io/badge/-Clerk-black?style=for-the-badge&logoColor=white&logo=clerk&color=6C47FF" alt="clerk" />
    <img src="https://img.shields.io/badge/-Shadcn_UI-black?style=for-the-badge&logoColor=white&logo=shadcnui&color=000000" alt="shadcnui" />
    <img src="https://img.shields.io/badge/-TypeScript-black?style=for-the-badge&logoColor=white&logo=typescript&color=3178C6" alt="typescript" />
  </div>

  <h3 align="center">OneConnect: The Ultimate Community Social Platform</h3>

  <p align="center">
    A high-performance social networking application built with Next.js 14, focusing on structured discussions, real-time community management, and professional UI/UX.
  </p>
</div>

## 📋 Table of Contents

1. 🤖 [Introduction](#introduction)
2. ⚙️ [Tech Stack](#tech-stack)
3. 📊 [ER Model & Architecture](#er-model)
4. 🔋 [Features](#features)
5. 🤸 [Quick Start](#quick-start)
6. 🚀 [Deployment](#deployment)

---

## <a name="introduction">🤖 Introduction</a>

Build a full stack **OneConnect** clone using Next.js 14. This application transforms complex Figma designs into a functional social platform featuring nested deep comments, real-time notifications, organization-based communities, and a blazing-fast user experience.

---

## <a name="tech-stack">⚙️ Tech Stack</a>

- **Framework**: Next.js 14 (App Router)
- **Database**: MongoDB (Mongoose ODM)
- **Auth**: Clerk (Email, Google, GitHub)
- **UI Components**: Shadcn UI & TailwindCSS
- **File Uploads**: UploadThing
- **Validation**: Zod & React Hook Form
- **Webhooks**: Svix (for Clerk-to-MongoDB sync)

---

## <a name="er-model">📊 ER Model & Data Flow</a>

OneConnect uses a relational-style NoSQL schema to ensure data integrity across social interactions.

### Entity Relationships:
* **User (1:N) Threads**: One user can author multiple OneConnect posts.
* **Thread (Recursive 1:N)**: A Thread can contain multiple "Children" Threads (Nested Comments).
* **Community (M:N) User**: Users can join multiple communities; communities manage hundreds of members.
* **Community (1:N) Threads**: Specific threads can be exclusive to an organization.

### How it Works:
1.  **Auth Sync**: Clerk handles the UI; a **Webhook** sends data to our server to create a matching MongoDB User.
2.  **Thread Nesting**: Each reply stores a `parentId`. The frontend recursively renders these to create the "Deep Thread" look.
3.  **Server Actions**: Instead of standard APIs, we use Next.js Server Actions for direct database mutation from the UI.

---

## <a name="features">🔋 Features</a>

👉 **Authentication**: Secure login/signup with comprehensive profile management.
👉 **OneConnect Creation**: Dedicated page for creating threads with image support.
👉 **Nested Commenting**: Structured conversation flow with infinite-depth replies.
👉 **Community Management**: Create communities, invite members, and assign roles.
👉 **Activity Notifications**: Instant alerts when users interact with your posts.
👉 **Real-Time Search**: Search for users or communities with server-side pagination.
👉 **SSR & SEO**: Server-side rendering for optimal performance and search visibility.

---

## <a name="quick-start">🤸 Quick Start</a>

**Prerequisites**
- Node.js (v18+)
- MongoDB Atlas Account
- Clerk Account

