# Secure Face Attendance System

A serverless web application designed to manage attendance using secure face recognition technology. This project leverages AWS services to handle authentication and image storage, providing a seamless experience for both administrators and users.

## 🚀 Features

### 🔐 User Authentication

- **Secure Login**: Integrated with **AWS Cognito** for robust user identity management.
- **Role-Based Access Control**:
  - **Admin Mode**: Allows administrators to register new users by capturing their facial data and assigning a unique User ID.
  - **User Mode**: Standard users can log in to mark their attendance simply by capturing their face.

### 📸 Real-Time Face Capture

- **Camera Integration**: Utilizes the device's webcam to stream and capture real-time video.
- **Instant Processing**: Captures high-quality images directly from the browser for processing.

### ☁️ Serverless Architecture

- **AWS S3 Integration**: Captured images are uploaded directly to Amazon S3 buckets.
  - **Registration**: Admin uploads are stored in the `admin_faces/` directory.
  - **Attendance**: Daily attendance captures are stored in the `uploads/` directory with precise timestamps.
- **Client-Side Logic**: Built with vanilla **HTML5, CSS3, and JavaScript**, making it lightweight and easy to deploy.

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Cloud Services**:
  - **Amazon Cognito**: User Pool and Identity management.
  - **Amazon S3**: Object storage for face images.
- **Libraries**:
  - `aws-sdk-2.1259.0.min.js`
  - `amazon-cognito-identity.min.js`

## 📋 Usage

1.  **Login**: Enter valid credentials in the login form.
    - _Admin users_ will see the registration panel.
    - _Standard users_ will see the attendance marking interface.
2.  **Start Camera**: Click `CAMERA Start Camera` to enable the webcam.
3.  **Action**:
    - **For Admin**: Enter a User ID (e.g., `20BCS001`) and click `👤 Register Face`.
    - **For User**: Simply click `✅ Mark Attendance` to capture and upload your photo.
4.  **Status**: The application provides real-time feedback (Success/Error) on the operation.

## ⚙️ Configuration

The application is currently configured to connect to specific AWS resources defined in the code:

- **User Pool ID**: `ap-south-1_DBdAqQGEY`
- **Region**: `ap-south-1`
- **S3 Bucket**: `face-attendance-project-001`

> **Note**: For a production deployment, ensure CORS configurations on S3 and Cognito are correctly set to allow access from your hosting domain.
