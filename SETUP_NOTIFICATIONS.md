# 🔔 Notification Setup Guide

This guide will help you set up **Discord webhooks** for instant notifications and **Resend** for professional emails.

## 🚀 Quick Setup (5 minutes)

### Step 1: Discord Webhook (FREE - Instant Notifications)

1. **Create a Discord Server** (if you don't have one):
   - Open Discord → Click "+" → "Create My Own" → "For me and my friends"
   - Name it "Reps N Results Notifications"

2. **Create a Webhook**:
   - Right-click your server → "Server Settings"
   - Go to "Integrations" → "Webhooks" → "New Webhook"
   - Name: "Signup Notifications"
   - Choose a channel (create #signups if needed)
   - Copy the "Webhook URL"

3. **Add to Environment**:
   ```bash
   DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/YOUR_WEBHOOK_ID/YOUR_TOKEN
   ```

### Step 2: Resend Setup (FREE - 3,000 emails/month)

1. **Sign up at [resend.com](https://resend.com)**
   - Use your email
   - Verify your account

2. **Get API Key**:
   - Go to "API Keys" in dashboard
   - Click "Create API Key"
   - Name: "Reps N Results"
   - Copy the key (starts with `re_`)

3. **Add to Environment**:
   ```bash
   RESEND_API_KEY=re_your_api_key_here
   ```

4. **Verify Domain** (Optional but recommended):
   - Go to "Domains" → "Add Domain"
   - Add your domain (e.g., `yourdomain.com`)
   - Follow DNS setup instructions
   - Use `welcome@yourdomain.com` as FROM_EMAIL

## 📱 Testing Your Setup

1. **Test Discord**:
   - Go to your webhook URL in browser
   - You should see webhook info
   - Try signing up in your app

2. **Test Resend**:
   - Check your Resend dashboard for email logs
   - New users should receive welcome emails
   - You should get admin notifications

## 🎯 What You'll Get

### Discord Notifications (Instant):
- 🎉 Real-time signup alerts on your phone
- 👤 User name and email
- ⏰ Signup timestamp
- 📱 Beautiful embed format

### Resend Emails (Professional):
- 📧 Welcome email to new users
- 🎨 Beautiful HTML design
- 📊 Admin notification emails
- 📈 Email analytics in dashboard

## 💡 Pro Tips

1. **Mobile Notifications**: Install Discord mobile app for instant push notifications
2. **Email Customization**: Edit the HTML in `signup-notification+api.ts` to match your branding
3. **Analytics**: Check Resend dashboard for email open rates and delivery stats
4. **Scaling**: Resend free tier handles 3,000 emails/month (100/day)

## 🔧 Environment Variables

Create a `.env` file in your project root:

```bash
# Discord (Free forever)
DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/YOUR_WEBHOOK_ID/YOUR_TOKEN

# Resend (3,000 emails/month free)
RESEND_API_KEY=re_your_api_key_here

# Optional: Custom domain emails
FROM_EMAIL=welcome@yourdomain.com
ADMIN_EMAIL=admin@yourdomain.com
```

## 🚨 Security Notes

- Never commit `.env` files to git
- Keep your webhook URLs and API keys private
- Use environment variables in production
- Resend API keys start with `re_`

## 📞 Need Help?

- **Discord Issues**: Check webhook URL format and permissions
- **Resend Issues**: Verify API key and domain setup
- **Email Delivery**: Check spam folders and Resend logs

---

**Ready to get notified?** Set up Discord first for instant gratification, then add Resend for professional emails! 🚀