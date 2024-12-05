# Understanding Angular Project Structure - Demo App Guide

## Project Creation
To create a new Angular project, run:
```bash
ng new demo-app
```

## 📁 Complete Project Structure Explained
```
demo-app/
│
├── 📁 src/                      # Source files for the project
│   │
│   ├── 📁 app/                  # Main application code
│   │   ├── app.component.ts     # Root component class
│   │   ├── app.component.html   # Root component template
│   │   ├── app.component.css    # Root component styles
│   │   ├── app.component.spec.ts# Root component tests
│   │   └── app.module.ts        # Root module definition
│   │
│   ├── 📁 assets/              # Static assets (images, etc.)
│   │   └── .gitkeep
│   │
│   ├── 📁 environments/        # Environment configurations
│   │   ├── environment.ts      # Development environment
│   │   └── environment.prod.ts # Production environment
│   │
│   ├── favicon.ico            # Website icon
│   ├── index.html            # Main HTML file
│   ├── main.ts              # Main entry point
│   ├── polyfills.ts        # Browser polyfills
│   └── styles.css         # Global styles
│
├── 📁 node_modules/           # Third-party dependencies
│
├── 📁 e2e/                    # End-to-end tests
│   ├── src/
│   │   ├── app.e2e-spec.ts
│   │   └── app.po.ts
│   └── protractor.conf.js
│
├── .editorconfig             # Editor configuration
├── .gitignore               # Git ignore rules
├── angular.json             # Angular workspace configuration
├── package.json             # Project dependencies and scripts
├── README.md               # Project documentation
├── tsconfig.json           # TypeScript configuration
└── tslint.json            # Linting rules
```

## 📝 Key Files Explained

### 1. Root Configuration Files

#### 📄 package.json
```json
{
  "name": "demo-app",
  "version": "0.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test"
  },
  "dependencies": {
    "@angular/core": "~13.0.0",
    "@angular/common": "~13.0.0"
    // ... other dependencies
  }
}
```
- Manages project dependencies
- Defines npm scripts for common tasks
- Lists project metadata

#### 📄 angular.json
```json
{
  "projects": {
    "demo-app": {
      "architect": {
        "build": {
          "options": {
            "outputPath": "dist/demo-app",
            "index": "src/index.html",
            "main": "src/main.ts"
          }
        }
      }
    }
  }
}
```
- Configures Angular workspace
- Defines build options
- Sets up development server

### 2. Source Files

#### 📄 src/index.html
```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>DemoApp</title>
  <base href="/">
</head>
<body>
  <app-root></app-root>
</body>
</html>
```
- Entry point HTML
- Contains app-root component
- Links styles and scripts

#### 📄 src/main.ts
```typescript
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app/app.module';

platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));
```
- Bootstraps Angular application
- Loads root module (AppModule)

### 3. App Components

#### 📄 src/app/app.module.ts
```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
- Main application module
- Declares components
- Configures dependencies

#### 📄 src/app/app.component.ts
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'demo-app';
}
```
- Root component class
- Defines component behavior
- Links template and styles

## 🔍 Common Operations

### Starting the Development Server
```bash
ng serve
```
- Starts local development server
- Watches for file changes
- Enables hot reload

### Building the Application
```bash
ng build
```
- Creates production build
- Outputs to dist/ folder
- Optimizes for deployment

### Creating New Components
```bash
ng generate component new-component
```
Creates:
```
src/app/new-component/
├── new-component.component.ts
├── new-component.component.html
├── new-component.component.css
└── new-component.component.spec.ts
```

## 💡 Tips for Students

1. **Start with App Component**
   - Understand the root component first
   - Modify app.component.html
   - See changes in real-time

2. **Explore Generated Files**
   - Look through each file
   - Read comments and documentation
   - Understand file relationships

3. **Use Angular CLI**
   - Generate components with CLI
   - Run development server
   - Build for production

4. **Follow Best Practices**
   - Keep components small
   - Use proper naming conventions
   - Organize files logically

Remember: This structure is the foundation of every Angular application. Take time to understand each part before building complex features.
