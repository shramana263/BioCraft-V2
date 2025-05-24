# BioCraft - Professional Biodata Generator

[![React](https://img.shields.io/badge/React-18.2.0-blue.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-5.2.0-646CFF.svg)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4.3-38B2AC.svg)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

BioCraft is a comprehensive biodata generator web application that enables users to create professional biodata documents using customizable templates. The platform offers extensive customization options, allowing users to generate diverse biodata formats from a single data entry.

## 🚀 Features

- **Multi-Template Support**: 4+ professional biodata templates
- **Responsive Design**: Mobile-first approach with seamless desktop experience
- **Dark/Light Mode**: Customizable theme support
- **Multi-Step Forms**: Intuitive step-by-step data collection
- **Real-time Preview**: Live preview of biodata while editing
- **PDF Export**: High-quality PDF generation
- **User Authentication**: Secure login and registration system
- **Data Management**: Complete CRUD operations for user data
- **Chatbot Integration**: AI-powered user assistance
- **Admin Panel**: Administrative dashboard for user management
- **Job Search Integration**: Built-in job search functionality

## 🏗️ Project Architecture

### Project Phases
1. **Phase 1**: Template Integration ✅
2. **Phase 2**: User Interface Integration ✅
3. **Phase 3**: Data Storage Integration ✅

### Technology Stack

#### Frontend
- **Framework**: React.js 18.2.0
- **Build Tool**: Vite 5.2.0
- **Styling**: Tailwind CSS 3.4.3, CSS Modules
- **Routing**: React Router DOM 6.23.1
- **State Management**: React Context API
- **Form Handling**: Formik 2.4.6
- **HTTP Client**: Axios 1.7.7
- **Data Fetching**: TanStack React Query 5.37.1

#### Backend
- **Framework**: Laravel (PHP)
- **Database**: MySQL
- **Authentication**: JWT
- **API**: RESTful services

## 📂 Project Structure

```
code/
├── public/                 # Static assets
├── src/
│   ├── admin/             # Admin panel components
│   ├── chatbot/           # Chatbot functionality
│   ├── components/        # Reusable UI components
│   ├── contexts/          # React Context providers
│   ├── layouts/           # Layout components
│   ├── pages/             # Page components
│   ├── router/            # Routing configuration
│   ├── services/          # API services
│   └── styles/            # Global styles
├── docs/                  # Documentation
└── package.json
```

## 🛠️ Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- Git

### Quick Start

1. **Clone the Repository**
   ```bash
   git clone [repository-url]
   cd biodatamakerv2/code
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   ```
   
   Configure your environment variables:
   ```env
   VITE_APP_BASE_URL=http://localhost:8000
   VITE_APP_ENV=development
   ```

4. **Start Development Server**
   ```bash
   npm run dev
   ```

5. **Open in Browser**
   ```
   http://localhost:5173
   ```

### Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint
npm test             # Run tests
```

## 🎯 Key Features & Usage

### Creating Biodata
1. **Register/Login** to your account
2. **Fill Personal Details** in the multi-step form
3. **Add Education** background and qualifications
4. **Include Work Experience** and achievements
5. **List Skills** and competencies
6. **Add Social Links** and professional profiles
7. **Choose Template** from available designs
8. **Preview & Download** your biodata as PDF

### Template System
- **Template 1**: Classic professional layout
- **Template 2**: Modern minimalist design
- **Template 3**: Creative colorful format
- **Template 4**: Executive formal style

### User Management
- Secure authentication with JWT tokens
- Profile management and data updates
- Multiple biodata versions support
- Data export and sharing options

## 🔗 API Integration

### Backend Repository
The backend API is maintained separately:
```
https://github.com/shramana263/BioCraftApi
```

### API Endpoints
- `POST /api/login` - User authentication
- `GET /api/user` - Get user profile
- `POST /api/biodata` - Create biodata
- `GET /api/biodata` - Retrieve biodata
- `PUT /api/biodata/{id}` - Update biodata
- `DELETE /api/biodata/{id}` - Delete biodata

## 📱 Responsive Design

BioCraft is built with a mobile-first approach:
- **Mobile**: Optimized for smartphones
- **Tablet**: Adapted for medium screens
- **Desktop**: Full-featured desktop experience
- **Print**: Print-optimized layouts

## 🎨 Theming & Customization

### Dark/Light Mode
- System preference detection
- Manual theme switching
- Persistent theme storage
- Smooth transitions

### Tailwind CSS Configuration
- Custom color palette
- Extended spacing scale
- Custom animations
- Responsive breakpoints

## 🧪 Testing

### Testing Strategy
- Unit tests for components
- Integration tests for workflows
- E2E tests for critical paths
- API integration tests

### Running Tests
```bash
npm test              # Run all tests
npm run test:watch    # Run tests in watch mode
npm run test:coverage # Generate coverage report
```

## 📈 Performance

### Optimization Features
- Code splitting by routes
- Lazy loading of components
- Image optimization
- Bundle size optimization
- Caching strategies

### Performance Metrics
- Lighthouse Score: 90+
- First Contentful Paint: <2s
- Time to Interactive: <3s
- Bundle Size: <500KB gzipped

## 🚀 Deployment

### Build for Production
```bash
npm run build
```

### Deployment Platforms
- **Vercel**: Automatic deployments
- **Netlify**: JAMstack deployment
- **Traditional Hosting**: Static file hosting

### Environment Configuration
```bash
# Production
VITE_APP_BASE_URL=https://api.biocraft.com
VITE_APP_ENV=production
```

## 📚 Documentation

Comprehensive documentation is available:

- **[Software Documentation](SOFTWARE_DOCUMENTATION.md)** - Complete system overview
- **[API Documentation](API_DOCUMENTATION.md)** - Backend API reference
- **[User Manual](USER_MANUAL.md)** - End-user guide
- **[Developer Guide](DEVELOPER_GUIDE.md)** - Development setup and guidelines
- **[Component Documentation](COMPONENT_DOCUMENTATION.md)** - Component library reference

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Process
1. Fork the repository
2. Create feature branch
3. Make changes with tests
4. Submit pull request
5. Code review and merge

### Code Style
- ESLint configuration
- Prettier formatting
- Conventional commit messages
- TypeScript support

## 🐛 Troubleshooting

### Common Issues

#### Build Failures
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

#### Development Server Issues
```bash
# Clear Vite cache
rm -rf node_modules/.vite
npm run dev
```

For more troubleshooting help, see our [Developer Guide](DEVELOPER_GUIDE.md).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- React.js community for excellent documentation
- Tailwind CSS for the utility-first approach
- Vite for fast build tooling
- All contributors who helped build BioCraft

## 📞 Support

- **Issues**: [GitHub Issues](issues)
- **Documentation**: See the comprehensive documentations
- **Email**: shramanashow@gmail.com

---

**Made with ❤️ by the BioCraft Team**
