# Task4
# Robot Arm Control System (Flutter + PHP + MySQL)

A complete system to control a robotic arm using sliders, save poses, and manage them through a Flutter mobile app and PHP backend with MySQL database.

## 📁 Project Structure

```
project_root/
├── robot_arm_flutter/
│   ├── lib/
│   │   └── main.dart
│   └── pubspec.yaml
│
├── robot_api/
│   ├── get_run_pose.php
│   ├── save_pose.php
│   ├── delete_pose.php
│   └── robot_arm_db.sql
```

## ⚙ Requirements

- Flutter SDK
- XAMPP (Apache + MySQL)
- VS Code or Android Studio
- Android emulator or physical device (optional for testing)

## 🚀 How to Use

### 1. Database Setup

1. Open XAMPP.
2. Start **Apache** and **MySQL**.
3. Open [http://localhost/phpmyadmin](http://localhost/phpmyadmin) in your browser.
4. Click **Import**, then choose the file `robot_arm_db.sql` from the `robot_api` folder.
5. Click **Go** to create the database and table.

### 2. Backend Setup (PHP)

1. Copy the entire `robot_api` folder into:
   ```
   C:\xampp\htdocs\
   ```
2. Final path should be:
   ```
   C:\xampp\htdocs\robot_api\
   ```

### 3. Flutter Setup

1. Open the `robot_arm_flutter` folder using VS Code or Android Studio.
2. Run:
   ```
   flutter pub get
   ```
3. In `lib/main.dart`, ensure all API URLs use this base:
   ```
   http://10.0.2.2/robot_api/
   ```
   > If you're using an emulator.  
   > If you're on a real Android device, use your local IP (e.g., `192.168.x.x`).

4. Run the app:
   ```
   flutter run
   ```

## 💡 Features

- 4 sliders to control motors.
- Save current pose to database.
- View all saved poses.
- Delete any pose.
- Uses HTTP requests to communicate with PHP backend.

## 📝 Notes

- The backend is written in plain PHP using `mysqli` (no frameworks).
- MySQL database contains one table `poses`.
- The app assumes 0–180 range for each motor.
- The system works offline on localhost.
