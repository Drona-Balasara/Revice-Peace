# Revive Peace - Mental Wellness Web Application

![Revive Peace Logo](images/logo.png)

A comprehensive mental wellness web application designed to support users' mental health journey through various therapeutic features and interactive experiences.

## 🌟 Features

### Core Wellness Tools
- **🤖 AI Chat Bot**: 24/7 emotional support and guidance through intelligent conversation
- **📝 Digital Journaling**: Secure, private space for daily reflection and emotional processing
- **🎧 Binaural Beats**: Audio therapy for deep relaxation, focus enhancement, and stress relief
- **💆‍♀️ Therapy & Wellness**: Curated music collection, guided meditation, and gentle yoga practices

### Therapeutic Games
- **🧩 Puzzle Challenge**: Brain-teasing puzzles for problem-solving skills
- **🌿 Maze Navigation**: Peaceful maze exploration for spatial reasoning
- **🔍 Word Quest**: Hidden word games for vocabulary expansion
- **🟢 Simon Says**: Memory and pattern recognition training
- **🎯 Hangman**: Classic word guessing with difficulty levels
- **⚡ Reflex Click**: Reaction time improvement in a calming environment
- **🌸 Zen Garden**: Mindful relaxation experience

### Progress Tracking
- **📊 Dashboard**: Comprehensive statistics and progress tracking
- **🏆 Achievement System**: Win rates, scores, and personal bests
- **📈 Analytics**: Usage patterns and improvement insights

## 🚀 Live Demo

Visit the live application: [Revive Peace on Netlify](https://your-netlify-url.netlify.app)

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **UI Framework**: Bootstrap 4
- **Icons**: Font Awesome
- **Libraries**: jQuery
- **Storage**: Local Storage for data persistence
- **Architecture**: Multi-page responsive web application

## 📁 Project Structure

```
revive-peace/
├── html/                   # HTML pages
│   ├── main.html          # Homepage
│   ├── dashboard.html     # Progress dashboard
│   ├── Login.html         # User authentication
│   ├── journaling.html    # Digital journaling
│   ├── therapy.html       # Wellness tools
│   ├── games.html         # Games overview
│   └── [game-pages].html # Individual game pages
├── css/                   # Stylesheets
│   ├── style.css         # Main styles
│   ├── plugins.css       # Plugin styles
│   └── [feature].css     # Feature-specific styles
├── js/                    # JavaScript files
│   ├── jquery.min.js     # jQuery library
│   ├── custom.js         # Custom scripts
│   └── dz.*.js          # Additional utilities
├── images/               # Image assets
├── plugins/              # Third-party plugins
└── README.md            # Project documentation
```

## 🏃‍♂️ Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- No server setup required - runs entirely in the browser

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/revive-peace.git
   cd revive-peace
   ```

2. **Open the application**
   ```bash
   # Simply open html/main.html in your browser
   # Or use a local server (recommended)
   python -m http.server 8000
   # Then visit http://localhost:8000/html/main.html
   ```

### For Development
```bash
# If using VS Code with Live Server extension
# Right-click on html/main.html and select "Open with Live Server"
```

## 🌐 Deployment

### Netlify Deployment

1. **Automatic Deployment** (Recommended)
   - Fork this repository
   - Connect your GitHub account to Netlify
   - Select the repository and deploy
   - Set build command: (leave empty)
   - Set publish directory: `/`

2. **Manual Deployment**
   - Download the project as ZIP
   - Drag and drop the folder to Netlify dashboard
   - Your site will be live instantly

### GitHub Pages
```bash
# Enable GitHub Pages in repository settings
# Select source: Deploy from a branch
# Branch: main / (root)
```

## 🎮 How to Use

### Getting Started
1. Visit the homepage (`html/main.html`)
2. Explore different features through the navigation menu
3. Create an account or use as guest
4. Start your wellness journey!

### Key Features Usage

**Journaling**
- Navigate to Features → Journaling
- Write daily reflections and activities
- Entries are saved locally and privately

**Games**
- Access via Games menu or Features → Games
- Each game tracks your progress automatically
- View statistics in the Dashboard

**Therapy Tools**
- Explore calm music, meditation, and yoga
- Use binaural beats for focused relaxation
- All tools designed for immediate stress relief

## 🔧 Configuration

### AI Chat Bot Setup
The AI chat bot uses an external webhook. To configure:
1. Replace the webhook URL in navigation menus
2. Update the link in `html/main.html` and other pages
3. Current URL: `https://notknown.app.n8n.cloud/webhook/6d3062ae-c732-4b6a-a8c4-a8a4e1bc2872/chat`

### Customization
- **Colors**: Modify CSS variables in `css/style.css`
- **Content**: Update HTML files for text changes
- **Games**: Add new games by following existing patterns
- **Features**: Extend functionality in respective HTML/JS files

## 📱 Browser Compatibility

- ✅ Chrome 60+
- ✅ Firefox 55+
- ✅ Safari 12+
- ✅ Edge 79+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow existing code style and structure
- Test on multiple browsers
- Ensure mobile responsiveness
- Update documentation for new features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Bootstrap** for the responsive framework
- **Font Awesome** for beautiful icons
- **jQuery** for DOM manipulation
- **Mental Health Community** for inspiration and feedback

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/revive-peace/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/revive-peace/discussions)
- **Email**: support@revivepeace.com

## 🔮 Roadmap

- [ ] User account system with cloud sync
- [ ] Mobile app development
- [ ] Advanced AI chat bot features
- [ ] Community features and sharing
- [ ] Professional therapist integration
- [ ] Multilingual support
- [ ] Offline mode capabilities

---

**Made with ❤️ for mental wellness and inner peace**

*Remember: This application is designed to support your wellness journey but is not a replacement for professional mental health care. Please seek professional help if you're experiencing serious mental health issues.*