# BioCraft - Biodata Generator Application

## Table of Contents
1. [Project Overview](#project-overview)
2. [System Architecture](#system-architecture)
3. [Technology Stack](#technology-stack)
4. [Project Structure](#project-structure)
5. [Core Features](#core-features)
6. [Installation & Setup](#installation--setup)
7. [Development Guide](#development-guide)
8. [API Integration](#api-integration)
9. [Context Management](#context-management)
10. [Routing System](#routing-system)
11. [Component Architecture](#component-architecture)
12. [Styling & UI Framework](#styling--ui-framework)
13. [State Management](#state-management)
14. [Authentication System](#authentication-system)
15. [Data Flow](#data-flow)
16. [Testing Guidelines](#testing-guidelines)
17. [Deployment](#deployment)
18. [Troubleshooting](#troubleshooting)
19. [Contributing](#contributing)
20. [License](#license)

---

## Project Overview

**BioCraft** is a comprehensive biodata generator web application that enables users to create professional biodata documents using various templates. The application provides extensive customization options, allowing users to generate diverse biodata formats from a single data entry.

### Key Objectives
- Simplify biodata creation process
- Provide multiple professional templates
- Enable easy data management and updates
- Offer responsive design for all devices
- Integrate advanced features like chatbot assistance

### Project Phases
1. **Phase 1**: Template Integration
2. **Phase 2**: User Interface Integration
3. **Phase 3**: Data Storage Integration

---

## System Architecture

```
Frontend (React.js)
    ├── User Interface Layer
    ├── State Management (Context API)
    ├── Routing System (React Router)
    ├── Component Library
    └── API Integration Layer
            ↓
Backend (Laravel PHP)
    ├── Authentication System
    ├── RESTful API
    ├── Data Processing
    └── Business Logic
            ↓
Database (MySQL)
    ├── User Data
    ├── Biodata Information
    ├── Templates
    └── System Configurations
```

---

## Technology Stack

### Frontend
- **Framework**: React.js 18.2.0
- **Build Tool**: Vite 5.2.0
- **Styling**: 
  - Tailwind CSS 3.4.3
  - Vanilla CSS
  - Tailwind CSS Motion & Animate
- **Routing**: React Router DOM 6.23.1
- **State Management**: React Context API
- **Form Handling**: Formik 2.4.6
- **HTTP Client**: Axios 1.7.7
- **Data Fetching**: TanStack React Query 5.37.1

### UI/UX Libraries
- **Icons**: React Icons 5.2.1
- **Charts**: Chart.js 4.4.8 + React Chart.js 2
- **Carousel**: React Slick 0.30.2
- **Chatbot**: React Chatbot Kit 2.2.2
- **Printing**: React to Print 3.0.2
- **Notifications**: React Toastify 10.0.6

### Development Tools
- **TypeScript Support**: @types/react, @types/react-dom
- **Linting**: ESLint 8.57.0
- **CSS Processing**: PostCSS 8.4.38, Autoprefixer 10.4.19

### Backend (External)
- **Framework**: Laravel (PHP)
- **Database**: MySQL
- **API**: RESTful services

---

## Project Structure

```
code/
├── public/                     # Static assets
│   ├── vite.svg
│   └── images/                 # Application images
│       ├── boticon.jpg
│       ├── chat_bg.jpg
│       ├── logo.png
│       └── ...
├── src/
│   ├── admin/                  # Admin panel components
│   │   ├── LandingAdmin.jsx
│   │   ├── components/
│   │   └── pages/
│   ├── assets/                 # React assets
│   ├── chatbot/               # Chatbot functionality
│   │   ├── ActionProvider.jsx
│   │   ├── Chat.jsx
│   │   ├── config.jsx
│   │   └── components/
│   ├── components/            # Reusable components
│   │   ├── forms/
│   │   ├── outputTemplate/
│   │   ├── post/
│   │   ├── Structure/
│   │   └── ...
│   ├── contexts/              # React Context providers
│   │   ├── StateContext.jsx
│   │   ├── ThemeContext.jsx
│   │   ├── DataContext.jsx
│   │   └── ...
│   ├── layouts/               # Layout components
│   │   ├── AuthLayout.jsx
│   │   └── GuestLayout.jsx
│   ├── pages/                 # Page components
│   │   ├── Home.jsx
│   │   ├── Profile.jsx
│   │   ├── FormBiodata.jsx
│   │   └── ...
│   ├── router/                # Routing configuration
│   │   ├── AuthRouter.jsx
│   │   ├── GuestRouter.jsx
│   │   └── Playground.jsx
│   ├── services/              # API services
│   │   ├── auth-api.js
│   │   └── user-api.js
│   ├── App.jsx               # Main app component
│   ├── main.jsx              # Application entry point
│   └── index.css             # Global styles
├── package.json              # Dependencies and scripts
├── vite.config.js           # Vite configuration
├── tailwind.config.js       # Tailwind CSS configuration
└── postcss.config.js        # PostCSS configuration
```

---

## Core Features

### 1. User Authentication
- **Registration**: New user account creation
- **Login/Logout**: Secure authentication system
- **Token Management**: JWT-based authentication
- **Protected Routes**: Role-based access control

### 2. Biodata Creation
- **Multi-step Form**: Progressive data collection
- **Personal Details**: Basic information input
- **Educational Background**: Academic qualifications
- **Professional Experience**: Work history
- **Skills Management**: Technical and soft skills
- **Social Networks**: Social media profiles

### 3. Template System
- **Multiple Templates**: 4+ professional designs
- **Live Preview**: Real-time template preview
- **Customization**: Template-specific modifications
- **Print/Export**: PDF generation capabilities

### 4. Data Management
- **CRUD Operations**: Complete data lifecycle management
- **Image Upload**: Profile picture management
- **Data Validation**: Form validation and error handling
- **Data Persistence**: Backend integration

### 5. User Interface
- **Responsive Design**: Mobile-first approach
- **Dark/Light Mode**: Theme switching
- **Interactive Elements**: Smooth animations
- **Accessibility**: WCAG compliance considerations

### 6. Additional Features
- **Chatbot Integration**: User assistance
- **Job Search**: External job API integration
- **Admin Panel**: Administrative functionality
- **Review System**: User feedback mechanism

---

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager
- Git version control

### Environment Setup

1. **Clone the Repository**
```bash
git clone [repository-url]
cd biodatamakerv2
```

2. **Install Dependencies**
```bash
npm install
```

3. **Environment Configuration**
Create `.env` file in the root directory:
```env
VITE_APP_BASE_URL=http://your-backend-url
VITE_API_KEY=your-api-key
```

4. **Start Development Server**
```bash
npm run dev
```

5. **Build for Production**
```bash
npm run build
```

6. **Preview Production Build**
```bash
npm run preview
```

---

## Development Guide

### Code Style Guidelines

#### React Components
```jsx
// Use functional components with hooks
import React, { useState, useEffect } from 'react';

const ComponentName = ({ prop1, prop2 }) => {
  const [state, setState] = useState(initialValue);
  
  useEffect(() => {
    // Side effects
  }, [dependencies]);
  
  return (
    <div className="component-wrapper">
      {/* Component JSX */}
    </div>
  );
};

export default ComponentName;
```

#### File Naming Conventions
- **Components**: PascalCase (e.g., `UserProfile.jsx`)
- **Utilities**: camelCase (e.g., `apiHelpers.js`)
- **Constants**: UPPER_SNAKE_CASE (e.g., `API_ENDPOINTS.js`)

#### Import Order
1. External libraries
2. Internal components
3. Context providers
4. Utilities and helpers
5. Styles

### Component Development

#### Creating New Components
1. Create component file in appropriate directory
2. Implement component logic
3. Add PropTypes or TypeScript interfaces
4. Write unit tests
5. Update documentation

#### Context Usage
```jsx
// Using existing contexts
import { useStateContext } from '../contexts/StateContext';
import { useThemeContext } from '../contexts/ThemeContext';

const MyComponent = () => {
  const { user, token } = useStateContext();
  const { isDark, setDark } = useThemeContext();
  
  // Component logic
};
```

---

## API Integration

### Axios Configuration
```javascript
// axios-client.jsx
import axios from "axios";

const axiosClient = axios.create({
    baseURL: `${import.meta.env.VITE_APP_BASE_URL}/api`
});

// Request interceptor for authentication
axiosClient.interceptors.request.use((config) => {
    const token = localStorage.getItem('ACCESS_TOKEN');
    config.headers.Authorization = `Bearer ${token}`;
    return config;
});

// Response interceptor for error handling
axiosClient.interceptors.response.use(
    (response) => response,
    (error) => {
        if (error.response?.status === 401) {
            localStorage.removeItem('ACCESS_TOKEN');
            // Redirect to login
        }
        throw error;
    }
);
```

### API Service Structure
```javascript
// services/auth-api.js
export function authLogin(payload) {
    return axiosClient.post("/login", payload)
        .then(({ data }) => data)
        .catch((error) => { throw error; });
}

export function authLogout() {
    return axiosClient.post("/logout")
        .then(() => {})
        .catch((error) => { throw error; });
}
```

### React Query Integration
```jsx
import { useQuery, useMutation } from '@tanstack/react-query';

// Data fetching
const { data, isLoading, error } = useQuery({
    queryKey: ['user'],
    queryFn: fetchUser
});

// Data mutations
const mutation = useMutation({
    mutationFn: updateUser,
    onSuccess: (data) => {
        // Handle success
    },
    onError: (error) => {
        // Handle error
    }
});
```

---

## Context Management

### State Context
```jsx
// contexts/StateContext.jsx
const StateContext = createContext({
    user: null,
    token: null,
    setUser: () => {},
    setToken: () => {},
});

export const StateProvider = ({ children }) => {
    const [user, setUser] = useState({});
    const [token, _setToken] = useState(localStorage.getItem("ACCESS_TOKEN"));
    
    const setToken = (token) => {
        _setToken(token);
        if (token) {
            localStorage.setItem("ACCESS_TOKEN", token);
        } else {
            localStorage.removeItem("ACCESS_TOKEN");
        }
    };
    
    return (
        <StateContext.Provider value={{ user, token, setUser, setToken }}>
            {children}
        </StateContext.Provider>
    );
};
```

### Theme Context
```jsx
// contexts/ThemeContext.jsx
export const ThemeProvider = ({ children }) => {
    const [isDark, setDark] = useState(() => {
        const savedTheme = localStorage.getItem('darkMode');
        return savedTheme ? JSON.parse(savedTheme) : false;
    });
    
    useEffect(() => {
        localStorage.setItem('darkMode', JSON.stringify(isDark));
    }, [isDark]);
    
    return (
        <ThemeContext.Provider value={{ isDark, setDark }}>
            {children}
        </ThemeContext.Provider>
    );
};
```

### Available Contexts
1. **StateContext**: Global state management
2. **ThemeContext**: Dark/light mode theming
3. **DataContext**: Form data management
4. **ProgressContext**: Multi-step form progress
5. **MobileContext**: Mobile responsiveness
6. **PanelContext**: Sidebar/panel state
7. **MessageContext**: Notification system

---

## Routing System

### Router Structure
```jsx
// router/Playground.jsx
const PlayGround = () => {
    const { token } = useStateContext();
    const [isGuest, setIsGuest] = useState(true);
    
    useEffect(() => {
        setIsGuest(!token);
    }, [token]);
    
    return (
        <>
            {isGuest ? (
                <GuestLayout>
                    <GuestRouter />
                </GuestLayout>
            ) : (
                <AuthLayout>
                    <AuthRouter />
                </AuthLayout>
            )}
        </>
    );
};
```

### Route Definitions

#### Guest Routes
- `/` - Landing page
- `/signin` - User login
- `/signup` - User registration
- `/about-us` - About page
- `/contact-us` - Contact page
- `/guest-templates` - Template preview

#### Authenticated Routes
- `/` - Dashboard/Landing
- `/templates` - Template selection
- `/formbiodata` - Biodata form
- `/profile` - User profile
- `/make-biodata` - Biodata creation
- `/template-[1-4]` - Template views
- `/admin` - Admin panel

---

## Component Architecture

### Layout Components

#### AuthLayout
```jsx
const AuthLayout = ({ children }) => {
    const { user, token, setUser, setToken } = useStateContext();
    const { isDark } = useThemeContext();
    
    return (
        <div className={`${isDark ? 'dark' : ''}`}>
            <div className="flex w-full">
                <div className="flex flex-col w-full">
                    <Navbar userName={user?.name} onLogout={handleLogout} />
                    <main>{children}</main>
                </div>
            </div>
        </div>
    );
};
```

#### GuestLayout
```jsx
const GuestLayout = ({ children }) => {
    const { isDark } = useThemeContext();
    
    return (
        <div className={`${isDark ? 'dark' : ''}`}>
            <div className="flex w-full h-screen">
                <div className="flex flex-col h-screen w-full">
                    <Navbar />
                    <div className="h-[calc(100vh-80px)] w-full flex justify-center items-center">
                        {children}
                    </div>
                </div>
            </div>
        </div>
    );
};
```

### Form Components

#### Multi-step Form Flow
```jsx
const FormBiodata = () => {
    const { isNext, setNext, nextButton } = useProgressContext();
    
    const renderStep = () => {
        switch(isNext) {
            case 0: return <PersonalDetails />;
            case 1: return <EducationDetails />;
            case 2: return <Specialization />;
            case 3: return <Experience />;
            case 4: return <Skills />;
            case 5: return <SocialNetwork />;
            default: return <Navigate to="/profile" />;
        }
    };
    
    return <div>{renderStep()}</div>;
};
```

### Reusable Components

#### FormikInputBox
```jsx
const FormikInputBox = ({ 
    label, 
    name, 
    type = "text", 
    placeholder,
    required = false 
}) => {
    return (
        <Field name={name}>
            {({ field, meta }) => (
                <div className="form-group">
                    <label>{label} {required && '*'}</label>
                    <input
                        {...field}
                        type={type}
                        placeholder={placeholder}
                        className={`form-input ${meta.error && meta.touched ? 'error' : ''}`}
                    />
                    {meta.error && meta.touched && (
                        <span className="error-message">{meta.error}</span>
                    )}
                </div>
            )}
        </Field>
    );
};
```

---

## Styling & UI Framework

### Tailwind CSS Configuration
```javascript
// tailwind.config.js
export default {
    darkMode: 'class',
    content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
    theme: {
        extend: {
            boxShadow: {
                '3xl': '0 35px 60px -15px rgba(0, 0, 0, 0.3)',
            },
            keyframes: {
                slideRight: {
                    '0%': { transform: 'translateX(-20%)' },
                    '100%': { transform: 'translateX(0%)' }
                },
            },
            animation: {
                slideRight: 'slideRight ease-in-out 0.5s'
            },
        },
    },
    plugins: [
        require('tailwindcss-motion'),
        require('tailwindcss-animate')
    ],
};
```

### Design System

#### Color Palette
- **Primary**: Blue tones for main actions
- **Secondary**: Gray scales for supporting elements
- **Success**: Green for positive actions
- **Warning**: Yellow for alerts
- **Error**: Red for errors

#### Typography
- **Headings**: Font weight 600-700
- **Body**: Font weight 400-500
- **Captions**: Font weight 300-400

#### Spacing
- **Margins**: 4px increments (1, 2, 3, 4, 6, 8, 12, 16, 24, 32)
- **Padding**: Consistent with margin scale
- **Border Radius**: 4px, 8px, 12px, 16px, full

#### Responsive Breakpoints
- **sm**: 640px
- **md**: 768px
- **lg**: 1024px
- **xl**: 1280px
- **2xl**: 1536px

---

## State Management

### Context-based State Management

#### Global State Structure
```javascript
{
    // Authentication
    user: { id, name, email, ... },
    token: "jwt-token-string",
    
    // UI State
    isDark: boolean,
    isMobile: boolean,
    isSidebarOpen: boolean,
    
    // Form State
    currentStep: number,
    formData: { ... },
    isLoading: boolean,
    
    // Messages
    message: "notification-text",
    messageType: "success|error|warning"
}
```

#### State Updates
```jsx
// Context usage pattern
const { state, setState } = useContext(SomeContext);

// State update with side effects
const updateState = (newValue) => {
    setState(newValue);
    // Persist to localStorage if needed
    localStorage.setItem('key', JSON.stringify(newValue));
};
```

### Form State Management
```jsx
// Using Formik for complex forms
const FormComponent = () => {
    const initialValues = {
        name: '',
        email: '',
        // ... other fields
    };
    
    const validationSchema = Yup.object({
        name: Yup.string().required('Name is required'),
        email: Yup.string().email('Invalid email').required('Email is required'),
    });
    
    const handleSubmit = (values, { setSubmitting }) => {
        // Handle form submission
        submitData(values)
            .then(() => {
                // Success handling
            })
            .catch(() => {
                // Error handling
            })
            .finally(() => {
                setSubmitting(false);
            });
    };
    
    return (
        <Formik
            initialValues={initialValues}
            validationSchema={validationSchema}
            onSubmit={handleSubmit}
        >
            <Form>
                {/* Form fields */}
            </Form>
        </Formik>
    );
};
```

---

## Authentication System

### Token Management
```javascript
// Token storage and retrieval
const setToken = (token) => {
    if (token) {
        localStorage.setItem("ACCESS_TOKEN", token);
    } else {
        localStorage.removeItem("ACCESS_TOKEN");
    }
};

const getToken = () => {
    return localStorage.getItem("ACCESS_TOKEN");
};
```

### Authentication Flow
1. **Login**: User submits credentials
2. **Token Receipt**: Backend returns JWT token
3. **Token Storage**: Token stored in localStorage
4. **Request Headers**: Token attached to API requests
5. **Route Protection**: Routes check for valid token
6. **Token Expiry**: Automatic logout on token expiration

### Protected Route Implementation
```jsx
const ProtectedRoute = ({ children }) => {
    const { token } = useStateContext();
    
    if (!token) {
        return <Navigate to="/signin" replace />;
    }
    
    return children;
};
```

### Authentication API
```javascript
// Login function
export function authLogin(credentials) {
    return axiosClient.post("/login", credentials)
        .then(({ data }) => {
            localStorage.setItem("ACCESS_TOKEN", data.token);
            return data;
        })
        .catch((error) => {
            throw error;
        });
}

// Logout function
export function authLogout() {
    return axiosClient.post("/logout")
        .then(() => {
            localStorage.removeItem("ACCESS_TOKEN");
        })
        .catch((error) => {
            console.error("Logout error:", error);
        });
}
```

---

## Data Flow

### Application Data Flow Diagram
```
User Interaction
       ↓
Component Event Handler
       ↓
Context State Update / API Call
       ↓
Backend Processing (if applicable)
       ↓
State Update / UI Re-render
       ↓
User Feedback
```

### Form Data Flow
```
1. User fills form fields
2. Formik manages field state
3. Form validation on blur/change
4. Submit triggers API call
5. Loading state displayed
6. Success/error feedback shown
7. Navigation or state update
```

### Authentication Data Flow
```
1. User submits login credentials
2. API call to authentication endpoint
3. Backend validates credentials
4. JWT token returned on success
5. Token stored in localStorage
6. User context updated
7. Redirect to authenticated area
8. Subsequent API calls include token
```

---

## Testing Guidelines

### Testing Strategy
1. **Unit Tests**: Individual component testing
2. **Integration Tests**: Component interaction testing
3. **E2E Tests**: Full user workflow testing
4. **API Tests**: Backend integration testing

### Testing Tools Recommendations
- **Jest**: Unit testing framework
- **React Testing Library**: Component testing
- **Cypress**: End-to-end testing
- **MSW**: API mocking

### Test File Structure
```
src/
├── components/
│   ├── Button/
│   │   ├── Button.jsx
│   │   ├── Button.test.jsx
│   │   └── Button.stories.jsx
│   └── ...
├── __tests__/
│   ├── integration/
│   ├── utils/
│   └── setupTests.js
```

### Example Test
```jsx
// Button.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import Button from './Button';

describe('Button Component', () => {
    test('renders button with text', () => {
        render(<Button>Click me</Button>);
        expect(screen.getByText('Click me')).toBeInTheDocument();
    });
    
    test('calls onClick handler when clicked', () => {
        const handleClick = jest.fn();
        render(<Button onClick={handleClick}>Click me</Button>);
        
        fireEvent.click(screen.getByText('Click me'));
        expect(handleClick).toHaveBeenCalledTimes(1);
    });
});
```

---

## Deployment

### Build Process
```bash
# Install dependencies
npm install

# Run tests
npm test

# Build for production
npm run build

# Preview build
npm run preview
```

### Environment Variables
```bash
# Production environment
VITE_APP_BASE_URL=https://production-api.domain.com
VITE_APP_ENV=production

# Staging environment
VITE_APP_BASE_URL=https://staging-api.domain.com
VITE_APP_ENV=staging
```

### Deployment Platforms

#### Vercel Deployment
1. Connect GitHub repository
2. Configure build settings
3. Set environment variables
4. Deploy automatically on push

#### Netlify Deployment
1. Connect repository
2. Build command: `npm run build`
3. Publish directory: `dist`
4. Set environment variables

#### Traditional Hosting
1. Build the application
2. Upload `dist` folder contents
3. Configure web server
4. Set up SSL certificate

### Performance Optimization
- **Code Splitting**: Route-based splitting
- **Lazy Loading**: Component lazy loading
- **Bundle Analysis**: Webpack bundle analyzer
- **Image Optimization**: WebP format, lazy loading
- **Caching**: Browser caching strategies

---

## Troubleshooting

### Common Issues

#### 1. Build Failures
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install

# Clear Vite cache
rm -rf node_modules/.vite
npm run dev
```

#### 2. API Connection Issues
- Check environment variables
- Verify backend URL
- Check CORS configuration
- Validate API endpoints

#### 3. Authentication Problems
- Check token expiration
- Verify token format
- Check localStorage permissions
- Validate API headers

#### 4. Styling Issues
- Check Tailwind CSS configuration
- Verify PostCSS setup
- Check for CSS conflicts
- Validate responsive breakpoints

### Debug Mode
```javascript
// Enable debug mode
if (import.meta.env.DEV) {
    console.log('Debug information:', data);
}
```

### Error Boundary Implementation
```jsx
class ErrorBoundary extends React.Component {
    constructor(props) {
        super(props);
        this.state = { hasError: false };
    }
    
    static getDerivedStateFromError(error) {
        return { hasError: true };
    }
    
    componentDidCatch(error, errorInfo) {
        console.error('Error caught by boundary:', error, errorInfo);
    }
    
    render() {
        if (this.state.hasError) {
            return <h1>Something went wrong.</h1>;
        }
        
        return this.props.children;
    }
}
```

---

## Contributing

### Development Workflow
1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

### Code Review Process
1. All code must be reviewed before merging
2. Ensure tests pass
3. Check for code style compliance
4. Verify documentation updates

### Commit Message Convention
```
type(scope): description

feat(auth): add user registration functionality
fix(ui): resolve mobile responsive issues
docs(readme): update installation instructions
style(css): improve button hover effects
refactor(api): simplify authentication logic
test(unit): add tests for user service
```

### Pull Request Template
```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Unit tests pass
- [ ] Manual testing completed
- [ ] Cross-browser testing done

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
```

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact & Support

### Development Team
- **Project Lead**: [Name]
- **Frontend Developer**: [Name]
- **Backend Developer**: [Name]

### Repository Links
- **Frontend**: Current repository
- **Backend**: https://github.com/shramana263/BioCraftApi

### Documentation
- **API Documentation**: [Link to API docs]
- **Design System**: [Link to design docs]
- **User Manual**: [Link to user manual]

---

## Appendices

### Appendix A: API Endpoints
```
Authentication:
POST /api/login
POST /api/logout
POST /api/registration

User Management:
GET /api/user
GET /api/users
PUT /api/user/update

Biodata:
POST /api/biodata
GET /api/biodata
PUT /api/biodata/update
DELETE /api/biodata/delete
```

### Appendix B: Database Schema
```sql
-- Users table
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Biodata table
CREATE TABLE biodata (
    id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT FOREIGN KEY REFERENCES users(id),
    personal_details JSON,
    education JSON,
    experience JSON,
    skills JSON,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Appendix C: Performance Metrics
- **Bundle Size**: Target < 500KB gzipped
- **First Contentful Paint**: Target < 2s
- **Time to Interactive**: Target < 3s
- **Lighthouse Score**: Target > 90

---

*Last Updated: July 1, 2025*
*Version: 1.0.0*
