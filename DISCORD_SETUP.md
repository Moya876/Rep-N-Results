# 🔔 Discord Notification Setup - Quick Fix Guide

## The Issue
You're not receiving Discord notifications when users sign up. Let's fix this step by step!

## 🚀 Quick Setup (2 minutes)

### Step 1: Create Discord Webhook

1. **Open Discord** (desktop or web)
2. **Go to your server** (or create one):
   - Click "+" in server list
   - "Create My Own" → "For me and my friends"
   - Name: "App Notifications"

3. **Create Webhook**:
   - Right-click your server name
   - "Server Settings"
   - "Integrations" → "Webhooks"
   - "New Webhook"
   - Name: "Signup Alerts"
   - Choose channel: #general (or create #signups)
   - **Copy the Webhook URL** (looks like: `https://discord.com/api/webhooks/123456789/abcdef...`)

### Step 2: Add to Environment

1. **Create/Edit `.env` file** in your project root:
```bash
DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/YOUR_WEBHOOK_ID/YOUR_TOKEN
```

2. **Replace with your actual webhook URL** from Step 1

### Step 3: Test It!

1. **Sign up in your app** with a test account
2. **Check Discord** - you should see a beautiful notification!
3. **Check browser console** for any error messages

## 🔍 Troubleshooting

### Not Working? Check These:

1. **Webhook URL Format**:
   ```
   ✅ Correct: https://discord.com/api/webhooks/123456789/abcdef...
   ❌ Wrong: https://discord.com/channels/123456789/987654321
   ```

2. **Environment Variable**:
   - Make sure `.env` file is in project root
   - No spaces around the `=`
   - Restart your dev server after adding

3. **Discord Permissions**:
   - Make sure you have "Manage Webhooks" permission
   - Webhook channel should allow messages

4. **Check Console Logs**:
   - Open browser dev tools
   - Look for Discord-related errors
   - Check if webhook URL is being loaded

## 📱 Mobile Notifications

To get notifications on your phone:

1. **Install Discord mobile app**
2. **Enable push notifications** in Discord settings
3. **Join your server** on mobile
4. **Test signup** - you'll get instant push notifications!

## 🎯 What You'll See

When someone signs up, you'll get:
- 🎉 Instant Discord notification
- 👤 User's name and email
- ⏰ Signup timestamp
- 📱 Beautiful embed with app branding
- 🔔 Push notification on your phone

## 🆘 Still Not Working?

1. **Test webhook directly**:
   - Go to your webhook URL in browser
   - Should show webhook info (not 404)

2. **Check environment**:
   ```bash
   # In terminal, check if env var is loaded:
   echo $DISCORD_WEBHOOK_URL
   ```

3. **Try a simple test**:
   - Use a webhook testing tool
   - Send a basic message to verify webhook works

## 💡 Pro Tip

Create a dedicated #signups channel for cleaner notifications:
1. Create new text channel: #signups
2. Update webhook to use this channel
3. Mute other channels if you only want signup alerts

---

**Need help?** The webhook URL is the most common issue - make sure it's the full webhook URL, not a channel link!