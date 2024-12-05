# Building Your First Angular SPA - Practical Example

## 🚀 Simple SPA Project Structure

```
my-angular-spa/
├── src/
│   ├── app/
│   │   ├── components/
│   │   │   ├── home/
│   │   │   ├── about/
│   │   │   └── contact/
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   └── app-routing.module.ts
│   └── index.html
```

## 📝 Step-by-Step Implementation

### 1. Create New Project
```bash
ng new my-angular-spa --routing
```

### 2. Generate Components
```bash
ng generate component components/home
ng generate component components/about
ng generate component components/contact
```

### 3. Set Up Routing
```typescript
// app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './components/home/home.component';
import { AboutComponent } from './components/about/about.component';
import { ContactComponent } from './components/contact/contact.component';

const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent },
  { path: 'contact', component: ContactComponent },
  { path: '**', redirectTo: '' }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

### 4. Create Navigation Menu
```html
<!-- app.component.html -->
<nav>
  <ul>
    <li><a routerLink="/" routerLinkActive="active" 
           [routerLinkActiveOptions]="{exact: true}">Home</a></li>
    <li><a routerLink="/about" routerLinkActive="active">About</a></li>
    <li><a routerLink="/contact" routerLinkActive="active">Contact</a></li>
  </ul>
</nav>

<router-outlet></router-outlet>
```

### 5. Style the Navigation
```css
/* app.component.css */
nav {
  background: #333;
  padding: 1rem;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
}

nav a {
  color: white;
  text-decoration: none;
  padding: 0.5rem 1rem;
}

.active {
  background: #666;
  border-radius: 4px;
}
```

## 🔄 How It Works

```
User Interaction Flow:
┌─────────────┐
│ Click Link  │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Router      │
│ Intercepts  │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Update URL  │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Load New    │
│ Component   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ Render View │
└─────────────┘
```

## 🎯 Adding Features

### 1. Loading Indicator
```typescript
// app.component.ts
import { Router, Event, NavigationStart, NavigationEnd } from '@angular/router';

export class AppComponent {
  loading = false;

  constructor(private router: Router) {
    router.events.subscribe((event: Event) => {
      if (event instanceof NavigationStart) {
        this.loading = true;
      }
      if (event instanceof NavigationEnd) {
        this.loading = false;
      }
    });
  }
}
```

### 2. Page Transitions
```css
/* styles.css */
.page {
  animation: fadeIn 0.3s ease-in;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
```

### 3. Error Handling
```typescript
// app-routing.module.ts
const routes: Routes = [
  // ... other routes
  { path: '404', component: NotFoundComponent },
  { path: '**', redirectTo: '/404' }
];
```

## 💡 Best Practices

1. **Component Organization**
```
components/
├── shared/          # Reusable components
├── features/        # Feature-specific components
└── layout/          # Layout components
```

2. **Lazy Loading**
```typescript
const routes: Routes = [
  {
    path: 'admin',
    loadChildren: () => import('./admin/admin.module')
      .then(m => m.AdminModule)
  }
];
```

3. **Route Guards**
```typescript
@Injectable()
export class AuthGuard implements CanActivate {
  canActivate() {
    return this.authService.isLoggedIn();
  }
}
```

## 🚀 Running the Application

1. Start the development server:
```bash
ng serve
```

2. View in browser:
```
http://localhost:4200
```

## 📝 Testing Navigation

1. Click different navigation links
2. Observe URL changes
3. Notice no page reload
4. Watch component transitions
5. Check active link styles

Remember:
- SPAs provide smooth navigation
- Components load dynamically
- State persists between views
- User experience is seamless
