# Database Tables

## Owner/Customer Table
| Field      | Type      | Options                                      |
|------------|-----------|----------------------------------------------|
| _id        | ObjectId  |                                              |
| username   | String    | {required: true}                             |
| password   | String    | {required: true}                             |
| role       | String    | {enum: ['Owner', 'Customer'], required: true}|

## Apartment Table                                                  
| Field             | Type                | Options                                     |
|-------------------|---------------------|---------------------------------------------|
| _id               | ObjectId            |                                             |
| ApartmentName     | String              | {required: true}                            |
| ApartmentPrice    | Number              | {required: true}                            |
| ApartmentDesc.    | String              | {required: true}                            |
| ApartmentOffering | String              | {required: true}                            |
| ApartmentImg      | Array[imagesSchema] | Embedded                                    |
| ApartmentCity     | String              | {enum: [all bahrain cites], required: true} |
| ApartmentRating   | Number              | {required: true}                            |
| BookingCalendar   | Array[Number]       | {default: Array(365)}                       |
| Owner             | ObjectId            | {required: true}                            |

## Images Schema (Embedded)
| Field             | Type                | Options              |
|-------------------|---------------------|----------------------|
| url               | String              | Image URL            |
| cloudinary_id     | String              | Cloudinary storage ID|

## City Table
| Field         | Type      | Options        |
|---------------|-----------|----------------|
| _id           | ObjectId  |                |
| CityName      | String    |{required: true}|



### Relationships
- **One-to-Many**: One City can have many Apartments, but each Apartment belongs to one City.
- **One-to-Many**: One Owner can have many Apartments, but each Apartment belongs to one Owner.