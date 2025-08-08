## Project Overview

Build a functional quiz application MVP with WYSIWYG editor, basic question types, and simple white-labeling - all deployable on a single VPS.

## Technology Stack (Simplified)

### Frontend

- **React** + TypeScript + Tailwind CSS
- **Slate.js** for WYSIWYG editor (lightweight)
- **Monaco Editor** for code challenges
- **React Hook Form** for forms

### Backend

- **Node.js + Express**
- **PostgreSQL** database
- **Redis** for sessions/caching
- **JWT** for authentication

### Infrastructure (Single VPS)

- **Docker Compose** for orchestration
- **Nginx** as reverse proxy
- **PM2** for process management
- **Simple monitoring** with Docker health checks

## Week 1: Foundation & Core Setup

### Day 1-2: Project Setup & Infrastructure

**Tasks:**

- Set up VPS with Docker and Docker Compose
- Create project structure (monorepo or separate repos)
- Configure Nginx reverse proxy
- Set up PostgreSQL and Redis containers
- Basic CI/CD pipeline (GitHub Actions)

**Docker Compose Services:**

```yaml
# docker-compose.yml
services:
  frontend, backend, postgres, redis, nginx
```

### Day 3-5: Authentication & Basic UI

**Tasks:**

- User registration/login with JWT
- Basic dashboard layout
- Organization/tenant setup (simple)
- Database schema creation
- API endpoints for auth

**Key Components:**

- Login/Register forms
- Protected routes
- Basic navigation
- Simple tenant context

### Day 6-7: Database Design & API Foundation

**Tasks:**

- Complete database schema
- API endpoints for CRUD operations
- Basic error handling
- Input validation

**Core Tables:**

```sql
users, organizations, quizzes, questions, responses, sessions
```

## Week 2: Core Quiz Functionality

### Day 8-10: WYSIWYG Quiz Builder

**Tasks:**

- Implement Slate.js rich text editor
- Create question components (MCQ, Short Answer)
- Drag-and-drop question ordering
- Quiz preview functionality

**Components:**

- `QuizBuilder` - main editor interface
- `QuestionEditor` - individual question editing
- `RichTextEditor` - Slate.js wrapper
- `QuestionTypes` - MCQ and Short Answer

### Day 11-12: Quiz Taking Interface

**Tasks:**

- Quiz player component
- Answer submission handling
- Basic timer functionality
- Results calculation and display

**Components:**

- `QuizPlayer` - main quiz interface
- `QuestionRenderer` - displays questions
- `ProgressBar` - shows completion
- `ResultsPage` - shows scores

### Day 13-14: Code Challenge Feature

**Tasks:**

- Monaco Editor integration
- Simple code execution (Node.js sandbox)
- Test case creation
- Basic syntax highlighting

**Implementation:**

- Docker container for code execution
- Simple test runner
- Security: limited execution time/memory

## Week 3: SaaS Features & Deployment

### Day 15-17: White-Labeling Basics

**Tasks:**

- Custom branding (logo, colors)
- Subdomain routing
- Theme system implementation
- Basic multi-tenancy

**Features:**

- Upload custom logo
- Set primary/secondary colors
- Custom domain mapping (simple)
- Tenant-specific data isolation

### Day 18-19: Basic Analytics & Polish

**Tasks:**

- Simple analytics dashboard
- Quiz performance metrics
- UI/UX improvements
- Bug fixes and testing

**Metrics:**

- Quiz completion rates
- Average scores
- Question performance
- Basic charts with Chart.js

### Day 20-21: Production Deployment

**Tasks:**

