# 🛡️ WeLe Guard v3.0 — AI Chat Community Moderator
### GlitchCon 2.0 · GBA_1 · Semantic AI + Agentic Moderation

---

## 🚀 SETUP (5 steps)

### 1. Install Node.js
https://nodejs.org → LTS → Install → verify: `node -v`

### 2. Open in VS Code
File → Open Folder → wele-guard → Terminal (Ctrl+`)

### 3. Install dependencies
```
npm install
```

### 4. Get FREE Groq API Key
1. https://console.groq.com → Sign up free
2. API Keys → Create API Key
3. Copy key (starts with `gsk_`)

### 5. Run & open
```
npm run dev
```
Open http://localhost:5173

---

## 👥 DEMO ACCOUNTS

| Role | Email | Password |
|------|-------|----------|
| 👑 Admin | admin@wele.com | admin123 |
| 👤 Learner | alex@wele.com | user123 |
| 🎓 Mentor | priya@wele.com | user123 |
| 👤 Learner | sam@wele.com | user123 |

---

## 🆕 v3.0 FEATURES

### Separate Role-Based Login
- Admin → full dashboard (users, groups, global rules)
- Learner/Mentor → chat with onboarding (skillset + group selection)

### Agentic Context Resolution
- User enters their skillset on first login
- Before each message, an AI agent calls `/api/agent/resolve-context`
- Agent gets: user skillset + group semantic context + message
- Returns: relevance score, reasoning, suggested group if off-topic
- This context is fed INTO the main moderation prompt

### Semantic AI Moderation (not keyword-based)
- Python ML question in Data Science group → SAFE ✅
- Python for Java REST API integration → SAFE ✅  
- "Can I use Python?" in Java group → BORDERLINE (agent decides based on context)
- Netflix discussion anywhere → BLOCKED ✅
- No keyword blacklists — pure LLM semantic understanding

### Admin Controls
- Ban/unban users directly
- Edit group semantic context (what the AI understands about each group)
- Add/remove allowed and disallowed topic hints
- View all users + violation counts

