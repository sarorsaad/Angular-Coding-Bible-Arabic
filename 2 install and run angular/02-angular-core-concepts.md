# Angular Core Concepts - Visual Guide

## 1. Component Architecture
```
┌──────────────── Component ────────────────┐
│                                          │
│  ┌─────────────┐    ┌─────────────┐     │
│  │  Template   │    │   Styles    │     │
│  │  (HTML)     │    │   (CSS)     │     │
│  └─────────────┘    └─────────────┘     │
│          ▲                ▲              │
│          │                │              │
│    ┌─────────────────────────────┐      │
│    │      Component Class        │      │
│    │      (TypeScript)          │      │
│    └─────────────────────────────┘      │
└──────────────────────────────────────────┘
```

## 2. Data Flow in Components
```
┌─────────── Parent Component ───────────┐
│                                       │
│  ┌────────────┐      ┌────────────┐  │
│  │   @Input   │ ──▶  │ Properties │  │
│  └────────────┘      └────────────┘  │
│         ▲                             │
│         │                             │
└─────────│─────────────────────────────┘
          │
┌─────────│─────────────────────────────┐
│         │                             │
│  ┌────────────┐      ┌────────────┐  │
│  │  @Output   │ ◀──  │   Events   │  │
│  └────────────┘      └────────────┘  │
│                                       │
└─────── Child Component ───────────────┘
```

## 3. Module Structure
```
┌─────────────── NgModule ──────────────┐
│                                       │
│  ┌─────────────┐    ┌─────────────┐  │
│  │ Declarations│    │   Imports    │  │
│  │ Components  │    │   Other      │  │
│  │ Directives  │    │   Modules    │  │
│  │ Pipes      │    │              │  │
│  └─────────────┘    └─────────────┘  │
│                                       │
│  ┌─────────────┐    ┌─────────────┐  │
│  │  Exports    │    │  Providers  │  │
│  │  Shared     │    │  Services   │  │
│  │  Components │    │             │  │
│  └─────────────┘    └─────────────┘  │
└───────────────────────────────────────┘
```

## 4. Service and Dependency Injection
```
┌─────────────── Service ───────────────┐
│                                       │
│  ┌─────────────────────────────────┐  │
│  │        @Injectable()            │  │
│  └─────────────────────────────────┘  │
│                  │                     │
│                  ▼                     │
│  ┌─────────────────────────────────┐  │
│  │     Business Logic & Data       │  │
│  └─────────────────────────────────┘  │
│                  │                     │
└──────────────────│────────────────────┘
                   │
┌──────────────────│────────────────────┐
│  Component       ▼                     │
│  ┌─────────────────────────────────┐  │
│  │   constructor(                  │  │
│  │     private service: Service    │  │
│  │   ) { }                        │  │
│  └─────────────────────────────────┘  │
└───────────────────────────────────────┘
```

## 5. Angular Application Flow
```
┌─────────────── Browser ───────────────┐
│                                       │
│  ┌─────────────┐    ┌─────────────┐  │
│  │   index.html│───▶│  main.ts    │  │
│  └─────────────┘    └─────────────┘  │
│                           │           │
│                           ▼           │
│  ┌─────────────┐    ┌─────────────┐  │
│  │  AppModule  │◀───│ Bootstrap   │  │
│  └─────────────┘    └─────────────┘  │
│         │                             │
│         ▼                             │
│  ┌─────────────┐    ┌─────────────┐  │
│  │AppComponent │───▶│  Components │  │
│  └─────────────┘    └─────────────┘  │
└───────────────────────────────────────┘
```

## 6. Template Syntax Highlights
```
┌─────────── Template Features ─────────┐
│                                       │
│  ★ Data Binding                       │
│  ├── {{ interpolation }}              │
│  ├── [property]="value"              │
│  ├── (event)="handler()"             │
│  └── [(ngModel)]="property"          │
│                                       │
│  ⚡ Directives                         │
│  ├── *ngIf="condition"               │
│  ├── *ngFor="let item of items"      │
│  └── [ngClass]="{'class': condition}" │
│                                       │
│  ⚙ Pipes                             │
│  ├── {{ value | uppercase }}         │
│  ├── {{ date | date:'short' }}       │
│  └── {{ price | currency }}          │
└───────────────────────────────────────┘
```

## 7. Lifecycle Hooks Timeline
```
┌──────────── Component Lifecycle ──────────┐
│                                          │
│  1. ⚡ constructor()                      │
│     └── Component instance created       │
│                                          │
│  2. ★ ngOnChanges()                      │
│     └── Input properties changed         │
│                                          │
│  3. ▶ ngOnInit()                         │
│     └── Component initialized            │
│                                          │
│  4. □ ngDoCheck()                        │
│     └── Change detection                 │
│                                          │
│  5. ◆ ngAfterViewInit()                  │
│     └── View initialized                 │
│                                          │
│  6. ■ ngOnDestroy()                      │
│     └── Cleanup before destruction       │
└──────────────────────────────────────────┘
```

## Color Guide
```
Symbols meaning:
★ - Primary feature
⚡ - Important concept
▶ - Action/Event
□ - Check/Validation
◆ - View related
■ - Lifecycle related
```

## Best Practices
```
┌─────────── Angular Best Practices ────────┐
│                                          │
│  1. Component Organization               │
│     ├── Small, focused components        │
│     └── Single responsibility            │
│                                          │
│  2. Data Management                      │
│     ├── Use services for shared data     │
│     └── Minimize component state         │
│                                          │
│  3. Performance                          │
│     ├── Use OnPush change detection      │
│     └── Lazy load modules               │
│                                          │
│  4. Code Style                          │
│     ├── Follow Angular style guide      │
│     └── Use TypeScript features         │
└──────────────────────────────────────────┘
```
