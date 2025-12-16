# Kandivali Motor Training Institute (KMTS) App

A React Native mobile application built with Expo for Kandivali Motor Training Institute. The app allows potential students to learn about services and submit enquiries directly through Firebase Firestore.

## Features

- **Home Screen**: Overview of KMTS with key features and benefits
- **Services Screen**: Detailed information about all training programs
- **Contact Screen**: Enquiry form with real-time validation
- **Firebase Integration**: All enquiries stored in Firestore
- **Email Notifications**: Automatic email alerts for new enquiries

## Tech Stack

- **Framework**: React Native with Expo SDK 54
- **Navigation**: Expo Router with Tab Navigation
- **Backend**: Firebase Firestore
- **Email**: EmailJS
- **Language**: TypeScript
- **Icons**: Lucide React Native

## Firebase Configuration

The app is pre-configured to use the following Firebase project:

- Project ID: `bots-db5aa`
- Firestore Collection: `enquiries`

All form submissions are automatically saved to Firestore with:
- Name
- Phone
- Email
- Course interested
- Message
- Timestamp
- Status (set to "new")

## Getting Started

### Prerequisites

- Node.js 18 or higher
- npm or yarn
- Expo CLI

### Installation

1. Install dependencies:
```bash
npm install
```

2. Configure EmailJS (see EMAILJS_SETUP.md)

3. Start the development server:
```bash
npm run dev
```

4. Scan the QR code with Expo Go app (iOS/Android) or press 'w' for web

## Project Structure

```
├── app/
│   ├── (tabs)/
│   │   ├── _layout.tsx      # Tab navigation configuration
│   │   ├── index.tsx         # Home screen
│   │   ├── services.tsx      # Services screen
│   │   └── contact.tsx       # Contact/Enquiry form
│   └── _layout.tsx           # Root layout
├── config/
│   └── firebase.ts           # Firebase configuration
├── services/
│   ├── enquiryService.ts     # Firestore operations
│   └── emailService.ts       # Email notifications
└── hooks/
    └── useFrameworkReady.ts  # Framework initialization hook
```

## Form Validation

The contact form includes comprehensive validation:

- **Name**: Required field
- **Phone**: Required, must be 10 digits
- **Email**: Required, must be valid email format
- **Course**: Required, dropdown selection
- **Message**: Optional

## Available Courses

1. Driving License
2. Car Training
3. Motorcycle Training
4. Commercial License

## Design Philosophy

The app follows a minimal, clean design aesthetic with:

- Blue primary color (#2563eb)
- Consistent spacing and typography
- Clear visual hierarchy
- Smooth user feedback
- Accessible color contrasts

## Email Notifications

Email notifications are sent via EmailJS when a new enquiry is submitted. See `EMAILJS_SETUP.md` for configuration instructions.

## Scripts

- `npm run dev` - Start development server
- `npm run build:web` - Build for web platform
- `npm run lint` - Run linter
- `npm run typecheck` - Run TypeScript type checking

## Production Deployment

The app uses Firebase credentials that work for both development and production. Ensure EmailJS is properly configured before deploying to production.

## Support

For questions or issues, please contact the KMTS administration.
