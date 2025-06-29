# 🚨 Fixing Expo Go 502 Error

## What's Causing the 502 Error

A 502 error in Expo Go usually means:
- Development server connection issues
- Network connectivity problems
- Metro bundler configuration issues
- API route conflicts

## 🔧 Quick Fixes (Try in Order)

### 1. Restart Development Server
```bash
# Stop current server (Ctrl+C)
# Clear Metro cache and restart
npx expo start --clear
```

### 2. Check Network Connection
- Ensure your phone and computer are on the **same WiFi network**
- Disable VPN if you're using one
- Try switching to mobile hotspot temporarily

### 3. Use Tunnel Mode
```bash
npx expo start --tunnel
```
This creates a public URL that bypasses local network issues.

### 4. Clear Expo Go Cache
- **iOS**: Delete and reinstall Expo Go app
- **Android**: Go to Settings > Apps > Expo Go > Storage > Clear Cache

### 5. Check for Port Conflicts
```bash
# Kill any processes using port 8081
npx kill-port 8081
# Restart with specific port
npx expo start --port 8082
```

### 6. Disable API Routes Temporarily
The 502 might be caused by your API routes. Let's temporarily disable them:

```bash
# Rename API files to disable them
mv app/signup-notification+api.ts app/signup-notification+api.ts.disabled
mv app/test-notification+api.ts app/test-notification+api.ts.disabled
```

Then restart:
```bash
npx expo start --clear
```

## 🔍 Advanced Troubleshooting

### Check Metro Config
Create/update `metro.config.js`:

```javascript
const { getDefaultConfig } = require('expo/metro-config');

const config = getDefaultConfig(__dirname);

module.exports = config;
```

### Check for Environment Issues
```bash
# Check if .env file is causing issues
mv .env .env.backup
npx expo start --clear
```

### Network Diagnostics
```bash
# Check if development server is running
curl http://localhost:8081
# Should return Metro bundler page
```

## 📱 Alternative: Use Development Build

If Expo Go continues having issues, switch to a development build:

```bash
# Install EAS CLI
npm install -g @expo/eas-cli

# Login
eas login

# Build for your device
eas build --platform android --profile development
# or for iOS
eas build --platform ios --profile development
```

## 🎯 Most Common Solutions

**90% of 502 errors are fixed by:**

1. **Restart with clear cache**: `npx expo start --clear`
2. **Use tunnel mode**: `npx expo start --tunnel`
3. **Same WiFi network**: Double-check both devices are connected to same network
4. **Disable API routes**: Temporarily rename `+api.ts` files

## 🆘 If Nothing Works

1. **Check Expo status**: Visit status.expo.dev
2. **Try different network**: Use mobile hotspot
3. **Update Expo Go**: Ensure latest version on phone
4. **Restart router**: Sometimes network equipment needs refresh

## 📞 Quick Test

Try this minimal test:
```bash
# Create new test project
npx create-expo-app TestApp
cd TestApp
npx expo start
```

If the test project works, the issue is with your current project configuration.