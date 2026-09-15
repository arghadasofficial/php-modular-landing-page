Here is the updated `README.md` file with a new **Tutorial: How to Customize** section added right after the Setup instructions. This will help anyone who clones the repository understand exactly how to work with your modular architecture.

```markdown
# PHP Modular Landing Page Template

A lightweight, high-conversion PHP website architecture designed for rapid deployment of business and corporate landing pages. This project utilizes a strict component-based structure to guide visitors through a trust-building narrative, ending with a built-in lead capture system and administration dashboard.

## Key Features
*   **Narrative-Driven Layout:** Pre-structured to flow from introduction (Hero/About) to trust building (Founder/Ethics/Reviews) and finally conversion (CTA/Contact Form).
*   **Component-Based UI:** Every section of the page is isolated into its own file for rapid customization and clean code.
*   **Lead Management Dashboard:** Integrated, secure backend (`admin-panel.php`) to view and manage customer inquiries submitted via the frontend.
*   **Zero-Bloat Performance:** Built entirely with vanilla PHP and optimized assets, avoiding the heavy overhead of traditional CMS platforms.

## Page Flow & Structure
The primary `index.php` is composed of the following sequential modules:
1.  **Hero:** First impression and primary value proposition.
2.  **About:** Company overview and trust factors.
3.  **Founder & Ethics:** Humanizes the brand and establishes corporate credibility.
4.  **Products:** Highlights the flagship product followed by the general catalog.
5.  **Social Proof:** Customer reviews and testimonials.
6.  **Conversion:** Targeted Call-To-Action (CTA) and low-friction query form.

## Directory Layout
├── assets/          # Static files (CSS, JS, images)
├── components/      # Reusable UI sections (hero.php, founder.php, cta.php, etc.)
├── partials/        # Global layout wrappers (head.inc.php, nav.inc.php, foot.inc.php)
├── utils/           # Helper functions and database configuration (`db.php`)
├── admin-panel.php  # Backend dashboard for viewing submitted form queries
├── index.php        # Main modular landing page
└── .gitignore       # Git ignore rules

## Setup & Installation
1. Clone the repository to your local server environment:
```bash
   git clone [https://github.com/arghadasofficial/php-modular-landing-page.git](https://github.com/arghadasofficial/php-modular-landing-page.git)
```

2. Create a MySQL database and execute the following SQL to set up the lead capture table:
```sql
CREATE TABLE form_queries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    phone VARCHAR(50),
    subject VARCHAR(255),
    message TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

```

3. Update the database credentials inside `utils/db.php`.
4. Launch your local server and navigate to `http://localhost/php-modular-landing-page/index.php` to view the frontend.
5. Access the backend via `http://localhost/php-modular-landing-page/admin-panel.php`.

## Tutorial: How to Customize

**1. Editing Existing Sections**
To change the content or layout of a specific part of the website, navigate to the `components/` directory. For example, to update the main header text, open `components/hero.php` and modify the HTML inside.

**2. Adding a New Section**
Because the architecture is modular, adding new sections is simple:

* Create a new PHP file in the components folder (e.g., `components/faq.php`).
* Build your layout inside this new file.
* Open `index.php` and include your new section exactly where you want it to render:
```php
<!-- FAQ Section -->
<?php include 'components/faq.php'; ?>

```

**3. Managing Leads**
Once your site is live and visitors submit the form found in `components/query-form.php`, their data is securely saved to your database. Navigate to `/admin-panel.php` and log in to view a sortable table of all your customer inquiries.

## Maintainer

Developed and maintained by **Argha Das**.

```
