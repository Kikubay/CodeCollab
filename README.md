# CodeCollab - Collaborative Code Editor

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

## 🚀 Overview

CodeCollab is a powerful web-based collaborative code editor that allows developers to write, share, and execute code in real-time. With built-in version control, multi-user collaboration, and secure code execution, it's the perfect tool for pair programming, teaching, or remote collaboration.

## ✨ Features

- **Real-time Collaboration**: Multiple users can edit code simultaneously with live cursor tracking
- **Multi-language Support**: Write and execute code in JavaScript, Python, Ruby, and more
- **Version Control**: Track changes with built-in version history and easy rollback
- **Chat System**: Communicate with collaborators in real-time without leaving the editor
- **File Management**: Create, organize, and manage files and folders in your workspace
- **Access Control**: Control who can view, edit, or execute your code
- **Code Execution**: Run your code directly in the browser with secure sandboxed execution
- **Custom Themes**: Choose from light or dark themes for comfortable coding

## 🛠️ Tech Stack

- **Frontend**: React, Socket.io client, Monaco Editor
- **Backend**: Node.js, Express
- **Database**: MongoDB
- **Real-time Communication**: Socket.io
- **Authentication**: JWT (JSON Web Tokens)

## 📋 Prerequisites

- Node.js (v18.0.0 or higher) [Download](https://nodejs.org/en/download/)
- npm (v9.0.0 or higher) - *Included with Node.js installation*
- MongoDB Atlas (Free Tier) [Sign Up](https://www.mongodb.com/cloud/atlas/register)
  + We use MongoDB Atlas for database hosting - no local installation required.
  + Free tier includes 512MB storage and shared clusters.
  + Perfect for development and small projects.

  ##

  + If you still want a open source alternative, I recommend using [FerretDB](https://www.github.com/FerretDB/FerretDB) but you'll have to change some code in the project.

## 🔧 Installation

1. **Clone the repository**
   ```
   git clone https://github.com/Kikubay/codecollab.git
   cd codecollab
   ```

2. **Install dependencies**
   ```
   # Install server dependencies
   npm install

   # Install client dependencies
   cd client
   npm install
   ```

3. **Environment Variables**

   Create `.env` in the root directory with the following:
   ```
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/codecollab
   JWT_SECRET=your_jwt_secret
   JWT_EXPIRE=30d
   ```

   Create `.env` in the client directory:
   ```
   REACT_APP_API_URL=http://localhost:5000/api
   REACT_APP_SOCKET_URL=http://localhost:5000
   ```

4. **Start the application**
   ```
   # Start MongoDB (if not running as a service)
   mongod

   # In the root directory, run:
   npm run dev
   ```

## 🖥️ Usage

1. **Register/Login**: Create an account or login to access your workspace
2. **Dashboard**: View and manage your files, or create a new file
3. **Editor**: Write and edit code with syntax highlighting and auto-completion
4. **Collaboration**: Share the file URL with others to collaborate in real-time
5. **Execution**: Run your code and see the output directly in the editor
6. **Version Control**: Save versions of your code and revert when needed

## 🔌 API Endpoints

| Method | Endpoint                      | Description                              |
|--------|-------------------------------|------------------------------------------|
| POST   | /api/auth/register            | Register a new user                      |
| POST   | /api/auth/login               | Login and get token                      |
| GET    | /api/files                    | Get all files for user                   |
| POST   | /api/files                    | Create a new file                        |
| GET    | /api/files/:id                | Get file by ID                           |
| PUT    | /api/files/:id/content        | Update file content                      |
| POST   | /api/execute                  | Execute code                             |
| GET    | /api/version/:fileId          | Get version history                      |
| POST   | /api/version/:fileId          | Create a new version                     |

## 👥 Collaboration Features

The real-time collaboration is powered by Socket.io and includes:

- **Content Synchronization**: All changes are immediately synced to all connected users
- **Cursor Tracking**: See where other users are editing with colored cursors
- **User Presence**: Know who is currently viewing or editing the file
- **Chat System**: Discuss changes or provide feedback without switching context

## 🔒 Security

- All API endpoints are protected with JWT authentication
- Code execution is sandboxed to prevent server vulnerabilities
- File access is controlled by the owner through collaborator permissions

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 To-Do List

- [ ] **Multilingual Support**:
    + Add support for more programming languages to cater to a broader range of developers.

- [ ] **UI/UX Overhaul**:
    + Improve the overall user interface and user experience to make CodeCollab more intuitive and visually appealing.

- [ ] **AI-powered Development Tools**:
    + Integrate AI-driven features, including:
        + Code Completion: Provide intelligent code suggestions to boost developer productivity.
        + Refactoring: Offer automated code refactoring to improve code quality and maintainability.
        + Chat: Implement a chat-based interface for users to interact with CodeCollab.
        + Intellisense: Enhance code editing with intelligent code insights and suggestions.

- [ ] **File System Management**:
    + Integrate file system management using the navigator option, allowing CodeCollab to access and manage project folders, enabling features like:
        + Project organization
        + File navigation
        + Folder creation and management

#### Let me know if you'd like me to make any further changes or additions to the project.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
