# Angular Project Structure Guide for Beginners

## Project Root Structure
```
my-angular-app/
├── src/                  # Main source code folder
├── node_modules/         # Dependencies
├── package.json          # Project configuration
├── angular.json         # Angular configuration
├── tsconfig.json        # TypeScript configuration
└── README.md            # Project documentation
```

## Source Folder (src/) Structure
```
src/
├── app/                 # Main application code
├── assets/             # Static files (images, etc.)
├── environments/       # Environment configurations
├── favicon.ico        # Website icon
├── index.html         # Main HTML file
├── main.ts            # Application entry point
└── styles.css         # Global styles
```

## 🎯 Key Files and Their Roles

### 1. Configuration Files
```
📄 package.json
• Purpose: Project management
• Contains: 
  - Dependencies list
  - Scripts for running/building
  - Project metadata

📄 angular.json
• Purpose: Angular workspace config
• Contains:
  - Build settings
  - Development server settings
  - Test configurations

📄 tsconfig.json
• Purpose: TypeScript settings
• Contains:
  - Compiler options
  - Path mappings
  - TypeScript rules
```

### 2. Source Files
```
📄 src/index.html
• Purpose: Entry HTML page
• Role: 
  - Loads initial application
  - Contains <app-root>
  - Links global styles

📄 src/main.ts
• Purpose: Application bootstrap
• Role:
  - Starts Angular application
  - Sets up environment
  - Loads main module

📄 src/styles.css
• Purpose: Global styles
• Role:
  - Defines app-wide CSS
  - Sets default styling
```

## 📁 App Folder Structure (src/app/)
```
app/
├── app.component.ts       # Root component
├── app.component.html     # Root template
├── app.component.css      # Root styles
├── app.component.spec.ts  # Root tests
├── app.module.ts         # Root module
└── components/           # Feature components
```

## 🔍 Component Structure
```
components/
└── feature/
    ├── feature.component.ts       # Logic
    ├── feature.component.html     # Template
    ├── feature.component.css      # Styles
    └── feature.component.spec.ts  # Tests
```

## 📚 Common Folders and Their Purpose

### 1. Components Folder
```
components/
• Purpose: UI Building Blocks
• Contains:
  - Feature components
  - Reusable components
  - Page components
Example files:
  - header.component.ts
  - sidebar.component.ts
  - footer.component.ts
```

### 2. Services Folder
```
services/
• Purpose: Business Logic & Data
• Contains:
  - API calls
  - Data processing
  - Shared functionality
Example files:
  - data.service.ts
  - auth.service.ts
  - util.service.ts
```

### 3. Models Folder
```
models/
• Purpose: Data Structure Definitions
• Contains:
  - Interfaces
  - Classes
  - Type definitions
Example files:
  - user.model.ts
  - product.interface.ts
  - types.ts
```

### 4. Guards Folder
```
guards/
• Purpose: Route Protection
• Contains:
  - Authentication guards
  - Authorization guards
Example files:
  - auth.guard.ts
  - admin.guard.ts
```

## 🛠️ Best Practices for Structure

### 1. Feature Modules
```
features/
└── feature-name/
    ├── components/     # Feature components
    ├── services/       # Feature services
    ├── models/        # Feature models
    └── feature.module.ts
```

### 2. Shared Module
```
shared/
├── components/        # Reusable components
├── pipes/            # Custom pipes
├── directives/       # Custom directives
└── shared.module.ts
```

### 3. Core Module
```
core/
├── services/         # Singleton services
├── guards/           # Route guards
├── interceptors/     # HTTP interceptors
└── core.module.ts
```

## 📝 Quick Reference Guide

### Common File Types
```
• *.component.ts    → Component logic
• *.component.html  → Component template
• *.component.css   → Component styles
• *.service.ts      → Services
• *.module.ts       → Modules
• *.guard.ts        → Route guards
• *.pipe.ts         → Custom pipes
• *.directive.ts    → Custom directives
• *.model.ts        → Data models
• *.interface.ts    → TypeScript interfaces
```

### Important Default Files
```
• app.module.ts     → Main application module
• app.component.ts  → Root component
• main.ts          → Application entry point
• index.html       → Main HTML file
• styles.css       → Global styles
```

## 🚀 Tips for Beginners

1. **Start Small**
   - Focus on app.component first
   - Add components gradually
   - Keep structure simple initially

2. **Organization Tips**
   - Group related files together
   - Use clear, descriptive names
   - Follow Angular naming conventions

3. **Common Patterns**
   - Feature-based organization
   - Shared module for reusable items
   - Core module for app-wide services

4. **File Naming**
   - Use kebab-case for files
   - Include the type in the name
   - Follow Angular style guide

Remember: This structure grows with your application. Start simple and expand as needed!
