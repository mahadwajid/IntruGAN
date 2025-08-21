# IntruGAN: GAN-Powered IoT Intrusion Detection System

## 🚀 Elevator Pitch

**IntruGAN is a GAN-powered deep learning system that strengthens IoT security by balancing network data and detecting cyber intrusions with higher accuracy.**

IntruGAN addresses the critical challenge of imbalanced network security datasets by leveraging Generative Adversarial Networks (GANs) to create synthetic attack samples, thereby improving the accuracy of intrusion detection systems. The platform provides a complete end-to-end solution from data upload to real-time threat detection with an intuitive web interface.

## 🎯 Key Features

- **🔐 Secure Authentication**: JWT-based user management with bcrypt password hashing
- **📊 Intelligent Data Analysis**: Automatic dataset profiling and imbalance detection
- **⚙️ Advanced Preprocessing**: Configurable data cleaning and feature engineering pipeline
- **🤖 GAN-Powered Balancing**: Synthetic data generation for minority attack classes
- **🛡️ Real-time Detection**: XGBoost-based intrusion detection with detailed metrics
- **📈 Interactive Visualizations**: Multi-chart data analysis and result presentation
- **📁 File Management**: Drag-and-drop CSV upload with progress tracking

## 🛠️ Technology Stack

### Backend Technologies

#### **Core Framework**
- **Node.js** (v18+) - JavaScript runtime environment
- **Express.js** (v4.21.2) - Web application framework
- **ES6 Modules** - Modern JavaScript module system

#### **Database & ORM**
- **MongoDB** (v6.12.0) - NoSQL document database
- **Mongoose** (v8.15.2) - MongoDB object modeling for Node.js
- **MongoDB Atlas** - Cloud database service (configurable)

#### **Authentication & Security**
- **JSON Web Tokens (JWT)** (v9.0.2) - Stateless authentication
- **bcryptjs** (v2.4.3) - Password hashing with salt rounds
- **CORS** (v2.8.5) - Cross-origin resource sharing

#### **File Handling & Processing**
- **Multer** (v1.4.5) - Multipart form data handling
- **python-shell** (v5.0.0) - Node.js ↔ Python integration
- **body-parser** (v1.20.3) - Request body parsing middleware

#### **Development Tools**
- **Nodemon** (v3.1.9) - Development server with auto-restart
- **dotenv** (v16.4.7) - Environment variable management

### Frontend Technologies

#### **Core Framework**
- **React** (v18.2.0) - JavaScript library for building user interfaces
- **React Router DOM** (v6.22.1) - Client-side routing
- **React Scripts** (v5.0.1) - Create React App build tools

#### **UI Framework & Components**
- **Material-UI (MUI)** (v7.1.1) - React component library
- **@emotion/react** (v11.14.0) - CSS-in-JS styling solution
- **@emotion/styled** (v11.14.0) - Styled components
- **React Icons** (v5.5.0) - Icon library

#### **Data Visualization**
- **Chart.js** (v4.5.0) - Flexible charting library
- **React Chart.js 2** (v5.3.0) - React wrapper for Chart.js
- **Recharts** (v2.15.3) - Composable charting library
- **Victory** (v36.6.8) - React charting library

#### **HTTP Client & State Management**
- **Axios** (v0.27.2) - Promise-based HTTP client
- **React Context API** - Built-in state management
- **Local Storage** - Client-side data persistence

#### **Development & Build Tools**
- **React App Rewired** (v2.2.1) - Customize Create React App config
- **Web Vitals** (v2.1.4) - Performance monitoring

### Machine Learning & AI Technologies

#### **Python Core Libraries**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Scikit-learn** - Machine learning algorithms
- **Joblib** - Parallel computing and model persistence

#### **Deep Learning Framework**
- **PyTorch** - Deep learning framework for GAN implementation
- **Neural Networks (torch.nn)** - Neural network layers and activation functions
- **Optimization** - Adam optimizer for GAN training

#### **Machine Learning Models**
- **XGBoost** - Gradient boosting for intrusion detection
- **Generative Adversarial Networks (GANs)** - Synthetic data generation
- **Feature Selection** - Chi-square and variance-based selection
- **Data Preprocessing** - StandardScaler, LabelEncoder, SimpleImputer

#### **Model Architecture Details**

**GAN Architecture:**
- **Generator**: 4-layer neural network (100→128→256→512→42)
- **Discriminator**: 3-layer network with LeakyReLU activation
- **Latent Dimension**: 100
- **Input Features**: 42 selected features

**XGBoost Model:**
- **Type**: Binary classifier for intrusion detection
- **Features**: 42 engineered features
- **Output**: Normal (0) vs Attack (1) classification

## 📁 Project Structure

