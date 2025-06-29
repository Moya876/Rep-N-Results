# 📱 Running Your App on Phone

## Quick Start (Expo Go)

1. **Install Expo Go** on your phone from App Store/Google Play
2. **Start dev server**: `npm run dev`
3. **Scan QR code** with your phone camera (iOS) or Expo Go app (Android)

⚠️ **Note**: Some features like notifications may not work in Expo Go due to native dependencies.

## Full Features (Development Build)

For full functionality including notifications, you'll need a development build:

### Step 1: Install EAS CLI
```bash
npm install -g @expo/eas-cli
```

### Step 2: Login to Expo
```bash
eas login
```

### Step 3: Configure Project
```bash
eas build:configure
```

### Step 4: Build for Your Device

**For iOS (iPhone):**
```bash
eas build --platform ios --profile development
```

**For Android:**
```bash
eas build --platform android --profile development
```

### Step 5: Install on Device

**iOS:**
- Download the `.ipa` file from the build link
- Install using TestFlight or direct installation

**Android:**
- Download the `.apk` file from the build link
- Install directly on your device (enable "Install from unknown sources")

### Step 6: Install Expo Dev Client
```bash
npx expo install expo-dev-client
```

### Step 7: Start Development Server
```bash
npx expo start --dev-client
```

## 🔧 Troubleshooting

### Common Issues:

1. **QR Code not working**:
   - Ensure same WiFi network
   - Try typing the URL manually in Expo Go

2. **Build failing**:
   - Check your bundle identifier is unique
   - Ensure all dependencies are compatible

3. **Notifications not working**:
   - Use development build, not Expo Go
   - Check environment variables are set

### Alternative: Expo Tunnel

If WiFi issues persist:
```bash
npx expo start --tunnel
```

This creates a public URL that works on any network.

## 📊 Testing Features

### What works in Expo Go:
- ✅ Basic UI and navigation
- ✅ Most React Native features
- ✅ Basic API calls

### What requires Development Build:
- 🔔 Push notifications
- 📧 Email notifications
- 🔐 Advanced native features
- 📱 Custom native modules

## 🚀 Production Testing

For final testing before app store:
```bash
eas build --platform ios --profile preview
eas build --platform android --profile preview
```

This creates production-like builds for final testing.