- VPS production setup
- Environment variables configuration
- SSL certificate setup (Let's Encrypt)
- Basic monitoring setup
- Backup strategy

## Simplified Feature Set (MVP)

### Quiz Builder

- ✅ Rich text editor (Slate.js)
- ✅ MCQ questions (single/multiple choice)
- ✅ Short answer questions
- ✅ Basic tracing (simple drawing canvas)
- ✅ Code challenges (JavaScript only)

### Quiz Taking

- ✅ Responsive player interface
- ✅ Progress tracking
- ✅ Auto-save (local storage)
- ✅ Basic timer
- ✅ Immediate results

### White-Labeling

- ✅ Custom logo upload
- ✅ Color customization
- ✅ Basic subdomain support
- ❌ Advanced theming (future)
- ❌ Custom CSS (future)

### Admin Features

- ✅ User management
- ✅ Basic analytics
- ✅ Organization settings
- ❌ Advanced reporting (future)

## VPS Setup Requirements

### Server Specifications

- **RAM**: 4GB minimum (8GB recommended)
- **Storage**: 40GB SSD minimum
- **CPU**: 2 cores minimum
- **OS**: Ubuntu 22.04 LTS

### Docker Services Configuration

```bash
# Services to run
- Frontend (React build served by Nginx)
- Backend API (Node.js + Express)
- PostgreSQL database
- Redis cache
- Code execution sandbox
- Nginx reverse proxy
```

### Estimated Monthly VPS Cost

- **Basic VPS**: $20-40/month
- **Domain**: $12/year
- **SSL Certificate**: Free (Let's Encrypt)
- **Total Monthly**: ~$25-45

## Development Resources

### Essential Libraries

```json
{
  "frontend": [
    "react", "typescript", "tailwindcss",
    "slate-react", "@monaco-editor/react",
    "react-hook-form", "axios", "chart.js"
  ],
  "backend": [
    "express", "pg", "redis", "jsonwebtoken",
    "bcryptjs", "multer", "joi", "cors"
  ]
}
```

### Key Documentation

- **Slate.js**: https://docs.slatejs.org/
- **Monaco Editor**: https://microsoft.github.io/monaco-editor/
- **Docker Compose**: https://docs.docker.com/compose/
- **PostgreSQL**: https://node-postgres.com/

## Daily Development Schedule

### Week 1 Focus: Infrastructure

- Morning: Backend API development
- Afternoon: Frontend setup and basic UI
- Evening: Docker configuration and deployment

### Week 2 Focus: Core Features

- Morning: Quiz builder implementation
- Afternoon: Question types and editor
- Evening: Testing and bug fixes

### Week 3 Focus: Polish & Deploy

- Morning: White-labeling features
- Afternoon: Analytics and final features
- Evening: Production deployment and testing

## Success Criteria (MVP)

### Functional Requirements

- ✅ Create quizzes with 3+ question types
- ✅ Take quizzes with real-time feedback
- ✅ Basic code challenges work
- ✅ Simple white-labeling (logo + colors)
- ✅ Multi-tenant data separation

### Technical Requirements

- ✅ Deployed on VPS with Docker
- ✅ SSL enabled
- ✅ Basic monitoring active
- ✅ Database backups configured
- ✅ Load time < 3 seconds

### Performance Targets

- Handle 100 concurrent users
- Quiz load time < 2 seconds
- Code execution < 5 seconds
- 99% uptime during testing

## Post-MVP Roadmap (Future Weeks)

### Week 4-5: Enhanced Features

- Advanced question types
- Better analytics
- Email notifications
- Improved UI/UX

### Week 6-8: Scaling

- Performance optimization
- Advanced white-labeling
- Payment integration
- API documentation

## Deployment Checklist

- [ ] VPS configured with Docker
- [ ] SSL certificate installed
- [ ] Environment variables set
- [ ] Database migrations run
- [ ] Monitoring containers active
- [ ] Backup cron jobs configured
- [ ] Domain DNS configured
- [ ] Basic security hardening done

## Risk Mitigation

### Technical Risks

- **VPS limitations**: Start small, plan for horizontal scaling
- **Code execution security**: Use Docker containers with resource limits
- **Data loss**: Automated daily backups to cloud storage

### Timeline Risks

- **Feature creep**: Stick to MVP scope
- **Integration issues**: Use battle-tested libraries
- **Deployment problems**: Test deployment early and often

This condensed plan focuses on delivering a working MVP in 3 weeks that can be deployed on a single VPS and demonstrates all core functionality.