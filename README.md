ModelHub – AI Model Selection Utility

A production-ready AI Model Selection Utility built for the Binaire JavaScript Developer Assessment. The application helps users discover, compare, filter, search, and select AI models using the official Binaire model catalog while supporting offline access, Firebase authentication, advanced filtering, and a modern Adobe Spectrum-based UI.

Overview

ModelHub allows users to:

Browse AI models from the official Binaire API
Search models by name and family
Filter models using multiple criteria
Sort models intelligently
View detailed model metadata
Save favorite models
Track recently viewed models
Download model metadata as JSON
Work offline using cached data
Authenticate securely using Firebase
Live Features
Authentication
Firebase Email/Password Authentication
User Registration
Login
Forgot Password
Protected Routes
Persistent Sessions
User Profile Management
Model Discovery
Real-time model catalog from Binaire API
Model Details Drawer
Model Selection Workflow
Favorites Management
Recent Models History
Search
Search by Model Name
Search by Model Family
Case-insensitive search
Substring matching
Debounced search input
Filters
Pipeline Tags
Family Tags
Architecture Tags
Weight Format Tags
Safetensor Minimum Count
Safetensor Maximum Count
Sorting
Model Name (A → Z)
Model Name (Z → A)
Safetensor Count (Low → High)
Safetensor Count (High → Low)
Offline Support
IndexedDB Caching
Cached Model Catalog
Offline Search
Offline Filtering
Offline Sorting
Offline Model Details
Additional Features
JSON Download
Search History
Online/Offline Detection
Toast Notifications
Responsive Design
Smooth UI Animations
Official API

The application consumes the official Binaire Model Catalog:

https://binaire.app/hf-models-api.json

The API provides model metadata including:

Model Name
Family
Architecture
Weight Format
Safetensor Counts
Hugging Face Tags
Repository Information
Use Cases
Download Commands
Tech Stack
Frontend
React
React Router
React Spectrum (Adobe Spectrum)
Context API
IndexedDB
Backend
Node.js
Express.js
Authentication
Firebase Authentication
Data Storage
IndexedDB
Local Storage
Development
Vite
ESLint
Project Structure
ModelHub/
│
├── client/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── contexts/
│   │   ├── hooks/
│   │   ├── utils/
│   │   └── routes/
│   │
│   ├── public/
│   └── package.json
│
├── server/
│   ├── routes/
│   ├── services/
│   ├── middleware/
│   └── package.json
│
├── README.md
├── .env.example
└── .gitignore
Environment Variables
Frontend

Create:

.env
VITE_MODEL_API_URL=https://binaire.app/hf-models-api.json
VITE_API_BASE_URL=http://localhost:5000/api

VITE_FIREBASE_API_KEY=
VITE_FIREBASE_AUTH_DOMAIN=
VITE_FIREBASE_PROJECT_ID=
VITE_FIREBASE_STORAGE_BUCKET=
VITE_FIREBASE_MESSAGING_SENDER_ID=
VITE_FIREBASE_APP_ID=
Backend

Create:

server/.env
MODEL_API_URL=https://binaire.app/hf-models-api.json
PORT=5000
CLIENT_ORIGIN=http://localhost:5173
Installation
Clone Repository
git clone <your-repository-url>
cd Binaire_Freznel_Assessment
Install Frontend Dependencies
cd client
npm install
Install Backend Dependencies
cd ../server
npm install
Run Application
Start Backend
cd server
npm run dev
Start Frontend
cd client
npm run dev

Application runs at:

Frontend: http://localhost:5173
Backend:  http://localhost:5000
Offline Architecture
Online Mode
Binaire API
      ↓
Node API Layer
      ↓
Model Repository
      ↓
IndexedDB Cache
      ↓
React UI
Offline Mode
IndexedDB Cache
      ↓
React UI
      ↓
Search / Filter / Sort

When internet is unavailable:

Cached model catalog loads automatically
Search remains functional
Filters remain functional
Sorting remains functional
Model details remain accessible
OOP Architecture

The assessment required implementation using Classes and OOP principles.

ModelApiClient

Responsibilities:

Fetch model catalog
Handle API errors
Validate responses
ModelRepository

Responsibilities:

Coordinate API and cache
Provide unified data access
ModelCache

Responsibilities:

IndexedDB persistence
Cache retrieval
Cache updates
ModelFilterEngine

Responsibilities:

Search logic
Filter logic
ModelSortEngine

Responsibilities:

Sorting algorithms
Ordering logic
Search Implementation
Model Name Search

Searches:

display_name
id
Family Search

Searches:

family
Search Features
Debounced
Case-insensitive
Partial matching
Fast filtering
Filtering Logic
Available Filters
Pipeline Tags
hf_tags.pipeline_tag
Family
family
Architecture
hf_tags.architecture
architecture_category
Weight Format
weight_format
Safetensor Range
safetensor_file_count
Logic

Within same category:

OR

Across categories:

AND
Sorting Logic
Model Name
A → Z
Z → A
Safetensor Count
Low → High
High → Low

Numeric sorting is used to avoid lexicographical ordering issues.

Download Safety

The assessment required handling large JSON downloads safely.

Process
Serialize model data
Validate JSON
Generate Blob
Create Object URL
Download File
Revoke Object URL
Benefits
Prevents malformed downloads
Avoids memory leaks
Supports large files
Preserves data integrity
Promise-Based API Handling

The assessment explicitly requested an approach without relying on async/await.

Primary API operations use Promise chaining:

fetch(url)
  .then(handleResponse)
  .then(normalizeData)
  .then(updateCache)
  .then(updateUI)
  .catch(handleError)
  .finally(stopLoading);

Benefits:

Explicit control flow
Easier error propagation
Matches assessment requirements
Security Measures
Environment Variables
Firebase Authentication
Protected Routes
Safe External Links
Input Validation
JSON Validation
API Response Validation
Secure Download Handling
CORS Protection
Assessment Requirement Mapping
Assessment Requirement	Implementation
Model Name Search	ModelFilterEngine
Family Search	ModelFilterEngine
Pipeline Filter	Dynamic API Filter
Family Filter	Dynamic API Filter
Architecture Filter	Dynamic API Filter
Weight Filter	Dynamic API Filter
Safetensor Range	Numeric Filter
Sorting	ModelSortEngine
Firebase Authentication	Firebase Auth
Offline Support	IndexedDB Cache
Network Detection	Online/Offline Monitor
OOP Design	Service Classes
API Integration	Binaire API
Adobe Spectrum	React Spectrum
Animations	CSS Transitions
JSON Download	Blob Export System
Future Improvements
Model Comparison Tool
Advanced Analytics Dashboard
Custom Saved Filters
Team Workspaces
Export to CSV
Dark/Light Theme Toggle
Advanced Model Recommendations
Author

[Your Full Name]

JavaScript Developer Assessment Submission

Repository: Binaire_Freznel_Assessment

Company: Binaire Private Limited

Screenshots

Add screenshots of:

Login Page
Dashboard
Model Catalog
Filters
Model Details
Offline Mode
Favorites Page

before final submission.
