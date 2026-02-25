# 🔐 ShadowChat

> A decentralized, real-time chat application with end-to-end encryption, AI-powered moderation, and stunning glassmorphism UI.

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18+-61DAFB?logo=react)](https://reactjs.org/)
[![WebSocket](https://img.shields.io/badge/WebSocket-Enabled-FF6B00.svg)](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

## ✨ Features

### 🛡️ Security
- **End-to-End Encryption**: Uses TweetNaCl.js for military-grade encryption
- **Zero-Knowledge Architecture**: Servers never see plaintext messages
- **Decentralized Design**: No central authority storing user data

### 💬 Real-time Communication
- **WebSocket Integration**: Sub-second message delivery
- **Typing Indicators**: See when others are typing
- **Online Status**: Real-time presence detection
- **Read Receipts**: Know when messages are delivered

### 🤖 AI-Powered Features
- **Content Moderation**: ML-based spam and inappropriate content detection
- **Smart Message Suggestions**: AI-powered autocomplete and suggestions
- **Sentiment Analysis**: Real-time message sentiment tracking

### 🎨 UI/UX
- **Glassmorphism Design**: Modern, sleek interface with frosted glass effects
- **Dark Mode**: Eye-friendly theme optimized for long chats
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Smooth Animations**: Fluid transitions and micro-interactions

### 📊 Rich Features
- **Channel Management**: Create public and private channels
- **User Profiles**: Customize your avatar and bio
- **Message History**: Full-text searchable chat history (encrypted)
- **File Sharing**: Send encrypted files up to 100MB
- **Reactions & Emojis**: Rich expression with emoji support

## 🚀 Quick Start

### Prerequisites
- Node.js 18.0+
- npm or yarn
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/vibhu-weeboo/ShadowChat.git
cd ShadowChat

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env

# Start development server
npm run dev
```

### Environment Variables

Create a `.env` file in the root directory:

```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_WS_URL=ws://localhost:5000
NODE_ENV=development
```

## 📁 Project Structure

```
ShadowChat/
├── client/                  # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom React hooks
│   │   ├── crypto/         # Encryption utilities
│   │   ├── styles/         # TailwindCSS styles
│   │   └── utils/          # Helper functions
│   └── package.json
├── server/                  # Node.js backend
│   ├── src/
│   │   ├── routes/         # API endpoints
│   │   ├── websocket/      # WebSocket handlers
│   │   ├── models/         # Database models
│   │   ├── middleware/     # Express middleware
│   │   ├── ai/             # AI moderation engine
│   │   └── utils/          # Helper utilities
│   └── package.json
├── docs/                    # Documentation
└── .github/                 # GitHub specific files
```

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **TailwindCSS** - Utility-first CSS
- **Framer Motion** - Animation library
- **TweetNaCl.js** - Cryptography
- **Socket.IO Client** - Real-time communication
- **Redux Toolkit** - State management

### Backend
- **Node.js + Express** - Server runtime
- **WebSocket (ws)** - Real-time protocol
- **MongoDB** - NoSQL database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication
- **TensorFlow.js** - AI moderation

## 🔐 Encryption Architecture

ShadowChat uses TweetNaCl.js for public-key cryptography:

1. **Key Generation**: Each user has a unique keypair (public + private)
2. **Message Encryption**: Messages encrypted with recipient's public key
3. **Decryption**: Only recipient can decrypt using their private key
4. **Server**: Stores encrypted data, never sees plaintext

## 📚 API Documentation

### WebSocket Events

```javascript
// Client to Server
socket.emit('send-message', { recipientId, encryptedMessage, nonce });
socket.emit('typing', { channelId });
socket.emit('user-online', { userId });

// Server to Client
socket.on('message-received', (data) => { });
socket.on('user-typing', (data) => { });
socket.on('online-users', (data) => { });
```

### REST API

```bash
# Authentication
POST /api/auth/register
POST /api/auth/login
POST /api/auth/logout

# Users
GET  /api/users/:id
GET  /api/users/search/:query
PUT  /api/users/:id

# Channels
GET  /api/channels
POST /api/channels
GET  /api/channels/:id

# Messages
GET  /api/messages/:channelId?limit=50
POST /api/messages
```

## 🧪 Testing

```bash
# Run unit tests
npm run test

# Run integration tests
npm run test:integration

# Generate coverage report
npm run test:coverage
```

## 🚀 Deployment

### Deploy to Vercel (Frontend)

```bash
npm install -g vercel
vercel
```

### Deploy to Railway/Render (Backend)

1. Push your code to GitHub
2. Connect your repository on Railway or Render
3. Set environment variables
4. Deploy!

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 Commit Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: Add new feature
fix: Fix bug
docs: Update documentation
style: Code style changes
refactor: Code refactoring
test: Add/update tests
chore: Maintenance tasks
```

## 🐛 Bug Reports

Found a bug? Please open an issue with:
- Description of the bug
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots (if applicable)

## 📖 Documentation

Detailed documentation is available in the `/docs` folder:
- [Architecture Guide](docs/architecture.md)
- [Security Documentation](docs/security.md)
- [API Reference](docs/api-reference.md)
- [Contribution Guidelines](docs/contributing.md)

## 🗺️ Roadmap

- [ ] End-to-end encryption v2 (Post-quantum cryptography)
- [ ] Video/Audio calling
- [ ] Message reactions and threading
- [ ] File backup and cloud sync
- [ ] Mobile app (React Native)
- [ ] Desktop app (Electron)
- [ ] Plugin system for extensions
- [ ] Multi-language support

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- TweetNaCl.js for cryptographic primitives
- The open-source community for inspiration
- All contributors who help improve ShadowChat

## 💬 Support

- 📧 Email: support@shadowchat.dev
- 💬 Discord: [Join our community](https://discord.gg/shadowchat)
- 🐙 GitHub Issues: [Report issues](https://github.com/vibhu-weeboo/ShadowChat/issues)

---

<div align="center">

**Made with ❤️ by the ShadowChat team**

⭐ Star us on GitHub if you find ShadowChat useful!

</div>
