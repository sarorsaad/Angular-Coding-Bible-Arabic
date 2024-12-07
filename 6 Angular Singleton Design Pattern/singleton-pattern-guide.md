# Angular Singleton Design Pattern Guide

## What is the Singleton Pattern? 🎯

The Singleton pattern is a design pattern that ensures a class has only one instance throughout the entire application lifecycle while providing global access to that instance.

## Key Characteristics

1. **Single Instance**: Only one instance exists across the application
2. **Global Access**: The instance is accessible from anywhere in the application
3. **Lazy Initialization**: The instance is created only when first requested

## Implementation in Angular 🛠️

### 1. Services as Singletons

Angular services are singletons by default when:
- Provided in the root level (`@Injectable({ providedIn: 'root' })`)
- Included in AppModule's providers array

```typescript
@Injectable({
  providedIn: 'root'
})
export class DataService {
  private data: any[] = [];

  getData(): any[] {
    return this.data;
  }

  addData(item: any): void {
    this.data.push(item);
  }
}
```

## Real-World Use Cases 🌟

### 1. User Authentication Service

```typescript
@Injectable({
  providedIn: 'root'
})
export class AuthService {
  private currentUser: User | null = null;

  login(credentials: {username: string, password: string}): Observable<User> {
    // Login logic here
    return this.http.post<User>('/api/login', credentials)
      .pipe(
        tap(user => this.currentUser = user)
      );
  }

  getCurrentUser(): User | null {
    return this.currentUser;
  }

  isLoggedIn(): boolean {
    return !!this.currentUser;
  }

  logout(): void {
    this.currentUser = null;
  }
}
```

### 2. Shopping Cart Service

```typescript
@Injectable({
  providedIn: 'root'
})
export class CartService {
  private items: Product[] = [];

  addToCart(product: Product): void {
    this.items.push(product);
  }

  getItems(): Product[] {
    return this.items;
  }

  clearCart(): void {
    this.items = [];
  }

  getTotal(): number {
    return this.items.reduce((sum, item) => sum + item.price, 0);
  }
}
```

### 3. Theme Service

```typescript
@Injectable({
  providedIn: 'root'
})
export class ThemeService {
  private currentTheme: string = 'light';

  setTheme(theme: 'light' | 'dark'): void {
    this.currentTheme = theme;
    document.body.className = theme;
  }

  getCurrentTheme(): string {
    return this.currentTheme;
  }

  toggleTheme(): void {
    this.setTheme(this.currentTheme === 'light' ? 'dark' : 'light');
  }
}
```

## When to Use Singleton Pattern? 🤔

### Good Use Cases ✅

1. **State Management**
   - User authentication state
   - Shopping cart data
   - Application configuration
   - Theme settings

2. **Shared Resources**
   - Database connections
   - HTTP clients
   - WebSocket connections
   - Cache management

3. **Configuration Services**
   - App settings
   - Environment variables
   - Feature flags

### When to Avoid ❌

1. **Component-Specific Logic**
   - UI state that should be isolated
   - Component-level data
   - Temporary form data

2. **Heavy Objects**
   - Large data structures that aren't always needed
   - Resource-intensive operations

## Best Practices 📝

1. **Use Angular's DI System**
   - Let Angular handle singleton creation
   - Use `providedIn: 'root'` for services

2. **Keep Services Focused**
   - Single responsibility principle
   - Clear and specific purpose
   - Well-defined public API

3. **State Management**
   - Consider using proper state management libraries for complex states
   - Use BehaviorSubject for reactive state management

4. **Testing**
   - Make services easily testable
   - Use dependency injection for better unit testing
   - Mock singleton services in tests

## Example Implementation with State Management

```typescript
@Injectable({
  providedIn: 'root'
})
export class StateService {
  private stateSubject = new BehaviorSubject<AppState>(initialState);
  state$ = this.stateSubject.asObservable();

  updateState(newState: Partial<AppState>): void {
    this.stateSubject.next({
      ...this.stateSubject.value,
      ...newState
    });
  }

  getCurrentState(): AppState {
    return this.stateSubject.value;
  }
}
```

## Conclusion

The Singleton pattern in Angular is powerful when used appropriately. It's best suited for managing application-wide state and shared resources. Angular's dependency injection system makes it easy to implement singletons through services, but remember to use them judiciously and only when they truly add value to your application architecture.
