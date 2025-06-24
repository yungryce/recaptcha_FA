<p align="center">
  <img src="https://img.shields.io/badge/Azure_Functions-2.0+-0062AD?logo=microsoftazure" alt="Azure Functions">
  <img src="https://img.shields.io/badge/Python-3.9+-3776AB?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Google_reCAPTCHA-Enterprise-4285F4?logo=google" alt="reCAPTCHA">
  <img src="https://img.shields.io/badge/Status-Active-success" alt="Status">
</p>

<div align="center">
  <h1>🛡️ reCAPTCHA Enterprise Function App</h1>
  <p><em>Serverless Bot Protection & Token Validation System</em></p>
</div>

---

## 📋 Table of Contents
- [📖 Overview](#-overview)
- [🎯 Learning Objectives](#-learning-objectives)
- [🛠️ Tech Stack](#️-tech-stack)
- [📁 Project Structure](#-project-structure)
- [🚀 Getting Started](#-getting-started)
- [💡 Usage](#-usage)
- [🏆 Key Features](#-key-features)
- [📚 Resources](#-resources)
- [👥 Contributors](#-contributors)

## 📖 Overview

This serverless Azure Function provides a comprehensive backend service for validating Google reCAPTCHA Enterprise tokens, implementing advanced bot protection and security measures for modern web applications. The system seamlessly integrates Azure Functions with Google Cloud's enterprise-grade reCAPTCHA service to deliver real-time threat assessment and automated abuse prevention.

Built with production-ready security patterns, this application demonstrates sophisticated cloud service integration, secure credential management, and robust API design. The function performs intelligent risk analysis, validates user interactions, and provides detailed assessment scores to help applications make informed security decisions.

## 🎯 Learning Objectives

Through this project, you will master:

- **Cloud Service Integration**: Connect Azure Functions with Google Cloud reCAPTCHA Enterprise
- **Security Implementation**: Implement enterprise-grade bot protection and threat detection
- **API Authentication**: Manage service account credentials and secure API communications
- **Risk Assessment**: Analyze and interpret reCAPTCHA risk scores and threat indicators
- **Error Handling**: Build robust validation and exception management systems
- **Production Security**: Implement secure credential management and API security patterns
- **Cross-Platform Integration**: Integrate multiple cloud service providers effectively

## 🛠️ Tech Stack

**Core Technologies:**
- **Azure Functions**: Serverless compute platform for HTTP-triggered security services
- **Python 3.9+**: Primary programming language with advanced security libraries
- **Google reCAPTCHA Enterprise**: Enterprise-grade bot protection and risk analysis

**Development Tools:**
- **Google Cloud SDK**: Comprehensive API client for reCAPTCHA Enterprise integration
- **Service Account Authentication**: Secure credential management for cross-cloud access
- **JSON Web APIs**: RESTful API design with structured response formatting
- **Azure Functions Core Tools**: Local development and testing environment

## 📁 Project Structure

```
recaptcha_FA/
├── function_app.py          # Main Azure Function with reCAPTCHA validation logic
├── host.json               # Function app runtime configuration
├── requirements.txt        # Python dependencies and Google Cloud libraries
├── .github/
│   └── workflows/          # CI/CD pipeline automation
├── ARCHITECTURE.md         # System design and security architecture
├── SKILLS-INDEX.md        # Technical skills and security competencies catalog
└── README.md              # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- **Azure Account**: Active Azure subscription with Functions service enabled
- **Google Cloud Account**: Project with reCAPTCHA Enterprise API enabled
- **Python 3.9+**: Local development environment with pip package manager
- **Azure Functions Core Tools**: For local testing and deployment
- **Google Cloud Service Account**: With reCAPTCHA Enterprise permissions
- **Git**: Version control system for code management

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd recaptcha_FA
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables**:
   ```bash
   # Create local.settings.json for local development
   {
     "IsEncrypted": false,
     "Values": {
       "AzureWebJobsStorage": "your-storage-connection-string",
       "FUNCTIONS_WORKER_RUNTIME": "python",
       "GOOGLE_APPLICATION_CREDENTIALS_JSON": "your-service-account-json",
       "GOOGLE_CLOUD_PROJECT_ID": "your-google-cloud-project-id",
       "RECAPTCHA_SITE_KEY": "your-recaptcha-site-key"
     }
   }
   ```

### Running the Project

1. **Local Development**:
   ```bash
   func start
   ```

2. **Deploy to Azure**:
   ```bash
   func azure functionapp publish <your-function-app-name>
   ```

3. **Test reCAPTCHA Validation**:
   ```bash
   curl -X POST "http://localhost:7071/api/verify_recaptcha" \
        -H "Content-Type: application/json" \
        -d '{"token":"your-recaptcha-token","action":"login"}'
## 💡 Usage

### reCAPTCHA Validation API

**Validate reCAPTCHA tokens and assess security risk:**

```bash
# Validate reCAPTCHA token with action verification
curl -X POST "http://localhost:7071/api/verify_recaptcha" \
     -H "Content-Type: application/json" \
     -d '{"token":"your-recaptcha-token","action":"login"}'
```

**Request Format:**
```json
{
  "token": "RECAPTCHA_TOKEN_FROM_CLIENT",
  "action": "EXPECTED_ACTION_NAME"
}
```

**Response Format:**
```json
{
  "status": 200,
  "message": "Success",
  "error": null,
  "data": {
    "score": 0.9,
    "reasons": []
  }
}
```

### Risk Score Interpretation

- **Score Range**: 0.0 to 1.0 (higher = more likely human)
- **0.9-1.0**: Very likely legitimate user interaction
- **0.7-0.8**: Likely human, monitor for patterns
- **0.3-0.6**: Suspicious activity, require additional verification
- **0.0-0.2**: Very likely bot or automated traffic

### Common Actions

- `login` - User authentication attempts
- `register` - Account creation workflows
- `contact` - Contact form submissions
- `purchase` - E-commerce transactions
- `comment` - User-generated content submission

## 🏆 Key Features

- **Enterprise-Grade Bot Protection**: Google reCAPTCHA Enterprise integration for advanced threat detection
- **Real-Time Risk Assessment**: Instant risk scoring with detailed threat analysis
- **Action Verification**: Prevents token reuse and ensures action authenticity
- **Service Account Security**: Secure cross-cloud authentication with Google Cloud
- **Structured API Responses**: Consistent JSON response format with detailed error handling
- **Comprehensive Logging**: Production-ready logging for security monitoring
- **Token Validation**: Complete token verification including validity and action matching
- **Error Resilience**: Robust exception handling for production environments
- **Performance Optimization**: Efficient API calls and minimal latency
- **Security Monitoring**: Built-in threat detection and analysis capabilities

## 📚 Resources

- [Google reCAPTCHA Enterprise Documentation](https://cloud.google.com/recaptcha-enterprise/docs)
- [Azure Functions Documentation](https://docs.microsoft.com/azure/azure-functions/)
- [Google Cloud Authentication Guide](https://cloud.google.com/docs/authentication)
- [Python Google Cloud SDK](https://cloud.google.com/python/docs/reference)
- [reCAPTCHA Score Interpretation](https://developers.google.com/recaptcha/docs/v3#interpreting_the_score)
- [SKILLS-INDEX.md](./SKILLS-INDEX.md) - Detailed security skills and competencies catalog
- [ARCHITECTURE.md](./ARCHITECTURE.md) - System design and security architecture

## 👥 Contributors

**Chigbu Joshua**
- 📧 Email: [chigbujoshua@yahoo.com](mailto:chigbujoshua@yahoo.com)
- 🐙 GitHub: [@yungryce](https://github.com/yungryce)
- 🎯 Role: Primary Author, Project Maintainer

*This project demonstrates advanced serverless security patterns and cross-cloud integration for enterprise-grade bot protection.*
