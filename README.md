# GHS Privacy Policy

A static website hosting the privacy policy for the GHS application, designed for deployment on DigitalOcean.

## Overview

This repository contains a simple, responsive static HTML page that displays the privacy policy for the GHS mobile application. The site is built with pure HTML and CSS (no build process required) for easy deployment and maintenance.

## Features

- 📱 Fully responsive design that works on all devices
- 🎨 Clean, professional styling with modern CSS
- ⚡ Fast loading with no external dependencies
- 🚀 Simple deployment process
- ♿ Accessible and SEO-friendly

## Local Development

To view the site locally:

1. Clone this repository:
   ```bash
   git clone https://github.com/VIPlearner/ghs-privacy-policy.git
   cd ghs-privacy-policy
   ```

2. Open `index.html` in your web browser:
   ```bash
   # On macOS
   open index.html
   
   # On Linux
   xdg-open index.html
   
   # On Windows
   start index.html
   ```

   Or use a local web server:
   ```bash
   # Using Python 3
   python3 -m http.server 8000
   
   # Using Node.js
   npx http-server
   ```

3. Navigate to `http://localhost:8000` in your browser

## Deployment on DigitalOcean

### Option 1: DigitalOcean App Platform (Recommended)

1. Log in to your DigitalOcean account
2. Go to the App Platform
3. Click "Create App"
4. Connect your GitHub repository (`VIPlearner/ghs-privacy-policy`)
5. Select the branch to deploy (e.g., `main`)
6. DigitalOcean will automatically detect this as a static site
7. Configure the following settings:
   - **Build Command:** (leave empty)
   - **Output Directory:** `/`
   - **HTTP Routes:** `/`
8. Review and launch the app

### Option 2: DigitalOcean Spaces + CDN

1. Create a DigitalOcean Space
2. Enable CDN on the Space
3. Upload `index.html` to the Space
4. Make the file public or configure appropriate permissions
5. Access via the Space's CDN endpoint

### Option 3: DigitalOcean Droplet

1. Create a Droplet with Ubuntu
2. Install Nginx:
   ```bash
   sudo apt update
   sudo apt install nginx
   ```
3. Clone this repository:
   ```bash
   cd /var/www
   sudo git clone https://github.com/VIPlearner/ghs-privacy-policy.git
   ```
4. Configure Nginx to serve the site:
   ```bash
   sudo nano /etc/nginx/sites-available/privacy-policy
   ```
   Add:
   ```nginx
   server {
       listen 80;
       server_name your-domain.com;
       root /var/www/ghs-privacy-policy;
       index index.html;
       
       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```
5. Enable the site and restart Nginx:
   ```bash
   sudo ln -s /etc/nginx/sites-available/privacy-policy /etc/nginx/sites-enabled/
   sudo nginx -t
   sudo systemctl restart nginx
   ```

## Customization

To customize the privacy policy:

1. Edit `index.html`
2. Update the content in the relevant sections
3. Modify the "Last Updated" date
4. Update contact information in the "Contact Us" section
5. Adjust styling in the `<style>` section if needed

## File Structure

```
ghs-privacy-policy/
├── index.html          # Main privacy policy page
└── README.md          # This file
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## License

Copyright © 2024 GHS. All rights reserved.

## Contact

For questions about this privacy policy site, please contact:
- Email: privacy@ghs.app