# Project Description:
The Rent Space Project is a user-friendly web application designed to showcase and manage a variety of rental spaces across different locations. This platform allows users to browse available spaces by location, view detailed descriptions and amenities, and facilitate an engaging booking experience for both renters and space owners.

**Welcome to Rent space, You can visit the web by following the link below:**
**[app link]()**

# App Features
1. **User Authentication**
    - Secure sign-up and login for space owners and renters
    - Role-based access control (owners vs. renters)
    - Token management and secure logout

2. **Advanced Space Management**
   - Add new rental spaces with detailed information
   - Edit and update space details, prices, and availability
   - Delete spaces from the platform
   - Multiple image uploads for each space

3. **Review & Rating System**
   - Owner response capability
   - Verified renter reviews only

4. **Cites Browsing** 
    - Users can explore apartments into various cites

5. **Detailed Apartment Views** 
    - Each Apartment features comprehensive details, including images, descriptions, and prices, to enhance the customer experience.

# User Stories:
1.**User Authentication**

    As a space owner, I want to sign up and log in securely so that I can manage my rental properties without unauthorized access.
    
    As a renter, I want to create an account and log in securely so that I can book spaces and manage my reservations.

2.**Browse Apartments**

    As a user, I want to browse spaces by location, price range, and dates so that I can easily find available properties that match my needs.
    
    As a user, I want to filter spaces by amenities and property type so that I can find spaces with specific features I require.

3.**View Apartment Details**

    As a user, I want to view comprehensive space details including photos, amenities, pricing, and availability so that I can make informed booking decisions.
    
    As a user, I want to see customer reviews and ratings for spaces so that I can assess the quality and reliability of the rental.

4.**Add New Apartments**

    As a space owner, I want to add new rental spaces to the platform with detailed information and multiple photos so that I can attract potential renters.

5.**Edit Existing Apartments**

    As a space owner, I want to edit space details, update pricing, and modify availability calendars so that my listings remain accurate and current.

6.**Delete Apartments**

    As a space owner, I want to remove spaces from the platform so that I can manage properties that are no longer available for rent.

7.**Manage Bookings**

    As a renter, I want to book available spaces and view my booking history so that I can manage my travel plans.


# Pseudocode:

* **User Authentication Functions**
    ```
        1. signUp(username, password)
            Steps:
            Check if the username already exists in the database.
            If it does, return a message indicating the username is taken.
            If not, hash the password for security.
            Save the new admin information (username and hashed password) to the database.
            Return a success message.
            logIn(username, password)

        2. logIn(username, password)
            Steps:
            Retrieve the admin from the database using the provided username.
            If the admin does not exist, return a "admin not found" message.
            If the admin exists, check the provided password against the stored hashed password.
            If the password matches, create a admin session and return a success message.
            If the password does not match, return an "Incorrect password" message.

        3. verifyToken(token)
            Steps:
            Extract token from request header.
            Verify JWT token signature and expiration.
            If valid, extract user payload and attach to request.
            If invalid, return "Unauthorized access" error.
    ```

* **Apartments Management Functions**
    ````
        1. addSpace(spaceData, ownerId)
            Steps:
            Validate space data (name, price, location, description, amenities).
            Create space object with provided details and owner ID.
            Upload space images to cloud storage.
            Save space object to database with availability calendar.
            Return created space with ID.

        2. editSpace(spaceId, updatedFields, ownerId)
            Steps:
            Verify space exists and belongs to owner using ownerId.
            If not authorized, return "Access denied" error.
            Update space with new fields provided.
            If images updated, handle image upload/replacement.
            Save updated space to database.
            Return updated space object.

        3. deleteSpace(spaceId, ownerId)
            Steps:
            Verify space exists and belongs to owner using ownerId.
            If not authorized, return "Access denied" error.
            Remove space from database.
            Clean up associated images from storage.
            Return success message.

        4. getOwnerSpaces(ownerId)
            Steps:
            Fetch all spaces from database where owner = ownerId.
            Include booking statistics and revenue data.
            Return spaces list with analytics.
    ````

* **Booking Apartments Functions**
    ````
        1. createBooking(spaceId, customerId, checkInDate, duration)
            Steps:
            Verify space availability for requested dates.
            If available, create booking object with:
              - spaceId, customerId, checkInDate, checkOutDate
              - total price, booking status: "confirmed"
            Update space availability calendar.
            Save booking to database.
            Send confirmation notification.
            Return booking details with confirmation.

        2. getCustomerBookings(customerId)
            Steps:
            Fetch all bookings for customer from database.
            Include space details and booking status.
            Return bookings list.

        3. cancelBooking(bookingId, customerId)
            Steps:
            Verify booking exists and belongs to customer.
            If within cancellation period, update booking status to "cancelled".
            Update space availability calendar.
            Process refund if applicable.
            Return cancellation confirmation.
    ````

* **Review & Rating Functions**
    ````
        1. createReview(spaceId, customerId, bookingId, rating, comment)
            Steps:
            Verify customer has completed booking (checked out).
            If not completed, return "Review not allowed" error.
            Create review object with rating and comment.
            Calculate new average rating for space.
            Save review to database.
            Update space average rating.
            Return created review.

        2. getSpaceReviews(spaceId)
            Steps:
            Fetch all approved reviews for space from database.
            Include customer information and booking date.
            Calculate average rating and rating distribution.
            Return reviews with statistics.

        3. getCustomerReviews(customerId)
            Steps:
            Fetch all reviews written by customer.
            Include space details and review status.
            Return customer's review history.
    ````

# Useful pics:

### Home page:
![home page]()