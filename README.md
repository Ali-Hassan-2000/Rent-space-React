# Rent Space
Rent Space is a modern web application designed to help users browse, list, and book a variety of rentable spaces such as rooms, offices, studios, workspaces, and more. The platform connects space owners with renters through a smooth, intuitive, and user-friendly online experience.

## Overview
Rent Space is a full-stack, web-based application that simplifies finding and managing rentable spaces. The platform allows users to:
- Browse a diverse catalog of available spaces  
- View detailed information about each listing  
- Book spaces with ease  
- Manage bookings and owned spaces  
- Enjoy a clean, responsive, and accessible browsing experience

[Front-end repo (React)](https://github.com/Ali-Hassan-2000/Rent-space-FrontEnd)

[Back-end repo](https://github.com/Ali-Hassan-2000/Rent-space-BackEnd)
  
[Web link](https://rent-space-front-end.vercel.app/)
![main page]()

## Table of Contents
- [Features](#features) 
- [Usage Instructions](#usage-instructions)
- [Functions Overview](#functions-overview)
- [Technologies Used](#technologies-used)
- [Planned Future Enhancements](#planned-future-enhancements)
- [References](#references)

## Features
- Browse and explore various rentable spaces
- Filter spaces by cities
- View detailed descriptions, pricing, and images  
- Create and manage bookings  
- Space owners can add, edit, and delete their space listings  
- Responsive and user-friendly interface  

## Usage Instructions
- **Browse Apartmets:** Navigate through available spaces and explore cities.  
- **View Details:** Click on any space to see more details such as price, description, and images.  
- **Book a Space:** Select a date range and submit a booking request (for authenticated users).   
- **Manage Apartments (Owners):** Create, edit, and delete your space listings through your dashboard.  
- **Return to Home:** Use the main navigation to quickly return to the home page.

## Functions Overview

### `browseSpaces()`
Fetches and displays a list of all available spaces from the backend API.

### `filterByCity(Id)`
Filters spaces based on the selected city.

### `viewSpaceDetails(Id)`
Retrieves and shows detailed information about a selected space.

### `createSpace(spaceData, images)`
Allows owners to add a new space with information and images uploaded to Cloudinary.

### `deleteSpace(Id)`
Deletes a space from the database and removes associated media.

### `updateSpace(Id, updatedData, newImages)`
Updates an existing spaces details and replaces old images if new ones are uploaded.

### `getCities()`
Retrieves all cities for filters and navigation menus.

### `createBooking(bookingData)`
Handles booking creation for users selecting a space and date range.

### `renderErrorPage(errorMessage)`
Displays a clear, user-friendly error message in case of issues or failed requests.

## Technologies Used
- **JavaScript** – Main application logic  
- **HTML** – Structure and layout  
- **CSS** – Styling and interface design  
- **React / Node.js / Express** (modify according to your actual stack)  
- **Cloudinary** – Image storage  
- **Git / GitHub** – Version control  

## Planned Future Enhancements
Here are some planned future enhancements for the Rent Space app:


1. **Advanced Search & Filters**  
   Add filters for price range, location, availability calendar, and more.

2. **Owner Dashboard 2.0**  
   Build analytics for owners (booking stats, revenue insights, etc.).

3. **Mobile App Version**  
   Develop a mobile-friendly downloadable app for both owners and renters.

4. **User Reviews & Ratings**  
   Allow users to leave feedback for spaces they have booked.

5. **Payment Integration**  
   Add automated checkout and payment processing for bookings.

## References
- [1] [Atlas DataBase (mongodb)](https://www.mongodb.com/products/platform/atlas-database) MongoDB Atlas is a fully managed cloud database service that simplifies the deployment.
- [2] [Cloudinary cloud storage](https://cloudinary.com/) Cloudinary is a powerful media management platform that provides image and video upload.
- [3] [Heroku internet server](https://dashboard.heroku.com/) Heroku is a cloud platform that enables developers to build, run, and operate applications entirely in the cloud.
- [4] [Vercel](https://vercel.com/) Vercel is a cloud platform that enables developers to build, run, and operate applications entirely in the cloud (works great with React).

