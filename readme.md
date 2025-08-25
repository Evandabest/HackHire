# HackHire 🚀

An intelligent recruitment platform designed to help Johnson & Johnson discover and hire top software engineering talent for internships and full-time roles through AI-powered candidate matching and team formation.

## 🎯 Overview

HackHire transforms the traditional hiring process by leveraging machine learning algorithms to automatically analyze candidate resumes, match skills to job requirements, and form balanced teams for innovation challenges. The platform provides an end-to-end solution for modern technical recruitment.

## 🏗️ System Architecture

```text
Candidates & Recruiters (J&J Hiring Platform)
┌─────────────────────┬─────────────────────┐
│                     │                     │
▼                     ▼                     ▼
👤 Candidate Portal   👔 Recruiter Portal   📊 Admin Dashboard
├── Profile Creation  ├── Challenge Mgmt   ├── Analytics View
├── Resume Upload     ├── Team Overview    ├── User Management
├── Skill Assessment  ├── Candidate Review ├── System Monitoring
├── Team Participation├── Hiring Decisions ├── Performance Metrics
└── Progress Tracking └── Report Generation└── Configuration
         │                    │                     │
         └────────────────────┼─────────────────────┘
                              ▼
                   🖥️ Backend API (Flask)
                   ├── JWT Authentication & Authorization
                   ├── RESTful API Endpoints
                   ├── User & Team Management
                   ├── Challenge & Project Handling
                   ├── Resume Processing Pipeline
                   ├── Real-time Data Synchronization
                   └── Security & Validation Layer
                              │
                              ▼
          ┌─────────────────────────────────────────────┐
          │        🤖 AI/ML Processing Pipeline         │
          ├─────────────────────┬───────────────────────┤
          ▼                     ▼                       ▼
    📄 Resume Processor    🧠 Google Gemini AI    🎯 Team Builder
    ├── PDF Text Extract  ├── Skill Analysis     ├── K-Means Clustering
    ├── Content Parsing   ├── Experience Eval    ├── Balanced Grouping
    ├── Data Validation   ├── Education Scoring  ├── Diversity Optimization
    └── S3 Integration    └── Vector Generation  └── Team Assignment
                              │
                              ▼
                   💾 Data Layer & Storage
                   ├── SQLite Database (User Data)
                   ├── AWS S3 (Resume Storage)
                   ├── Team & Challenge Records
                   └── Analytics & Metrics Data
```

## ✨ Key Features

### 🤖 AI-Powered Resume Analysis

- **Smart Resume Processing**: Automatically extracts and analyzes resume content using Google's Gemini AI
- **Multi-dimensional Scoring**: Evaluates candidates on technical skills, experience, and education (1-10 scale)
- **Job Matching**: Compares candidate profiles against specific job listings and requirements

### 🎲 Intelligent Team Formation

- **K-Means Clustering**: Groups candidates based on complementary skills and experience levels
- **Balanced Team Generation**: Creates diverse teams of 6 members with varied skill distributions
- **Innovation Challenge Support**: Automatically forms teams for hackathons and coding challenges

### 👥 Comprehensive User Management

- **Dual User Types**: Support for both candidates and recruiters/hiring managers
- **Secure Authentication**: JWT-based authentication with password hashing
- **Profile Management**: Complete candidate profiles with LinkedIn, GitHub, and resume links

### 📊 Interactive Dashboard

- **Team Visualization**: Modern React-based interface for viewing team compositions
- **Candidate Deep-dive**: Expandable candidate cards with detailed information
- **Real-time Updates**: Live team formation and candidate status tracking

## 🏗️ Architecture

### Frontend (`/Client`)

- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with custom components
- **Routing**: React Router for navigation
- **Build Tool**: Vite for fast development and building
- **UI Components**: Custom component library with Radix UI primitives

### Backend (`/Server`)

- **Framework**: Flask with Python
- **Database**: SQLite with SQLAlchemy ORM
- **Authentication**: JWT tokens with Flask-JWT-Extended
- **Security**: bcrypt password hashing
- **API**: RESTful endpoints with CORS support

### ML Pipeline (`/Model`)

