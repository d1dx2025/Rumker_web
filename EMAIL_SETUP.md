# Email Setup Guide for Rumker Contact Form

This guide will help you configure the contact form to send emails to `d1dx@proton.me`.

## Quick Setup

### 1. Backend Configuration

1. Navigate to the `backend` directory:
   ```bash
   cd backend
   ```

2. Copy the environment example file:
   ```bash
   cp env.example .env
   ```

3. Edit the `.env` file with your email configuration:

#### For ProtonMail (Recommended):
```env
EMAIL_SERVICE=protonmail
EMAIL_USER=d1dx@proton.me
EMAIL_PASS=your-protonmail-app-password
PORT=3001
```

#### For Gmail:
```env
EMAIL_SERVICE=gmail
EMAIL_USER=your-gmail@gmail.com
EMAIL_PASS=your-gmail-app-password
PORT=3001
```

#### For Outlook/Hotmail:
```env
EMAIL_SERVICE=outlook
EMAIL_USER=your-email@outlook.com
EMAIL_PASS=your-outlook-password
PORT=3001
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Start the Backend Server

```bash
npm start
```

The server will run on `http://localhost:3001`

### 4. Test the Contact Form

1. Open `index.html` in your browser
2. Fill out the contact form
3. Submit the form
4. You should be redirected to `success.html` upon successful submission

## Email Provider Setup Instructions

### ProtonMail Setup

1. Log into your ProtonMail account
2. Go to Settings → Security → App Passwords
3. Create a new app password for "Rumker Contact Form"
4. Use this app password in your `.env` file

### Gmail Setup

1. Enable 2-Factor Authentication on your Google account
2. Go to Google Account settings → Security → App passwords
3. Generate an app password for "Rumker Contact Form"
4. Use this app password in your `.env` file

### Outlook/Hotmail Setup

1. Use your regular email and password
2. Make sure "Less secure app access" is enabled (if using regular password)
3. Or use an app password if 2FA is enabled

## Features

✅ **Success Page**: Users are redirected to a beautiful success page after form submission  
✅ **Email Validation**: Comprehensive client-side and server-side validation  
✅ **Error Handling**: User-friendly error messages with visual feedback  
✅ **Fallback Support**: If backend is unavailable, opens email client with pre-filled message  
✅ **Multi-Provider Support**: Works with Gmail, ProtonMail, and Outlook  
✅ **Responsive Design**: Works on all devices  
✅ **Dark Mode**: Consistent with the main site design  

## Troubleshooting

### Backend Not Starting
- Check if port 3001 is available
- Verify all dependencies are installed (`npm install`)
- Check the `.env` file configuration

### Emails Not Sending
- Verify email credentials in `.env` file
- Check if the email service is correct
- For ProtonMail, ensure you're using an app password, not your regular password
- Check the console for error messages

### Form Not Working
- Ensure the backend server is running
- Check browser console for JavaScript errors
- Verify the form validation requirements are met

## Production Deployment

For production deployment:

1. Update the API URL in `script.js` to point to your production backend
2. Set up proper environment variables on your hosting platform
3. Ensure your email service allows SMTP connections from your hosting provider
4. Consider using a service like SendGrid or Mailgun for better deliverability

## Support

If you encounter any issues, check the browser console and server logs for error messages. The contact form includes comprehensive error handling and will guide users through any problems.
