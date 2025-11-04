# AttendEase 📱

**AttendEase** is a comprehensive mobile attendance management system built with Expo and React Native. It streamlines the process of tracking student attendance in educational institutions using RFID technology and geolocation verification.

## 🎯 Features

### For Students
- **RFID-Based Check-in**: Quick attendance marking using RFID cards
- **Course Registration**: Register for courses and view enrolled courses
- **Attendance Records**: View personal attendance history and statistics
- **Real-time Sessions**: See active attendance sessions for enrolled courses
- **Profile Management**: Update profile information and change PIN/password
- **Device Binding**: Secure account access with device-specific authentication
- **Support System**: Submit and track support tickets

### For Lecturers
- **Session Management**: Start and end attendance sessions with geolocation tracking
- **Course Management**: View and manage assigned courses
- **Attendance Tracking**: Monitor student attendance in real-time
- **Schedule Management**: Create and manage class schedules
- **Device Authorization**: Authorize students' new devices by scanning QR codes for secure access
- **Reports**: Generate attendance reports for courses

### For Administrators
- **College Management**: Create and manage colleges/faculties
- **Department Management**: Organize departments within colleges
- **Course Management**: Create and assign courses to departments
- **Student Management**: Register and manage student accounts
- **Lecturer Management**: Register and manage lecturer accounts
- **RFID Card Management**: Assign and track RFID cards
- **Analytics**: View system-wide attendance statistics

## 🛠️ Technology Stack

- **Frontend**: React Native with Expo
- **Routing**: Expo Router (file-based routing)
- **Backend**: Supabase (PostgreSQL database, Authentication, Storage)
- **State Management**: Zustand
- **UI Components**: Custom components with @gorhom/bottom-sheet
- **MQTT**: Real-time communication for RFID card scanning
- **AI Integration**: Groq API for intelligent features
- **Geolocation**: Expo Location for session verification
- **Camera**: Expo Camera for QR code scanning and image capture

## � Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- Expo CLI
- iOS Simulator (for Mac) or Android Emulator
- Supabase account (for backend services)

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Aherobo1/AttendEase.git
cd AttendEase
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Copy the `.env.example` file to `.env` and fill in your credentials:

```bash
cp .env.example .env
```

Required environment variables:
- `EXPO_PUBLIC_SUPABASE_PROJECT_URL`: Your Supabase project URL
- `EXPO_PUBLIC_SUPABASE_ANON_KEY`: Your Supabase anonymous key
- `EXPO_PUBLIC_MQTT`: MQTT broker credentials for RFID communication
- `EXPO_PUBLIC_GROQ_API_KEY`: Groq API key for AI features

### 4. Start the development server

```bash
npx expo start
```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## 📁 Project Structure

```
attendease/
├── app/                    # Main application code (Expo Router)
│   ├── (root)/            # Root layout
│   │   ├── (app)/         # Main app screens
│   │   │   ├── (tabs)/    # Bottom tab navigation
│   │   │   ├── (admin)/   # Admin management screens
│   │   │   ├── (card)/    # RFID card management
│   │   │   ├── (college)/ # College management
│   │   │   ├── (course)/  # Course management
│   │   │   └── ...        # Other feature modules
│   │   └── (auth)/        # Authentication screens
│   └── _layout.tsx        # Root layout configuration
├── api/                   # API handlers for Supabase
│   ├── handleAuth.ts
│   ├── handleStudents.ts
│   ├── handleLecturers.ts
│   ├── handleAttendanceSessions.ts
│   ├── handleAttendanceRecords.ts
│   ├── handleRfidCards.ts
│   └── ...
├── components/            # Reusable UI components
├── constants/             # App constants and configuration
├── hooks/                 # Custom React hooks
├── stores/                # Zustand state management
├── types/                 # TypeScript type definitions
├── utilities/             # Helper functions
└── assets/                # Images, fonts, and SVG files
```

## 🔑 Key Features Explained

### Multi-Factor Authentication
The system implements a robust multi-factor authentication strategy using IoT devices:
1. **RFID Card Verification**: Students use RFID cards for quick check-in
2. **PIN Authentication**: Additional security layer with PIN verification
3. **Geolocation Verification**: Ensures students are physically present in the classroom
4. **Device Binding**: Students' accounts are bound to their mobile devices. If a student attempts to log in on a new device, access is denied until a lecturer authorizes the device by scanning a QR code displayed on the student's new device
5. **Biometric Support**: Device-level biometric authentication for enhanced security

### Real-time Communication
- MQTT protocol for real-time RFID card scanning
- WebSocket connections for live attendance updates
- Instant notifications for attendance confirmations

### Attendance Session Management
- Lecturers start sessions with geolocation tracking
- Students must be within a specified radius to mark attendance
- Automatic session expiration
- Comprehensive attendance reports

## 🛡️ Security Features

- Secure authentication with Supabase
- Row-level security (RLS) policies
- Encrypted data transmission
- PIN-based secondary authentication
- **Device-specific authorization**: Each student account is bound to their registered device, preventing unauthorized access from other devices
- **QR Code-based Device Authorization**: Lecturers can authorize new student devices by scanning QR codes, ensuring controlled access
- Device-specific authorization
- Biometric authentication support

## 📱 Supported Platforms

- ✅ iOS (iPhone & iPad)
- ✅ Android (Phone & Tablet)
- 🚧 Web (Limited functionality)

## 🔧 Configuration

### Supabase Setup
1. Create a Supabase project
2. Run the database migrations (schema available in documentation)
3. Configure Row Level Security policies
4. Enable authentication providers
5. Set up storage buckets for profile images

### MQTT Broker Setup
Configure your MQTT broker credentials for RFID device communication:
- Broker URL
- Authentication credentials
- Topic subscriptions for card scanning events

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Aherobo1**
- GitHub: [@Aherobo1](https://github.com/Aherobo1)
- Repository: [AttendEase](https://github.com/Aherobo1/AttendEase)

## 🙏 Acknowledgments

- Built with [Expo](https://expo.dev)
- Backend powered by [Supabase](https://supabase.com)
- AI capabilities by [Groq](https://groq.com)
- Icons from [@expo/vector-icons](https://icons.expo.fyi)

## 📚 Documentation & Resources

For more detailed documentation about the project architecture and implementation:
- See the research documentation: `CHAPTER ONE - MULTIFACTOR AUTHENTICATION STRATEGY USING IoTs FOR ENHANCED STUDENT'S ATTENDANCE MANAG.docx`

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.