- **AI Engine**: Google Gemini 1.5 Flash for resume analysis
- **Clustering**: Scikit-learn K-Means for team formation
- **Data Processing**: PyPDF2 for resume text extraction
- **Cloud Integration**: AWS S3 for resume storage

## 🚦 Getting Started

### Prerequisites

- Python 3.8+
- Node.js 16+
- npm or yarn
- Google AI API key
- AWS credentials (for S3 resume storage)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Evandabest/HackHire.git
   cd HackHire
   ```

2. **Setup Backend**

   ```bash
   cd Server
   pip install -r requirements.txt
   
   # Create environment file
   echo "GOOGLE_API_KEY=your_google_api_key" > .env
   echo "SECRET_KEY=your_secret_key" >> .env
   echo "JWT_SECRET_KEY=your_jwt_secret" >> .env
   
   python main.py
   ```

3. **Setup Frontend**

   ```bash
   cd Client
   npm install
   npm run dev
   ```

4. **Setup ML Pipeline**

   ```bash
   cd Model
   pip install -r requirements.txt
   ```

### Environment Variables

```bash
# Required for ML Pipeline
GOOGLE_API_KEY=your_google_gemini_api_key

# Required for Backend
SECRET_KEY=your_flask_secret_key
JWT_SECRET_KEY=your_jwt_secret_key

# AWS Configuration (if using S3)
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
```

## 🔧 API Endpoints

### Authentication

- `POST /login` - User login
- `POST /register` - User registration
- `POST /logout` - User logout

### User Management

- `GET /getAllUsers` - Retrieve all candidates
- `GET /getAllUsers/:id` - Get specific candidate details
- `POST /createUser` - Create new candidate profile

### Team Management

- `GET /getAllTeams` - Retrieve all formed teams
- `POST /createTeam` - Create new team
- `GET /getTeam/:id` - Get specific team details

### Innovation Challenges

- `GET /getChallenges` - Get all active challenges
- `POST /createChallenge` - Create new innovation challenge

## 🎯 Use Cases

### For Recruiters

1. **Post Innovation Challenges**: Create coding challenges and hackathons
2. **View Candidate Pool**: Browse and evaluate all registered candidates
3. **Automatic Team Formation**: Let AI create balanced teams for challenges
4. **Track Progress**: Monitor team performance and candidate engagement

### For Candidates

1. **Profile Creation**: Upload resume and create comprehensive profile
2. **Skill Assessment**: Get AI-powered evaluation of technical abilities
3. **Team Participation**: Join automatically-formed teams for challenges
4. **Networking**: Connect with other candidates through team collaboration

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Frontend | React, TypeScript, Tailwind CSS, Vite |
| Backend | Flask, SQLAlchemy, JWT, bcrypt |
| Database | SQLite (development), PostgreSQL (production) |
| AI/ML | Google Gemini AI, Scikit-learn |
| Cloud | AWS S3, Boto3 |
| Authentication | JWT tokens, bcrypt hashing |

## 📊 Data Models

### Candidate

- Personal information (name, email, location)
- Academic details (graduation date, education)
- Professional links (LinkedIn, GitHub)
- Resume storage and processing

### Recruiter

- Company affiliation (Johnson & Johnson)
- Contact information
- Challenge creation permissions

### Team

- Project information and descriptions
- Member composition and roles
- Challenge association
- GitHub and Figma links

### Innovation Challenge

- Challenge details and requirements
- Timeline and deadlines
- Team size specifications
- Recruiter ownership

## 🔮 Future Enhancements

- **Real-time Collaboration**: Integrated code editor and project workspace
- **Video Interviews**: Automated scheduling and AI-powered interview analysis
- **Skill Verification**: Automated coding challenges and skill assessments
- **Analytics Dashboard**: Comprehensive hiring metrics and insights
- **Mobile App**: Native mobile application for candidates and recruiters
- **Integration Hub**: Connect with popular development tools and platforms

## 🤝 Contributing

We welcome contributions to HackHire! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

For questions, issues, or feature requests, please:

- Open an issue on GitHub
- Contact the development team
- Check the documentation and FAQ

---

Built with ❤️ for Johnson & Johnson's next generation of software engineers