```
idsfypnew-main/
├── backend/                          # Node.js server
│   ├── Controllers/                  # Business logic
│   │   ├── authController.js        # Authentication logic
│   │   ├── datasetController.js     # Dataset management
│   │   ├── preprocessing.js         # Data preprocessing
│   │   ├── GANBalancingController.js # GAN operations
│   │   └── Intrusiondetction.js     # Detection logic
│   ├── Models/                      # MongoDB schemas
│   │   ├── User.js                  # User model
│   │   ├── Dataset.js               # Dataset model
│   │   └── PreprocessDataset.js     # Preprocessed data model
│   ├── Routes/                      # API endpoints
│   │   ├── authRoutes.js            # Authentication routes
│   │   └── datasetRoutes.js         # Dataset routes
│   ├── uploads/                     # File storage
│   ├── binary_xgboost_model/        # Trained ML models
│   ├── GANModel/                    # GAN model files
│   ├── graphs/                      # Generated visualizations
│   ├── analyze_dataset.py           # Dataset analysis script
│   ├── prepro.py                    # Preprocessing pipeline
│   ├── GANBalancing.py              # GAN implementation
│   ├── detection_script.py          # Intrusion detection
│   └── requirements.txt             # Python dependencies
├── frontend/                        # React application
│   ├── src/
│   │   ├── Components/              # Reusable components
│   │   │   ├── Navbar.js            # Navigation bar
│   │   │   ├── Sidebar.js           # Side navigation
│   │   │   └── ProtectedRoute.js    # Route protection
│   │   ├── Contexts/                # React contexts
│   │   │   ├── AuthContext.js       # Authentication state
│   │   │   └── DatasetContext.js    # Dataset state
│   │   ├── Pages/                   # Application pages
│   │   │   ├── Home.js              # File upload
│   │   │   ├── DataVisualization.js # Data analysis
│   │   │   ├── Preprocessing.js     # Data preprocessing
│   │   │   ├── DataBalancing.js     # GAN balancing
│   │   │   ├── IntrusionDetection.js # Detection results
│   │   │   ├── Login.js             # User login
│   │   │   └── Signup.js            # User registration
│   │   ├── Services/                # API services
│   │   │   └── API.js               # HTTP client
│   │   └── CSS/                     # Stylesheets
│   └── public/                      # Static assets
```

## 🚀 Installation & Setup

### Prerequisites

- **Node.js** (v18 or higher)
- **Python** (v3.8 or higher)
- **MongoDB** (local installation or MongoDB Atlas account)
- **npm** or **yarn** package manager

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd idsfypnew-main/backend
   ```

2. **Install Node.js dependencies**
   ```bash
   npm install
   ```

3. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Configuration**
   Create a `.env` file in the backend directory:
   ```env
   PORT=5000
   MONGODB_URL=mongodb://localhost:27017/intrugan
   JWT_SECRET=your_jwt_secret_key_here
   ```

5. **Start the backend server**
   ```bash
   npm run dev
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd ../frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```

## 📖 Usage Guide

### 1. User Registration & Authentication
- Navigate to `/signup` to create a new account
- Use `/login` to access the system
- JWT tokens are automatically managed for session persistence

### 2. Dataset Upload & Analysis
- Upload CSV datasets via drag-and-drop interface
- Automatic dataset analysis provides:
  - Dataset size and attribute count
  - Class distribution analysis
  - Imbalance detection
  - Normal vs. attack sample identification

### 3. Data Preprocessing
- Configure preprocessing options:
  - Missing value handling (mean/mode imputation)
  - Feature scaling (StandardScaler)
  - Categorical encoding (LabelEncoder)
  - Feature selection (Chi-square/Variance)
- Generate preprocessed datasets with artifacts

### 4. GAN-Based Data Balancing
- Upload preprocessed datasets
- Configure GAN parameters for synthetic data generation
- Generate balanced datasets with improved class distribution
- Download balanced datasets for training

### 5. Intrusion Detection
- Upload datasets for real-time analysis
- XGBoost model provides:
  - Binary classification (Normal/Attack)
  - Confidence scores
  - Performance metrics (Accuracy, Precision, Recall, F1)
  - Detailed detection results

## 🔧 API Endpoints

### Authentication
- `POST /signup` - User registration
- `POST /login` - User authentication

### Dataset Management
- `POST /datasets/upload` - Upload CSV dataset
- `GET /datasets/retrive` - Retrieve all datasets with analysis
- `POST /datasets/preprocess` - Preprocess dataset
- `POST /datasets/balance-gan` - Balance dataset using GAN
- `POST /datasets/detect-intrusion` - Perform intrusion detection

## 🎨 Features in Detail

### **Data Analysis Pipeline**
- **Automatic Target Detection**: Identifies `attack_cat` or `label` columns
- **Class Distribution Analysis**: Normal vs. attack sample counting
- **Imbalance Assessment**: Determines if dataset needs balancing
- **Feature Engineering**: 42-feature selection for optimal performance

### **GAN Implementation**
- **Generator Network**: Creates synthetic attack samples
- **Discriminator Network**: Distinguishes real from synthetic data
- **Training Process**: Adversarial training for optimal generation
- **Quality Control**: Discriminator scoring for sample selection

### **Security Features**
- **Input Validation**: Server-side validation for all endpoints
- **File Type Restrictions**: CSV-only uploads for security
- **Authentication**: JWT-based session management
- **Error Handling**: Comprehensive error tracking and logging

### **User Experience**
- **Responsive Design**: Works on desktop and mobile devices
- **Real-time Feedback**: Progress indicators and status updates
- **Interactive Charts**: Multiple visualization options
- **Intuitive Navigation**: Sidebar-based navigation system

## 🔍 Performance Metrics

### **Detection Accuracy**
- **XGBoost Model**: High accuracy binary classification
- **Feature Selection**: 42 optimal features for detection
- **Real-time Processing**: Fast prediction capabilities

### **GAN Performance**
- **Synthetic Data Quality**: High-fidelity attack sample generation
- **Balancing Effectiveness**: Improved class distribution
- **Training Efficiency**: Optimized network architecture

## 🚀 Deployment

### **Production Deployment**
1. **Backend**: Deploy to cloud platforms (AWS, Azure, GCP)
2. **Frontend**: Build and deploy to CDN or hosting service
3. **Database**: Use MongoDB Atlas for cloud database
4. **Environment Variables**: Configure production environment

### **Docker Deployment** (Optional)
```dockerfile
# Backend Dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 5000
CMD ["npm", "start"]
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request


## 🙏 Acknowledgments

- **MongoDB** for database technology
- **React** and **Material-UI** for frontend framework
- **PyTorch** for deep learning capabilities
- **Scikit-learn** for machine learning algorithms


**IntruGAN** - Strengthening IoT Security with GAN-Powered Intrusion Detection
