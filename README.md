# JobFinder - Job Search Web Application

This project is a job search web application built with HTML and Tailwind CSS. It's structured as a set of modular components that can be reused throughout the application.

## Project Structure

The project is broken down into the following components:

```
jobfinder/
│
├── index.html           # Main entry point that includes all components
├── components/
│   ├── navbar.html      # Navigation bar component
│   ├── footer.html      # Footer component
│   ├── job-filter.html  # Job filtering component
│   └── job-card.html    # Individual job listing card
└── README.md            # This documentation
```

## Components Overview

### 1. Navbar Component (`navbar.html`)

The navbar is positioned at the top of the page and includes:
- JobFinder logo/brand name
- Navigation links (Home and Favorites)
- A notification badge on the Favorites link showing the count of saved jobs

**Features:**
- Responsive design
- Gradient background from blue-600 to blue-800
- Hover effects on navigation links
- Badge indicator for favorites count

**Code:**
```html
<!-- navbar.html -->
<nav class="bg-gradient-to-r from-blue-600 to-blue-800 shadow-lg">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16 items-center">
      <a href="/" class="text-white font-bold text-2xl tracking-tight">JobFinder</a>
      <div class="flex space-x-4">
        <a
          href="/"
          class="text-gray-100 hover:bg-blue-700 px-3 py-2 rounded-md transition duration-200 ease-in-out font-medium"
        >
          Home
        </a>
        <a
          href="/favorite"
          class="text-gray-100 hover:bg-blue-700 px-3 py-2 rounded-md transition duration-200 ease-in-out font-medium flex items-center"
        >
          Favorites
          <span
            class="ml-2 bg-red-500 text-white text-xs px-2 py-1 rounded-full"
          >
            2
          </span>
        </a>
      </div>
    </div>
  </div>
</nav>
```

### 2. Footer Component (`footer.html`)

The footer appears at the bottom of the page and includes:
- Brand information
- Site navigation links
- Copyright information

**Features:**
- Responsive layout that changes from column to row on medium screens
- Dark background color (gray-800)
- Hover effects on navigation links

**Code:**
```html
<!-- footer.html -->
<footer class="bg-gray-800 text-white py-6 mt-8">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex flex-col md:flex-row justify-between items-center">
      <div class="mb-4 md:mb-0">
        <span class="font-bold text-xl">JobFinder</span>
        <p class="text-gray-400 text-sm mt-1">
          Find your dream job today
        </p>
      </div>
      <ul class="flex space-x-6">
        <li>
          <a href="#" class="text-gray-300 hover:text-white transition">About</a>
        </li>
        <li>
          <a href="#" class="text-gray-300 hover:text-white transition">Contact</a>
        </li>
        <li>
          <a href="#" class="text-gray-300 hover:text-white transition">Privacy</a>
        </li>
        <li>
          <a href="#" class="text-gray-300 hover:text-white transition">Terms</a>
        </li>
      </ul>
    </div>
  </div>
</footer>
```

### 3. Job Filter Component (`job-filter.html`)

This component allows users to filter job listings based on various criteria:
- Category (Frontend, Backend, Fullstack)
- Location
- Minimum Salary

**Features:**
- Responsive grid layout (1 column on small screens, 2 columns on medium screens, 3 columns on large screens)
- Form controls with focus states
- Clear filters button

**Code:**
```html
<!-- job-filter.html -->
<div class="bg-white rounded-lg shadow-md p-6 mb-8">
  <h3 class="text-lg font-medium mb-4 text-gray-700 border-b pb-2">
    Filter Jobs
  </h3>
  <div class="grid gap-6 md:grid-cols-3 sm:grid-cols-2 grid-cols-1">
    <div>
      <label
        htmlFor="category"
        class="block text-sm font-medium text-gray-700 mb-1"
      >
        Category
      </label>
      <select
        name="category"
        id="category"
        class="w-full border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 bg-white shadow-sm"
      >
        <option value="">All Categories</option>
        <option value="Frontend">Frontend</option>
        <option value="Backend">Backend</option>
        <option value="Fullstack">Fullstack</option>
      </select>
    </div>

    <div>
      <label
        htmlFor="location"
        class="block text-sm font-medium text-gray-700 mb-1"
      >
        Location
      </label>
      <select
        name="location"
        id="location"
        class="w-full border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 bg-white shadow-sm"
      >
        <option value="">All Locations</option>
        <option value="Dharan">Dharan</option>
        <option value="Itahari">Itahari</option>
        <option value="Biratnagar">Biratnagar</option>
      </select>
    </div>

    <div>
      <label
        htmlFor="minSalary"
        class="block text-sm font-medium text-gray-700 mb-1"
      >
        Min Salary
      </label>
      <input
        type="number"
        name="minSalary"
        id="minSalary"
        placeholder="e.g. 90000"
        class="w-full border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-blue-500 shadow-sm"
      />
    </div>
  </div>
  <div class="mt-4 flex justify-end">
    <button
      class="bg-gray-100 hover:bg-gray-200 text-gray-700 font-medium py-2 px-4 rounded-md transition duration-200 shadow-sm border border-gray-300"
    >
      Clear Filters
    </button>
  </div>
</div>
```

