# Deployment Guide

## Email Configuration

The contact form sends emails to `team@virtunera.com` using Zoho Mail SMTP.

### Setting Up Environment Variables

1. Copy `env.example` to `.env`:
   ```bash
   cp env.example .env
   ```

2. Edit `.env` and fill in your Zoho Mail credentials:
   ```
   SMTP_USER=your-email@virtunera.com
   SMTP_PASS=your-zoho-password
   ```

### Required Environment Variables

- `SMTP_USER` - Your Zoho Mail email address (required)
- `SMTP_PASS` - Your Zoho Mail password (required)
- `SMTP_FROM` - Sender name/email (optional, defaults to "Virtu Nera <no-reply@virtunera.com>")
- `SMTP_HOST` - SMTP server (optional, defaults to "smtp.zoho.com")
- `SMTP_PORT` - SMTP port (optional, defaults to 587)
- `SMTP_SECURE` - Use SSL (optional, defaults to false for port 587)

### Hosting Platform Setup

When deploying to platforms like:
- **Vercel/Netlify**: Add environment variables in the platform dashboard
- **Railway/Render**: Add environment variables in the service settings
- **VPS/Server**: Set environment variables in your deployment script or systemd service

### Testing

- In development: Emails are logged to the console
- In production: Emails are sent via SMTP to `team@virtunera.com`

### Troubleshooting

If emails aren't sending:
1. Verify SMTP credentials are correct
2. Check that environment variables are set in your hosting platform
3. Ensure port 587 is not blocked by firewall
4. For Zoho Mail, you may need to enable "Less Secure Apps" or use an App Password


