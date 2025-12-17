# Small Notes Application

## Introduction
This repository contains a small technical assessment project setup.

You will work with the VILT stack including **Laravel**, **Inertia.js**, **Vue**, and **Tailwind CSS**.  
The focus is on clean code, clear structure, and a reasonable user experience rather than on building a fully production-ready application.

## Task Description
The full task description, including requirements and optional bonus objectives, can be found here:

👉 **[TASK.md](./TASK.md)**

Please read the task carefully before starting your implementation.

## Notes
- The expected implementation time is approximately **30–60 minutes**.
- Candidates are encouraged to commit their work regularly using **git** in a fresh, personal repository to demonstrate their development process.
- After completion, please send your **public GitHub repository URL** (or grant access via invitation) to:  
  **daniel.rossburg@semasystems.de**
- Feel free to document any assumptions or decisions either in this README or directly in your code where appropriate.

## Technical Setup

### Requirements
- Docker
- Git

### Configure Sail Shell Alias
https://laravel.com/docs/12.x/sail#configuring-a-shell-alias

### Setup

1. Duplicate the `.env.example` file and rename it to `.env`.

2. Install Composer dependencies via Docker
```bash
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php84-composer:latest \
    composer install --ignore-platform-reqs
```

3. Start the containers
```bash
sail up -d
```

4. Install Node dependencies.
 ```bash
 sail npm ci
 ```

5. Run Migrations + Seeders
```bash
sail artisan migrate
```

6. Start the vite development server.
```bash
sail npm run dev
```

The application will be accessible at http://localhost. Have fun! :)
