# Notification Deep Link in SwiftUI

This project demonstrates how to handle deep linking in SwiftUI using **push notifications**. 
It allows users to navigate to specific pages when a notification is received.

## Screenshots

_(Add screenshots here if needed)_

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Acknowledgments](#acknowledgments)

## Features

- **Deep Linking via Notifications**: Opens a specific page when a push notification is received.  
- **NavigationStack Integration**: Uses SwiftUI’s `NavigationStack` to handle navigation paths.  
- **Observable App State**: Utilizes `@Observable` `AppData` to manage app-wide navigation.  
- **Push Notification Handling**: Requests and processes notifications using `UNUserNotificationCenterDelegate`.  

## Project Structure

- **NotificationDeepLinkApp**: The main `@App` struct that initializes the app and sets up `AppData` as an environment object.  
- **ContentView**: Displays a list of navigation links and handles deep linking navigation.  
- **AppData**:  
  - Manages app-wide navigation paths.  
  - Implements `UIApplicationDelegate` and `UNUserNotificationCenterDelegate` for notification handling.  
  - Extracts `pageLink` from the notification payload to update the navigation path.  

## Installation

1. **Clone the Repository**:  
   ```bash
   git clone https://github.com/mohitDhami87/NotificationDeepLinkApp.git
   cd NotificationDeepLink
   ```

2. **Open in Xcode**:  
   ```bash
   open NotificationDeepLink.xcodeproj
   ```

3. **Build and Run**:  
   - Select the desired simulator or device.  
   - Press `Cmd + R` to build and run the project.  
   - Ensure push notification permissions are granted.  

## Usage

1. When the app launches, it requests **push notification permissions**.  
2. Clicking on a list item navigates to a different view using `NavigationLink`.  
3. When a push notification is received with a `"pageLink"` key, the app will **automatically navigate** to the corresponding view.  
4. If you want to maintain previous page instead of redirected to main page, then remove this line `"mainPageNavigationPath = []"` from didReceive delegate.

## Acknowledgments

This project provides a simple implementation of deep linking via push notifications in SwiftUI, leveraging `NavigationStack` and `UNUserNotificationCenterDelegate`.  

