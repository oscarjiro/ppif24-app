# PPIF 2024

![PPIF 2024 logo](public/ppif/images/Logo_UMN_PPIF.png)

The official website for **Perkenalan Prodi Informatika (PPIF) 2024**, part of the new-student orientation at **Universitas Multimedia Nusantara (UMN)**, organized by the Informatics student association.

**Theme:** *Express Yourself with Technology*  
**My role:** Lead developer  
**Status:** Completed event project (2024), preserved as a portfolio reference

## What we built

A custom event website with an interactive 3D landing page, event information, and a puzzle experience for incoming students.

- **3D landing page:** An animated PPIF logo built with Three.js / React Three Fiber, with lighting and bloom effects.
- **Event information:** Introductions to the Informatics program and PPIF, image galleries, and an interactive event timeline.
- **Responsive experience:** Custom navigation, transitions, and layouts for desktop and mobile.
- **Cyber City game:** A story-driven puzzle where teams enter a secret code, unlock an encrypted message, and submit their answer to reveal their group name.
- **Backend validation:** Laravel endpoints validate team codes and puzzle answers against a database.

The game was built for the 2024 event, so its content and access codes are historical rather than an ongoing service.

## Tech stack

| Area | Technologies |
| --- | --- |
| Backend | PHP 8.2+, Laravel 11, MySQL |
| Frontend | React 18, Inertia.js, Tailwind CSS |
| 3D and effects | Three.js, React Three Fiber, Drei, React Three Postprocessing |
| Build tools | Vite |
| Other UI | Headless UI, Heroicons, React Toastify |

## Project structure

- `resources/js/Pages/`: Main site, game story, and game archives screens
- `resources/js/Components/ppif/`: 3D landing page, animations, timeline, galleries, and game UI
- `app/Http/Controllers/GroupNameController.php`: Puzzle code and answer validation
- `routes/web.php` and `routes/api.php`: Website and game endpoints
- `database/seeders/`: Original team/puzzle sample data
- `public/ppif/`: Images, icons, and 3D assets

## Running locally

This is the original 2024 codebase. A fresh setup has not been verified against newer dependencies.

You'll need PHP, Composer, Node.js/npm, and a local MySQL database.

```bash
git clone https://github.com/oscarjiro/ppif24-app.git
cd ppif24-app
composer install
npm install
cp .env.example .env
php artisan key:generate
```

Set up a local database and configure the `DB_*` values in `.env`, then run:

```bash
php artisan migrate --seed
php artisan serve
```

In another terminal:

```bash
npm run dev
```

Open `http://localhost:8000`. The `--seed` option loads the original group/puzzle data for local use.

**Deployment note:** The repository includes an old GitHub Actions deployment workflow at `.github/workflows/github-deploy.yml`. It contains destructive database reset and application-key regeneration commands. Do not enable or reuse that workflow against a real server without reviewing and replacing those steps. Old environment files in the repository must not be reused as credentials.

## Credits

Developed for **PPIF 2024 at Universitas Multimedia Nusantara**.  
**Lead developer:** Oscar Jiro

---

*This repository documents the finished 2024 event project. It is preserved for its design, implementation, and development history.*
