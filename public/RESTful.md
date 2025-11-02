| HTTP Method | Path/Endpoint | CRUD Operation | Route Name | Purpose | Render/Redirect Action |
|-------------|---------------|----------------|------------|---------|------------------------|
| GET | `/` | Read | home | Display home page with cities/villages and featured apartments | `res.render('home')` |
| GET | `/apartments` | Read | index | Display full list of apartments (owner's view) | `res.render('apartments/index')` |
| GET | `/apartments/city/:cityId` | Read | cityApartments | Display apartments by specific city/village | `res.render('apartments/city')` |
| GET | `/apartments/:apartmentId` | Read | show | Display apartment details with booking form | `res.render('apartments/show')` |
| GET | `/apartments/new` | None | new | Render form to add new apartment | `res.render('apartments/new')` |
| GET | `/apartments/:apartmentId/edit` | None | edit | Render form to edit existing apartment | `res.render('apartments/edit')` |
| POST | `/apartments` | Create | create | Handle new apartment form submission | `res.redirect('/apartments/:apartmentId')` |
| PUT | `/apartments/:apartmentId` | Update | update | Handle apartment edit form submission | `res.redirect('/apartments/:apartmentId')` |
| DELETE | `/apartments/:apartmentId` | Delete | destroy | Handle apartment deletion | `res.redirect('/apartments')` |
| GET | `/cities` | Read | cities | Display cities page with ratings and prices | `res.render('cities/index')` |
| GET | `/favorites` | Read | favorites | Display user's favorite apartments | `res.render('favorites/index')` |
| POST | `/favorites/:apartmentId` | Create | addFavorite | Add apartment to favorites | `res.redirect('/favorites')` |
| DELETE | `/favorites/:apartmentId` | Delete | removeFavorite | Remove apartment from favorites | `res.redirect('/favorites')` |
| GET | `/bookings` | Read | bookings | Display user's booking list | `res.render('bookings/index')` |
| POST | `/bookings/:apartmentId` | Create | createBooking | Handle booking form submission | `res.redirect('/bookings')` |
| GET | `/auth/signin` | None | signin | Render sign in form | `res.render('auth/signin')` |
| POST | `/auth/signin` | None | login | Handle sign in form submission | `res.redirect('/')` |
| GET | `/auth/signup` | None | signup | Render sign up form | `res.render('auth/signup')` |
| POST | `/auth/signup` | Create | register | Handle sign up form submission | `res.redirect('/')` |

## Page to Route Mapping

### Authentication Pages
- **Sign In Form** → `GET /auth/signin`
- **Sign Up Form** → `GET /auth/signup`

### Main Application Pages
- **Home Page** → `GET /`
- **Cities Page** → `GET /cities`
- **Favorites Page** → `GET /favorites`
- **Booking List** → `GET /bookings`

### Apartment Management
- **Owner Apartments Page** → `GET /apartments`
- **Add Apartment Form** → `GET /apartments/new`
- **Edit Apartment Form** → `GET /apartments/:apartmentId/edit`
- **Apartment Details + Booking Form** → `GET /apartments/:apartmentId`

### City Navigation
- **City/Village Links on Home** → `GET /apartments/city/:cityId`