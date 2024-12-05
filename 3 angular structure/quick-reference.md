# Angular Structure Quick Reference

## 🔑 Key Files Cheat Sheet

### Root Files
```
📄 package.json
• npm dependencies
• project scripts (start, build, test)

📄 angular.json
• project configuration
• build options
• development server settings

📄 tsconfig.json
• TypeScript settings
```

### Source Files (src/)
```
📄 index.html
• entry point HTML
• contains <app-root>

📄 main.ts
• bootstraps application
• loads root module

📄 styles.css
• global styles
```

### App Files (src/app/)
```
📄 app.module.ts
• declares components
• imports modules
• provides services

📄 app.component.ts
• root component
• main application logic

📄 app.component.html
• main application template
```

## 📁 Common Folders

### Components
```
components/
• UI building blocks
• feature-specific views
• reusable elements
```

### Services
```
services/
• data operations
• business logic
• shared functionality
```

### Models
```
models/
• data structures
• interfaces
• type definitions
```

### Assets
```
assets/
• images
• icons
• static files
```

## 🎯 Quick Tips

1. Component Files:
   ```
   feature.component.ts    → Logic
   feature.component.html  → Template
   feature.component.css   → Styles
   ```

2. Service Pattern:
   ```
   data.service.ts
   auth.service.ts
   ```

3. Module Pattern:
   ```
   feature.module.ts
   shared.module.ts
   ```

Remember:
- Keep related files together
- Use clear naming
- Follow Angular conventions
