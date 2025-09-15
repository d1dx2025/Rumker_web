# Rumker Web - Cyber Intelligence Platform

A modern, responsive website for Rumker's cyber intelligence and investigations platform.

## Features

- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Dark Mode**: Toggle between light and dark themes
- **Contact Form**: Sends emails to d1dx@proton.me when submitted
- **Modern UI**: Built with Tailwind CSS and custom styling
- **Smooth Animations**: Intersection Observer for scroll animations

## Setup Instructions

### Frontend (Static Website)

The frontend is a static website that can be served from any web server. Simply open `index.html` in a browser or serve it using a local server.

### Backend (Email Service)

To enable email sending functionality, you need to set up the backend service:

1. **Navigate to the backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up environment variables:**
   - Copy `env.example` to `.env`
   - Update the email configuration:
     ```
     EMAIL_USER=your-email@gmail.com
     EMAIL_PASS=your-app-password
     PORT=3001
     ```

4. **For Gmail users:**
   - Enable 2-factor authentication
   - Generate an App Password (not your regular password)
   - Use the App Password in `EMAIL_PASS`

5. **Start the backend server:**
   ```bash
   npm start
   # or for development with auto-restart:
   npm run dev
   ```

6. **Update the frontend API URL:**
   - In `script.js`, change the `API_URL` from `http://localhost:3001/api/contact` to your production URL if deploying

## How It Works

### Contact Form Email Flow

1. **User fills out the contact form** with name, email, service interest, and message
2. **Form validation** ensures all required fields are filled and email format is valid
3. **Email sending** happens in two ways:
   - **Primary**: Backend API sends email directly to d1dx@proton.me using Nodemailer
   - **Fallback**: If backend is unavailable, opens user's email client with pre-filled mailto link

### Email Content

The email sent to d1dx@proton.me includes:
- Subject: "New Contact Form Submission - [Service Interest]"
- Sender information (name, email)
- Service interest selection
- User's message
- Formatted in both HTML and plain text

## File Structure

```
Rumker_web/
├── index.html          # Main HTML file
├── script.js           # Frontend JavaScript
├── styles.css          # Custom CSS styles
├── backend/            # Backend email service
│   ├── server.js       # Express.js server
│   ├── package.json    # Node.js dependencies
│   └── env.example     # Environment variables template
└── README.md           # This file
```

## Technologies Used

- **Frontend**: HTML5, CSS3, JavaScript (ES6+), Tailwind CSS
- **Backend**: Node.js, Express.js, Nodemailer
- **Email Service**: Gmail SMTP (configurable)

## Deployment

### Frontend
Deploy the static files (`index.html`, `script.js`, `styles.css`) to any web hosting service.

### Backend
Deploy the backend to a Node.js hosting service like:
- Heroku
- Vercel
- Railway
- DigitalOcean App Platform

Remember to:
1. Set environment variables on your hosting platform
2. Update the `API_URL` in `script.js` to point to your deployed backend
3. Configure CORS if needed for your domain

## Security Notes

- The backend includes basic validation
- Email credentials should be stored securely as environment variables
- Consider adding rate limiting for production use
- The frontend includes input sanitization

## Support

For questions or issues, contact d1dx@proton.me
