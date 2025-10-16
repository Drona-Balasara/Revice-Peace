# Deployment Guide for Revive Peace

This guide covers different deployment options for the Revive Peace mental wellness application.

## 🌐 Netlify Deployment (Recommended)

### Automatic Deployment from GitHub

1. **Prepare Repository**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Connect to Netlify**
   - Go to [Netlify](https://netlify.com)
   - Click "New site from Git"
   - Connect your GitHub account
   - Select the `revive-peace` repository

3. **Configure Build Settings**
   - Build command: (leave empty)
   - Publish directory: `.` (root)
   - Click "Deploy site"

4. **Custom Domain (Optional)**
   - Go to Site settings → Domain management
   - Add custom domain
   - Configure DNS settings

### Manual Deployment

1. **Prepare Files**
   ```bash
   # Create a zip file of your project
   zip -r revive-peace.zip . -x "*.git*" "node_modules/*" "*.DS_Store*"
   ```

2. **Deploy to Netlify**
   - Go to [Netlify](https://netlify.com)
   - Drag and drop the zip file to the deploy area
   - Your site will be live instantly

### Environment Variables (if needed)
```bash
# In Netlify dashboard → Site settings → Environment variables
SITE_URL=https://your-site.netlify.app
```

## 📄 GitHub Pages

### Setup GitHub Pages

1. **Repository Settings**
   - Go to repository Settings
   - Scroll to "Pages" section
   - Source: Deploy from a branch
   - Branch: `main` / `(root)`
   - Save

2. **Access Your Site**
   - URL: `https://yourusername.github.io/revive-peace/html/main.html`
   - May take a few minutes to be available

### Custom Domain for GitHub Pages
```bash
# Create CNAME file in root directory
echo "your-domain.com" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push origin main
```

## 🔧 Vercel Deployment

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   # Follow the prompts
   ```

3. **Configure vercel.json**
   ```json
   {
     "rewrites": [
       { "source": "/", "destination": "/html/main.html" },
       { "source": "/(.*)", "destination": "/html/main.html" }
     ]
   }
   ```

## 🐳 Docker Deployment

### Create Dockerfile
```dockerfile
FROM nginx:alpine

# Copy all files to nginx html directory
COPY . /usr/share/nginx/html/

# Copy custom nginx config
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

### Create nginx.conf
```nginx
server {
    listen 80;
    server_name localhost;
    root /usr/share/nginx/html;
    index html/main.html;

    location / {
        try_files $uri $uri/ /html/main.html;
    }

    location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }
}
```

### Build and Run
```bash
# Build Docker image
docker build -t revive-peace .

# Run container
docker run -p 8080:80 revive-peace
```

## ☁️ AWS S3 + CloudFront

### S3 Setup
```bash
# Create S3 bucket
aws s3 mb s3://revive-peace-app

# Upload files
aws s3 sync . s3://revive-peace-app --exclude "*.git*" --exclude "node_modules/*"

# Configure bucket for static website hosting
aws s3 website s3://revive-peace-app --index-document html/main.html --error-document html/main.html
```

### CloudFront Distribution
```bash
# Create CloudFront distribution (via AWS Console)
# Origin: S3 bucket
# Default root object: html/main.html
```

## 🔍 Firebase Hosting

1. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**
   ```bash
   firebase init hosting
   # Select existing project or create new
   # Public directory: . (current directory)
   # Single-page app: No
   # Overwrite index.html: No
   ```

3. **Configure firebase.json**
   ```json
   {
     "hosting": {
       "public": ".",
       "ignore": [
         "firebase.json",
         "**/.*",
         "**/node_modules/**"
       ],
       "rewrites": [
         {
           "source": "**",
           "destination": "/html/main.html"
         }
       ]
     }
   }
   ```

4. **Deploy**
   ```bash
   firebase deploy
   ```

## 🚀 Performance Optimization

### Image Optimization
```bash
# Compress images before deployment
# Use tools like ImageOptim, TinyPNG, or automated solutions
```

### CSS/JS Minification
```bash
# For production, consider minifying CSS and JS files
# Tools: UglifyJS, CleanCSS, or build tools like Webpack
```

### CDN Configuration
```html
<!-- Use CDN for common libraries -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<link href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/4.6.0/css/bootstrap.min.css" rel="stylesheet">
```

## 🔒 Security Headers

### Netlify (_headers file)
```
/*
  X-Frame-Options: DENY
  X-XSS-Protection: 1; mode=block
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src 'self' https://fonts.gstatic.com;
```

### Apache (.htaccess)
```apache
<IfModule mod_headers.c>
    Header always set X-Frame-Options DENY
    Header always set X-XSS-Protection "1; mode=block"
    Header always set X-Content-Type-Options nosniff
    Header always set Referrer-Policy "strict-origin-when-cross-origin"
</IfModule>
```

## 📊 Analytics Setup

### Google Analytics
```html
<!-- Add to all HTML pages before closing </head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🔧 Custom Domain Setup

### DNS Configuration
```
# A Records
@ → 185.199.108.153
@ → 185.199.109.153
@ → 185.199.110.153
@ → 185.199.111.153

# CNAME Record
www → yourusername.github.io
```

## 📱 PWA Configuration (Optional)

### Create manifest.json
```json
{
  "name": "Revive Peace",
  "short_name": "RevivePeace",
  "description": "Mental wellness web application",
  "start_url": "/html/main.html",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#007bff",
  "icons": [
    {
      "src": "images/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "images/icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

### Service Worker (sw.js)
```javascript
const CACHE_NAME = 'revive-peace-v1';
const urlsToCache = [
  '/html/main.html',
  '/css/style.css',
  '/js/jquery.min.js',
  '/images/logo.png'
];

self.addEventListener('install', event => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(cache => cache.addAll(urlsToCache))
  );
});

self.addEventListener('fetch', event => {
  event.respondWith(
    caches.match(event.request)
      .then(response => response || fetch(event.request))
  );
});
```

## 🐛 Troubleshooting

### Common Issues

1. **404 Errors**
   - Check file paths are correct
   - Ensure index.html redirects are configured
   - Verify build output directory

2. **CSS/JS Not Loading**
   - Check relative paths
   - Verify MIME types are correct
   - Check for CORS issues

3. **Images Not Displaying**
   - Verify image paths
   - Check image file formats
   - Ensure images are included in deployment

### Debug Commands
```bash
# Test local server
python -m http.server 8000

# Check file structure
find . -name "*.html" -o -name "*.css" -o -name "*.js"

# Validate HTML
# Use online validators or browser dev tools
```

## 📞 Support

For deployment issues:
- Check the hosting provider's documentation
- Review error logs in hosting dashboard
- Test locally first to isolate issues
- Contact support if needed

---

Choose the deployment method that best fits your needs. Netlify is recommended for its simplicity and features, while GitHub Pages is great for open-source projects.