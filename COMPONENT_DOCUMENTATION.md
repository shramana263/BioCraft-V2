# BioCraft - Component Library Documentation

## Table of Contents
1. [Overview](#overview)
2. [Core Components](#core-components)
3. [Layout Components](#layout-components)
4. [Form Components](#form-components)
5. [UI Components](#ui-components)
6. [Context Providers](#context-providers)
7. [Custom Hooks](#custom-hooks)
8. [Usage Examples](#usage-examples)

---

## Overview

This document provides comprehensive information about all reusable components in the BioCraft application. Each component is designed to be modular, reusable, and follows React best practices.

---

## Core Components

### App Component
**File:** `src/App.jsx`

Main application component that serves as the root of the component tree.

```jsx
const App = () => {
  return <></>; // Currently minimal, routing handled by Playground
};
```

### Playground Component
**File:** `src/router/Playground.jsx`

Main router component that handles authentication-based routing.

**Props:** None

**Features:**
- Authentication state management
- Layout switching based on auth status
- Lazy loading of router components
- Loading states

```jsx
const PlayGround = () => {
  const { token } = useStateContext();
  const [isGuest, setIsGuest] = useState(true);
  
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

---

## Layout Components

### AuthLayout
**File:** `src/layouts/AuthLayout.jsx`

Layout wrapper for authenticated users.

**Props:**
- `children` (ReactNode) - Child components to render

**Features:**
- User authentication validation
- Logout functionality
- Responsive sidebar support
- Dark mode integration
- Message notifications

```jsx
<AuthLayout>
  <Dashboard />
</AuthLayout>
```

### GuestLayout
**File:** `src/layouts/GuestLayout.jsx`

Layout wrapper for non-authenticated users.

**Props:**
- `children` (ReactNode) - Child components to render

**Features:**
- Guest navigation
- Responsive design
- Theme support
- Message notifications

```jsx
<GuestLayout>
  <Landing />
</GuestLayout>
```

### Navbar
**File:** `src/components/Structure/Navbar.jsx`

Main navigation component.

**Props:**
- `userName` (string, optional) - Logged in user's name
- `onLogout` (function, optional) - Logout handler

**Features:**
- Responsive navigation
- User menu dropdown
- Theme toggle
- Mobile menu support

### Sidebar
**File:** `src/components/Structure/Sidebar.jsx`

Side navigation component for authenticated users.

**Features:**
- Collapsible sidebar
- Navigation links
- User profile section
- Mobile-responsive

---

## Form Components

### FormikInputBox
**File:** `src/components/FormikInputBox.jsx`

Reusable input component integrated with Formik.

**Props:**
- `label` (string) - Input label
- `name` (string) - Formik field name
- `type` (string) - Input type (default: "text")
- `placeholder` (string) - Placeholder text
- `required` (boolean) - Whether field is required

```jsx
<FormikInputBox
  label="Email Address"
  name="email"
  type="email"
  placeholder="Enter your email"
  required
/>
```

### PersonalDetails
**File:** `src/components/post/PersonalDetails.jsx`

Multi-field form for personal information.

**Features:**
- Personal information collection
- File upload for profile image
- Form validation
- Progress tracking

### EducationDetails
**File:** `src/components/post/EducationDetails.jsx`

Dynamic form for educational background.

**Features:**
- Multiple education entries
- Add/remove functionality
- Date validation
- Institution information

### Experience
**File:** `src/components/post/Experience.jsx`

Work experience form component.

**Features:**
- Multiple job entries
- Date range validation
- Job description text areas
- Company information

### Skills
**File:** `src/components/post/Skills.jsx`

Skills management component.

**Features:**
- Skill categorization
- Add/remove skills
- Skill level indicators
- Tag-based interface

### Specialization
**File:** `src/components/post/Specialization.jsx`

Specialization and certification form.

**Features:**
- Certification details
- Validity dates
- Issuing organizations
- Multiple entries support

### SocialNetwork
**File:** `src/components/post/SocialNetwork.jsx`

Social media links form.

**Features:**
- Multiple platform support
- URL validation
- Icon integration
- Profile link management

---

## UI Components

### Templates
**File:** `src/components/Templates.jsx`

Template selection component.

**Features:**
- Template preview gallery
- Template selection
- Responsive grid layout
- Authentication-aware routing

```jsx
const bio_templates = [
  { src: "template1.jpg" },
  { src: "template2.jpg" },
  { src: "template3.jpg" },
  { src: "template4.jpg" }
];
```

### Preview
**File:** `src/components/Preview.jsx`

Template preview component.

**Props:**
- `templateData` (object) - Template configuration
- `onSelect` (function) - Template selection handler

### ImageSlider
**File:** `src/components/ImageSlider.jsx`

Image carousel component.

**Props:**
- `images` (array) - Array of image objects
- `autoPlay` (boolean) - Auto-play functionality
- `showDots` (boolean) - Show navigation dots

```jsx
<ImageSlider
  images={imageArray}
  autoPlay={true}
  showDots={true}
/>
```

### Landing
**File:** `src/components/Landing.jsx`

Main landing page component.

**Features:**
- Hero section
- Feature highlights
- Responsive design
- Call-to-action buttons

### Signin
**File:** `src/components/Signin.jsx`

User login form component.

**Features:**
- Form validation
- Error handling
- Remember me functionality
- Forgot password link

### Signup
**File:** `src/components/Signup.jsx`

User registration form component.

**Features:**
- Multi-step validation
- Password strength checking
- Terms acceptance
- Email verification

---

## Template Components

### Template1
**File:** `src/components/outputTemplate/Template1.jsx`

Classic professional biodata template.

**Features:**
- Clean layout
- Professional styling
- Print-optimized
- Data binding

### Template2
**File:** `src/components/outputTemplate/Template2.jsx`

Modern minimalist template.

**Features:**
- Contemporary design
- Minimalist approach
- Color customization
- Responsive layout

### Template3
**File:** `src/components/outputTemplate/Template3.jsx`

Creative colorful template.

**Features:**
- Vibrant colors
- Creative layout
- Visual elements
- Modern typography

### Template4
**File:** `src/components/outputTemplate/Template4.jsx`

Executive formal template.

**Features:**
- Executive styling
- Formal presentation
- Corporate design
- Professional layout

---

## Chatbot Components

### Chat
**File:** `src/chatbot/Chat.jsx`

Main chatbot interface component.

**Features:**
- Chat interface
- Message handling
- Bot responses
- User interaction

### ActionProvider
**File:** `src/chatbot/ActionProvider.jsx`

Handles chatbot actions and responses.

**Methods:**
- `handleUserMessage()` - Process user input
- `provideHelp()` - Provide assistance
- `navigateToSection()` - Navigation help

### MessageParser
**File:** `src/chatbot/MessageParser.jsx`

Parses user messages and determines intent.

**Methods:**
- `parseMessage()` - Analyze user input
- `extractIntent()` - Determine user intent
- `handleCommands()` - Process commands

### BotIcon
**File:** `src/chatbot/BotIcon.jsx`

Chatbot avatar component.

**Features:**
- Animated avatar
- Status indicators
- Customizable appearance

---

## Admin Components

### LandingAdmin
**File:** `src/admin/LandingAdmin.jsx`

Admin dashboard landing page.

**Features:**
- Analytics overview
- User management links
- System status
- Quick actions

### UserCard
**File:** `src/admin/components/UserCard.jsx`

User information display card.

**Props:**
- `user` (object) - User data
- `onEdit` (function) - Edit handler
- `onDelete` (function) - Delete handler

### UserList
**File:** `src/admin/components/UserList.jsx`

List of users with management options.

**Features:**
- Paginated user list
- Search functionality
- Sort options
- Bulk actions

### ActivityGraph
**File:** `src/admin/components/ActivityGraph.jsx`

User activity visualization.

**Features:**
- Chart.js integration
- Activity metrics
- Time-based data
- Interactive charts

### LoginGraph
**File:** `src/admin/components/LoginGraph.jsx`

Login analytics visualization.

**Features:**
- Login statistics
- Time-series data
- Trend analysis
- Export functionality

---

## Context Providers

### StateProvider
**File:** `src/contexts/StateContext.jsx`

Global application state management.

**Provided Values:**
- `user` - Current user object
- `token` - Authentication token
- `setUser()` - Update user
- `setToken()` - Update token

### ThemeProvider
**File:** `src/contexts/ThemeContext.jsx`

Theme management (dark/light mode).

**Provided Values:**
- `isDark` - Current theme state
- `setDark()` - Toggle theme

### DataProvider
**File:** `src/contexts/DataContext.jsx`

Form data management.

**Provided Values:**
- `profileImage` - Profile image state
- `formData` - Current form data
- `updateData()` - Update form data
- `deleteData()` - Delete data entry

### ProgressProvider
**File:** `src/contexts/ProgressContext.jsx`

Multi-step form progress tracking.

**Provided Values:**
- `currentStep` - Current form step
- `nextStep()` - Advance to next step
- `previousStep()` - Go to previous step
- `resetProgress()` - Reset to beginning

### MobileProvider
**File:** `src/contexts/MobileContext.jsx`

Mobile responsiveness management.

**Provided Values:**
- `isMobile` - Mobile state
- `screenSize` - Current screen dimensions

### PanelProvider
**File:** `src/contexts/PanelContext.jsx`

Sidebar and panel state management.

**Provided Values:**
- `isSidebarOpen` - Sidebar state
- `toggleSidebar()` - Toggle sidebar

### MessageProvider
**File:** `src/contexts/MessageContext.jsx`

Notification and message management.

**Provided Values:**
- `message` - Current message
- `messageType` - Message type (success, error, warning)
- `showMessage()` - Display message
- `clearMessage()` - Clear message

---

## Custom Hooks

### useStateContext
Access global application state.

```jsx
const { user, token, setUser, setToken } = useStateContext();
```

### useThemeContext
Access theme state and controls.

```jsx
const { isDark, setDark } = useThemeContext();
```

### useDataContext
Access form data management.

```jsx
const { 
  profileImage, 
  setProfileImage, 
  deleteUserData 
} = useDataContext();
```

### useProgressContext
Access form progress controls.

```jsx
const { 
  isNext, 
  setNext, 
  nextButton 
} = useProgressContext();
```

### useMobileContext
Access mobile responsiveness state.

```jsx
const { isMobile, setMobile } = useMobileContext();
```

### usePanelContext
Access sidebar and panel controls.

```jsx
const { 
  isSidebarOpen, 
  setSidebarOpen 
} = usePanelContext();
```

### useMessageContext
Access notification system.

```jsx
const { 
  message, 
  setMessage, 
  messageType 
} = useMessageContext();
```

---

## Usage Examples

### Basic Component Usage
```jsx
import React from 'react';
import { useStateContext } from '../contexts/StateContext';
import FormikInputBox from '../components/FormikInputBox';

const MyComponent = () => {
  const { user } = useStateContext();
  
  return (
    <div className="my-component">
      <h1>Welcome, {user?.name}</h1>
      <FormikInputBox
        label="Email"
        name="email"
        type="email"
        required
      />
    </div>
  );
};
```

### Context Provider Setup
```jsx
import React from 'react';
import { StateProvider } from './contexts/StateContext';
import { ThemeProvider } from './contexts/ThemeContext';
import App from './App';

const Root = () => {
  return (
    <StateProvider>
      <ThemeProvider>
        <App />
      </ThemeProvider>
    </StateProvider>
  );
};
```

### Form Integration
```jsx
import { Formik, Form } from 'formik';
import * as Yup from 'yup';
import FormikInputBox from '../components/FormikInputBox';

const UserForm = () => {
  const validationSchema = Yup.object({
    name: Yup.string().required('Name is required'),
    email: Yup.string().email('Invalid email').required('Email is required'),
  });

  const handleSubmit = (values) => {
    console.log('Form submitted:', values);
  };

  return (
    <Formik
      initialValues={{ name: '', email: '' }}
      validationSchema={validationSchema}
      onSubmit={handleSubmit}
    >
      <Form>
        <FormikInputBox
          label="Full Name"
          name="name"
          placeholder="Enter your name"
          required
        />
        <FormikInputBox
          label="Email Address"
          name="email"
          type="email"
          placeholder="Enter your email"
          required
        />
        <button type="submit">Submit</button>
      </Form>
    </Formik>
  );
};
```

### Template Usage
```jsx
import Template1 from '../components/outputTemplate/Template1';
import { useDataContext } from '../contexts/DataContext';

const BiodataPreview = () => {
  const { userData } = useDataContext();
  
  return (
    <div className="biodata-preview">
      <Template1 data={userData} />
    </div>
  );
};
```

---

## Best Practices

### Component Design
1. Keep components small and focused
2. Use TypeScript for prop validation
3. Implement proper error boundaries
4. Follow accessibility guidelines
5. Use semantic HTML elements

### State Management
1. Use context for global state only
2. Keep local state in components when possible
3. Implement proper loading and error states
4. Use React Query for server state

### Performance
1. Use React.memo for expensive components
2. Implement lazy loading for large components
3. Optimize re-renders with useMemo and useCallback
4. Use proper key props in lists

### Testing
1. Write unit tests for all components
2. Test user interactions
3. Mock external dependencies
4. Test accessibility features

---

This documentation should be updated whenever new components are added or existing components are modified.