### 4. Job Card Component (`job-card.html`)

Each job card represents a single job listing and includes:
- Company logo and name
- Job title
- Location information with icon
- Salary range with icon
- Job category tag
- Favorite/bookmark button

**Features:**
- Hover animation (slight upward movement and shadow increase)
- Organized information layout
- Visual separation of header and content
- Interactive favorite button
- Category tag with appropriate styling

**Code:**
```html
<!-- job-card.html -->
<div
  class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition transform hover:-translate-y-1 duration-200 h-full flex flex-col"
>
  <div
    class="p-4 bg-gray-50 flex justify-between items-center border-b"
  >
    <div class="flex items-center">
      <img
        src="https://png.pngtree.com/png-vector/20190304/ourmid/pngtree-growth-business-company-logo-png-image_728232.jpg"
        alt="company image"
        class="w-10 h-10 object-contain rounded bg-white p-1 border border-gray-200"
      />
      <span class="ml-2 font-medium text-gray-600">Vishwa Adarsh</span>
    </div>
    <button class="text-2xl focus:outline-none">
      <span class="text-amber-500 hover:text-amber-400"> ★ </span>
    </button>
  </div>
  <a href="/" class="p-4 flex-1 flex flex-col">
    <h3 class="text-lg font-semibold text-blue-800 mb-1">
      Frontend Developer
    </h3>
    <div class="text-gray-500 mb-2 flex items-center">
      <svg
        class="w-4 h-4 mr-1"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          strokeWidth="2"
          d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"
        ></path>
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          strokeWidth="2"
          d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"
        ></path>
      </svg>
      Dharan
    </div>
    <div class="text-green-700 font-medium mb-3">
      <svg
        class="w-4 h-4 inline mr-1"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          strokeLinecap="round"
          strokeLinejoin="round"
          strokeWidth="2"
          d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
        ></path>
      </svg>
      Rs. 20000 to Rs. 40000
    </div>
    <div class="mt-auto pt-2">
      <span
        class="inline-block bg-blue-100 text-blue-800 text-xs px-2 py-1 rounded font-medium"
      >
        Frontend
      </span>
    </div>
  </a>
</div>
```

### 5. Main Structure (`index.html`)

The main HTML file shows how to combine all components:

**Code:**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://unpkg.com/@tailwindcss/browser@4"></script>
    <title>JobFinder</title>
  </head>
  <body>
    <div class="min-h-screen bg-gray-50 flex flex-col">
      <!-- Include navbar.html here -->
      <nav class="bg-gradient-to-r from-blue-600 to-blue-800 shadow-lg">
        <!-- Navbar content here -->
      </nav>
      
      <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full flex-1 py-8">
        <div>
          <h1 class="text-4xl font-bold text-center mb-8 text-gray-800">
            Find Your Dream Job
          </h1>
          
          <!-- Include job-filter.html here -->
          <div class="bg-white rounded-lg shadow-md p-6 mb-8">
            <!-- Job filter content here -->
          </div>
          
          <div class="grid gap-6 lg:grid-cols-3 md:grid-cols-2 grid-cols-1">
            <!-- Include job-card.html here (multiple times) -->
            <div class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition transform hover:-translate-y-1 duration-200 h-full flex flex-col">
              <!-- Job card content here -->
            </div>
            <!-- More job cards... -->
          </div>
        </div>
      </main>
      
      <!-- Include footer.html here -->
      <footer class="bg-gray-800 text-white py-6 mt-8">
        <!-- Footer content here -->
      </footer>
    </div>
  </body>
</html>
```


