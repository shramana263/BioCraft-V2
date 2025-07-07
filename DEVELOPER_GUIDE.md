# Developer Setup Guide - BioCraft

## Prerequisites

### Required Software
- **Node.js** (v16.0.0 or higher)
- **npm** (v8.0.0 or higher) or **yarn** (v1.22.0 or higher)
- **Git** (latest version)
- **VS Code** (recommended IDE)

### Recommended VS Code Extensions
- ES7+ React/Redux/React-Native snippets
- Tailwind CSS IntelliSense
- Auto Rename Tag
- Bracket Pair Colorizer
- GitLens
- Prettier - Code formatter
- ESLint

## Project Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/biodatamaker.git
cd biodatamaker/code
```

### 2. Install Dependencies
```bash
# Using npm
npm install

# Using yarn
yarn install
```

### 3. Environment Configuration
Create a `.env` file in the root directory:
```env
# API Configuration
VITE_APP_BASE_URL=http://localhost:8000
VITE_APP_ENV=development

# Optional: Additional API keys
VITE_EMAILJS_SERVICE_ID=your_service_id
VITE_EMAILJS_TEMPLATE_ID=your_template_id
VITE_EMAILJS_PUBLIC_KEY=your_public_key
```

### 4. Start Development Server
```bash
npm run dev
```
The application will be available at `http://localhost:5173`

## Backend Setup

### Prerequisites
- PHP 8.1 or higher
- Composer
- MySQL 8.0 or higher
- Laravel 10.x

### Backend Repository
The backend is maintained in a separate repository:
```bash
git clone https://github.com/shramana263/BioCraftApi.git
```

Follow the backend repository's README for setup instructions.

## Development Workflow

### Branch Strategy
```
main
├── develop
├── feature/feature-name
├── hotfix/issue-description
└── release/version-number
```

### Workflow Steps
1. Create feature branch from `develop`
2. Implement feature with tests
3. Create pull request to `develop`
4. Code review and approval
5. Merge to `develop`
6. Deploy to staging for testing
7. Merge to `main` for production

### Commit Message Convention
```
type(scope): description

Types:
- feat: New feature
- fix: Bug fix
- docs: Documentation changes
- style: Code style changes
- refactor: Code refactoring
- test: Adding tests
- chore: Maintenance tasks

Examples:
feat(auth): add user registration functionality
fix(ui): resolve mobile responsive issues
docs(readme): update installation instructions
```

## Code Style Guidelines

### JavaScript/React Conventions
```javascript
// Use functional components with hooks
const ComponentName = ({ prop1, prop2 }) => {
  const [state, setState] = useState(initialValue);
  
  // Custom hooks for reusable logic
  const { data, loading } = useCustomHook();
  
  // Event handlers
  const handleClick = useCallback(() => {
    // Handle click
  }, [dependencies]);
  
  return (
    <div className="component-wrapper">
      {/* JSX content */}
    </div>
  );
};

export default ComponentName;
```

### File Naming Conventions
- Components: `PascalCase.jsx` (e.g., `UserProfile.jsx`)
- Hooks: `camelCase.js` (e.g., `useAuth.js`)
- Utilities: `camelCase.js` (e.g., `apiUtils.js`)
- Constants: `UPPER_SNAKE_CASE.js` (e.g., `API_ENDPOINTS.js`)

### CSS/Tailwind Guidelines
```jsx
// Prefer Tailwind utility classes
const Button = ({ variant, children }) => {
  const baseClasses = "px-4 py-2 rounded font-medium transition-colors";
  const variantClasses = {
    primary: "bg-blue-600 text-white hover:bg-blue-700",
    secondary: "bg-gray-200 text-gray-800 hover:bg-gray-300"
  };
  
  return (
    <button className={`${baseClasses} ${variantClasses[variant]}`}>
      {children}
    </button>
  );
};
```

## Testing Setup

### Unit Testing with Jest & React Testing Library
```bash
npm install --save-dev @testing-library/react @testing-library/jest-dom jest-environment-jsdom
```

### Test Configuration
Create `vitest.config.js`:
```javascript
import { defineConfig } from 'vitest/config';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
  test: {
    environment: 'jsdom',
    setupFiles: ['./src/setupTests.js'],
  },
});
```

### Writing Tests
```javascript
// UserProfile.test.jsx
import { render, screen, fireEvent } from '@testing-library/react';
import { vi } from 'vitest';
import UserProfile from './UserProfile';

describe('UserProfile Component', () => {
  test('renders user information', () => {
    const mockUser = { name: 'John Doe', email: 'john@example.com' };
    render(<UserProfile user={mockUser} />);
    
    expect(screen.getByText('John Doe')).toBeInTheDocument();
    expect(screen.getByText('john@example.com')).toBeInTheDocument();
  });
  
  test('calls onEdit when edit button is clicked', () => {
    const mockUser = { name: 'John Doe', email: 'john@example.com' };
    const mockOnEdit = vi.fn();
    
    render(<UserProfile user={mockUser} onEdit={mockOnEdit} />);
    
    fireEvent.click(screen.getByText('Edit'));
    expect(mockOnEdit).toHaveBeenCalledTimes(1);
  });
});
```

## Debugging Setup

