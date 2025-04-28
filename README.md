# Landing Page Maintenance Guide

This guide will help you maintain and customize the Computerbril landing page. Whether you're new to web development or need a quick reference, follow these instructions to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains your logo and navigation menu. To update:

```html
<!-- Logo Text -->
<div class="text-2xl font-bold text-blue-600">Computerbril</div>
```
- To change the logo text, replace "Computerbril" with your desired text
- To modify logo size, change `text-2xl` to `text-xl` (smaller) or `text-3xl` (larger)

### Hero Section
Located at the top of the page with the main heading and CTA button:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-6">
    Computerbril Arbowet
</h1>
<p class="text-xl md:text-2xl text-blue-600 font-semibold mb-8">
    Tijdelijk 20% Korting - Nog maar enkele dagen geldig!
</p>
```

To update:
1. Change heading text between the `<h1>` tags
2. Modify promotional text in the `<p>` tag
3. Responsive text sizes use this pattern:
   - `text-4xl`: Mobile devices
   - `md:text-5xl`: Medium screens
   - `lg:text-6xl`: Large screens

### Features Section
Each feature card follows this structure:

```html
<div class="p-8 rounded-xl bg-gray-50 hover:shadow-xl transition-shadow duration-300">
    <div class="text-blue-600 mb-4">
        <!-- SVG icon here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Arbowet Gecertificeerd</h3>
    <p class="text-gray-600">Voldoet aan alle wettelijke eisen voor beeldschermwerk</p>
</div>
```

To add a new feature:
1. Copy the entire `<div>` block
2. Paste it within the `grid` container
3. Update the heading and description text
4. Maintain the existing classes for consistent styling

## Fixing Broken Links

### Navigation Menu Links
Current navigation links are:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Voordelen</a>
    <a href="#benefits" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Benefits</a>
    <a href="#faq" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">FAQ</a>
    <a href="#contact" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Contact</a>
</div>
```

To update links:
1. For internal page sections, use `#section-id`
2. For external links, use the full URL: `https://example.com`
3. Update the text between `<a>` tags to match your navigation labels

### CTA Button Links
The main call-to-action buttons currently point to:
```html
<a href="https://computerbril.org/winkel" class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-semibold px-8 py-4 rounded-lg">
```

To update:
1. Replace `https://computerbril.org/winkel` with your shop URL
2. Ensure the URL includes `https://` for secure links

## Linking Privacy and Terms Pages

### Adding Footer Links
Add privacy and terms links to the footer section:

```html
<div class="border-t border-gray-800 mt-12 pt-8 text-sm text-gray-400">
    <p>&copy; 2024 Computerbril. Alle rechten voorbehouden.</p>
    <!-- Add this block -->
    <div class="mt-4 space-x-4">
        <a href="/privacy.html" class="hover:text-white transition-colors duration-300">Privacy Policy</a>
        <a href="/terms.html" class="hover:text-white transition-colors duration-300">Terms of Service</a>
    </div>
</div>
```

### Creating Policy Pages
1. Create two new files in your root directory:
   - `privacy.html`
   - `terms.html`
2. Use the same header and footer as `index.html`
3. Maintain consistent styling using Tailwind classes

## Troubleshooting

Common issues and solutions:

### Broken Styles
If Tailwind classes aren't working:
1. Check if the Tailwind CSS CDN link is present in the `<head>`:
```html
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
```
2. Verify there are no typos in class names
3. Ensure classes are space-separated

### Mobile Menu Issues
If the mobile menu isn't working:
1. Verify Alpine.js is loaded:
```html
<script defer src="https://unpkg.com/alpinejs@3.x.x/dist/cdn.min.js"></script>
```
2. Check that `x-data` and `@click` directives are present in the header

### Links Not Working
1. Verify that section IDs match the href attributes
2. Ensure external URLs include `https://`
3. Check for proper quotation marks around href values

Remember to test all changes across different devices and browsers before publishing updates to your live site.