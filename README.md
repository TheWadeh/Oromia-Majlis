# ORIASC - Majlisa Oromiyaa Website

A full-stack web application for Majlisa Oromiyaa Islamic Center built with React, TypeScript, Laravel, and MySQL.

**Live Site:** [oriasc.org](https://oriasc.org)

![Hero](public/hero.jpg)
![About](public/about.jpg)
![Prayer Time](public/prayer-time.jpg)

## Project Structure

```
├── frontend/          # React + TypeScript + Vite
├── backend/           # Laravel API
├── .deployment/       # Deployment scripts and guides
└── .htaccess          # Root routing configuration
```

## Features

- **Multi-language Support**: Oromo, English, Amharic, Arabic
- **Admin Dashboard**: Manage content, events, gallery, news, testimonials
- **Event Management**: Create and manage events with date and location
- **Gallery System**: Upload and organize images
- **Contact Form**: Receive messages from visitors
- **Responsive Design**: Mobile-friendly interface
- **PWA Support**: Progressive Web App capabilities

## Tech Stack

### Frontend
- React 18
- TypeScript
- Vite
- Tailwind CSS
- i18n for translations

### Backend
- Laravel 11
- MySQL
- Laravel Sanctum (Authentication)
- RESTful API

## Getting Started

### Local Development

#### Prerequisites
- Node.js 18+
- PHP 8.2+
- MySQL 8.0+
- Composer

#### Frontend Setup
```bash
cd frontend
npm install
npm run dev
```
Frontend runs on `http://localhost:8080`

#### Backend Setup
```bash
cd backend
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```
Backend runs on `http://localhost:8000`

## Production Deployment

### Frontend
```bash
npm run build --prefix frontend
```
Builds to `frontend/dist/`

### Backend
Deployed to `/public_html/api/` on cPanel

### Database
- Host: `localhost`
- Database: `oriasc_db`
- User: `oriasc_db`
- Password: `oriasc_db`

## Admin Credentials

- Email: `admin@oriasc.org`
- Password: `admin123`

## API Endpoints

### Public Endpoints
- `GET /api/health` - Health check
- `GET /api/announcements` - Get announcements
- `GET /api/contents` - Get content (news, events, projects)
- `GET /api/departments` - Get departments
- `GET /api/testimonials` - Get testimonials
- `GET /api/leaders` - Get leaders

### Admin Endpoints (Requires Authentication)
- `POST /api/login` - Admin login
- `POST /api/logout` - Admin logout
- `POST /api/contents` - Create content
- `PUT /api/contents/{id}` - Update content
- `DELETE /api/contents/{id}` - Delete content
- `POST /api/upload` - Upload files

## Environment Variables

### Frontend (.env)
```
VITE_API_URL=https://oriasc.org/api
```

### Backend (.env)
```
APP_ENV=production
APP_DEBUG=false
APP_URL=https://oriasc.org/api
DB_HOST=localhost
DB_DATABASE=oriasc_db
DB_USERNAME=oriasc_db
DB_PASSWORD=oriasc_db
FRONTEND_URL=https://oriasc.org
SANCTUM_STATEFUL_DOMAINS=oriasc.org,www.oriasc.org
```

## Deployment

### Via FTP
See `.deployment/PRODUCTION_DEPLOYMENT_GUIDE.md` for detailed instructions.

### Quick Deploy
1. Build frontend: `npm run build --prefix frontend`
2. Upload backend files to `/public_html/api/`
3. Upload frontend dist to `/public_html/`
4. Run migrations: `php artisan migrate --force`
5. Clear caches: `php artisan cache:clear`

## File Structure

### Frontend
```
frontend/
├── src/
│   ├── components/     # React components
│   ├── pages/          # Page components
│   ├── lib/            # Utilities and helpers
│   ├── services/       # API services
│   └── App.tsx         # Main app component
├── dist/               # Built files (production)
└── package.json
```

### Backend
```
backend/
├── app/
│   ├── Http/Controllers/Api/  # API controllers
│   ├── Models/                # Database models
│   └── Services/              # Business logic
├── database/
│   ├── migrations/            # Database migrations
│   └── seeders/               # Database seeders
├── routes/
│   └── api.php                # API routes
├── public/                    # Public files
└── .env                       # Environment config
```

## Troubleshooting

### Database Connection Issues
- Verify credentials in `.env`
- Check MySQL user permissions
- Ensure database exists

### API 500 Errors
- Check Laravel logs: `storage/logs/laravel.log`
- Verify database connection
- Clear caches: `php artisan cache:clear`

### Frontend Not Loading
- Clear browser cache
- Check `.htaccess` routing
- Verify frontend build: `npm run build`

## Support

For issues or questions, contact the development team.

## License

All rights reserved © 2024 Majlisa Oromiyaa
# oriasc