### VS Code Debug Configuration
Create `.vscode/launch.json`:
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Launch Chrome",
      "type": "chrome",
      "request": "launch",
      "url": "http://localhost:5173",
      "webRoot": "${workspaceFolder}/src"
    }
  ]
}
```

### React Developer Tools
Install browser extensions:
- React Developer Tools
- Redux DevTools (if using Redux)

### Console Debugging
```javascript
// Development-only logging
if (import.meta.env.DEV) {
  console.log('Debug info:', data);
}

// Error boundary for catching errors
const ErrorBoundary = ({ children }) => {
  const [hasError, setHasError] = useState(false);
  
  useEffect(() => {
    const handleError = (error) => {
      console.error('Caught error:', error);
      setHasError(true);
    };
    
    window.addEventListener('error', handleError);
    return () => window.removeEventListener('error', handleError);
  }, []);
  
  if (hasError) {
    return <div>Something went wrong!</div>;
  }
  
  return children;
};
```

## Performance Optimization

### Code Splitting
```javascript
// Lazy load components
const LazyComponent = lazy(() => import('./LazyComponent'));

// Route-based code splitting
const AuthRouter = lazy(() => import('./router/AuthRouter'));
const GuestRouter = lazy(() => import('./router/GuestRouter'));
```

### Bundle Analysis
```bash
# Install bundle analyzer
npm install --save-dev rollup-plugin-visualizer

# Add to vite.config.js
import { visualizer } from 'rollup-plugin-visualizer';

export default defineConfig({
  plugins: [
    react(),
    visualizer({
      filename: 'dist/stats.html',
      open: true,
    }),
  ],
});
```

### Image Optimization
```javascript
// Use WebP format when possible
const ImageComponent = ({ src, alt }) => {
  return (
    <picture>
      <source srcSet={`${src}.webp`} type="image/webp" />
      <img src={`${src}.jpg`} alt={alt} loading="lazy" />
    </picture>
  );
};
```

## Deployment Setup

### Environment-Specific Builds
```bash
# Development build
npm run dev

# Production build
npm run build

# Preview production build
npm run preview
```

### Environment Variables
```bash
# .env.development
VITE_APP_BASE_URL=http://localhost:8000
VITE_APP_ENV=development

# .env.production
VITE_APP_BASE_URL=https://api.biocraft.com
VITE_APP_ENV=production
```

### Docker Setup (Optional)
Create `Dockerfile`:
```dockerfile
FROM node:18-alpine as build

WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

## Troubleshooting

### Common Development Issues

#### Port Already in Use
```bash
# Find process using port 5173
lsof -ti:5173

# Kill the process
kill -9 <PID>

# Or use a different port
npm run dev -- --port 3000
```

#### Module Not Found Errors
```bash
# Clear node_modules and reinstall
rm -rf node_modules package-lock.json
npm install

# Clear npm cache
npm cache clean --force
```

#### Hot Reload Not Working
```bash
# Clear Vite cache
rm -rf node_modules/.vite

# Restart dev server
npm run dev
```

#### Build Failures
```bash
# Check for TypeScript errors
npm run type-check

# Check for linting errors
npm run lint

# Fix linting errors automatically
npm run lint:fix
```

### IDE Configuration Issues

#### VS Code Settings
Create `.vscode/settings.json`:
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.preferences.importModuleSpecifier": "relative"
}
```

#### Prettier Configuration
Create `.prettierrc`:
```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2
}
```

## API Development

### Axios Interceptors
```javascript
// Request interceptor
axiosClient.interceptors.request.use(
  (config) => {
    const token = localStorage.getItem('ACCESS_TOKEN');
    if (token) {
      config.headers.Authorization = `Bearer ${token}`;
    }
    return config;
  },
  (error) => {
    return Promise.reject(error);
  }
);

// Response interceptor
axiosClient.interceptors.response.use(
  (response) => response,
  (error) => {
    if (error.response?.status === 401) {
      localStorage.removeItem('ACCESS_TOKEN');
      window.location.href = '/signin';
    }
    return Promise.reject(error);
  }
);
```

### API Service Pattern
```javascript
// services/userService.js
class UserService {
  async getUser() {
    try {
      const response = await axiosClient.get('/user');
      return response.data;
    } catch (error) {
      throw new Error(`Failed to fetch user: ${error.message}`);
    }
  }
  
  async updateUser(userData) {
    try {
      const response = await axiosClient.put('/user', userData);
      return response.data;
    } catch (error) {
      throw new Error(`Failed to update user: ${error.message}`);
    }
  }
}

export default new UserService();
```

## Contributing Guidelines

### Pull Request Process
1. Update documentation if needed
2. Add tests for new functionality
3. Ensure all tests pass
4. Update CHANGELOG.md
5. Request review from team members

### Code Review Checklist
- [ ] Code follows style guidelines
- [ ] Tests are included and passing
- [ ] Documentation is updated
- [ ] No console.log statements in production code
- [ ] Error handling is implemented
- [ ] Performance impact is considered

### Issue Reporting
When reporting issues, include:
- Steps to reproduce
- Expected behavior
- Actual behavior
- Browser/OS information
- Screenshots if applicable
- Console error messages

---

For additional help, refer to the main documentation or contact the development team.
