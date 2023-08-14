
# My Full-Stack Firebase Demo Project

## Introduction

This is a demo project that illustrates the use of Firebase in a full-stack application. The project is built with Svelte for the front end, Node.jsand express for the back end, and Firebase as the database. It showcases user authentication, real-time updates, and various other Firebase features.

## Features

- **User Authentication**: Sign-up, log-in, and log-out with Firebase Authentication.
- **Real-time Database**: Storing and retrieving data in real-time using Firebase's Cloud Firestore.
- **File Storage**: Upload and manage files with Firebase Storage.
- **Hosting**: Leverage Firebase Hosting for rapid deployment.

## Prerequisites

Ensure you have the following installed on your system:

- Node.js (v14 or higher)
- npm (v6 or higher)
- Firebase CLI

## Installation

1. **Clone the repository:**


   git clone https://github.com/LMunoz34/Leel.Svelte.FullStack
   cd Leel.Svelte.FullStack


2. **Install dependencies:**


   npm install


3. **Set up Firebase:**

   Create a new project in your [Firebase Console](https://console.firebase.google.com/). Then, navigate to your project settings to find your config object. Replace the configuration in `src/firebaseConfig.js` with your config object.

4. **Start the development server:**


   npm start


## Deployment

To deploy the project using Firebase Hosting:

1. **Build the project:**

   ```bash
   npm run build
   ```

2. **Deploy with Firebase:**

   ```bash
   firebase deploy
   ```

## Usage

Visit `http://localhost:5173` (or your deployed URL) in your browser to explore the application.

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to proceed.

## License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.

## Support

If you encounter any problems or have suggestions, please open an issue, or contact me directly at your-email@example.com.

## Acknowledgements

Thanks to Firebase for making real-time applications simpler and more scalable!

---

