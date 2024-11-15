# SyneiOS - Image Capture & Upload App

VIDEO - https://docs.google.com/document/d/1Bq4US6T7Ja8fM0ZN4o6VDwThje2m3k-aubDM6_vDajA/edit?tab=t.0

## Overview
SyneiOS is an iOS application built with SwiftUI that enables users to capture, store, and upload images with robust handling of duplicates, upload management, and user notifications. The app follows MVVM architecture and emphasizes clean code practices through protocol-oriented programming.

## Features
- 📸 Camera Integration with AVFoundation
- 🗄️ Local Storage using Realm Database
- 📤 Background Upload Management
- 🔄 Upload Progress Tracking
- 🔍 Duplicate Image Detection
- 📱 Rich Notifications
- 🎯 Upload Resume Capability

## Architecture
The project follows MVVM (Model-View-ViewModel) architecture with additional layers for services and managers:

### Core Components

#### Models
- `ImageModel`: Realm object model storing image data and metadata
  - Handles image data, upload status, and duplicate detection
  - Uses Realm for persistent storage

#### Views
- `MainView`: Main container view
- `CameraView`: Camera preview and capture interface
- `ImageListView`: Displays captured images with upload status
- `ImagePreviewView`: Full-screen image preview
- `ToastView`: Custom notification banner

#### ViewModels
- `ImageCaptureViewModel`: Core business logic
  - Manages image capture, storage, and upload
  - Handles duplicate detection
  - Coordinates between services

### Services & Managers

#### Camera Service
- Handles camera setup and image capture
- Uses AVFoundation for camera operations
- Provides Combine publisher for captured images

#### Upload Service
- Manages image upload operations
- Handles upload progress tracking
- Supports background uploads

#### Notification Manager
- Manages local notifications
- Handles notification permissions
- Provides rich notifications with thumbnails

#### Storage Manager
- Handles Realm database operations
- Manages image persistence
- Handles data migrations

### Extensions
Organized in dedicated folder for better maintainability:
- `CameraService+Delegate`: Camera capture delegate
- `Image+UIImage`: SwiftUI Image conversion utilities

## Key Features Implementation

### Image Capture
- Uses AVFoundation for camera access
- Provides real-time camera preview
- Captures high-quality images
- Provides visual feedback during capture

### Upload Management
- Background upload support
- Progress tracking with UI updates
- Automatic retry for failed uploads
- Resume capability for interrupted uploads

### Duplicate Detection
1. Generates hash for captured images
2. Compares with existing images
3. Provides user choice for duplicates:
   - Upload anyway
   - Delete duplicate

### Notifications
- Rich notifications with image thumbnails
- Different behavior for foreground/background
- Custom in-app toast notifications
- Upload completion notifications



