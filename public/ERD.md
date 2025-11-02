# Database Tables

## Owner Table
| Field      | Type      | Options       |
|------------|-----------|---------------|
| _id        | ObjectId  |               |
| username   | String    |{requied: true}|
| password   | String    |{requied: true}|

## Customer Table
| Field      | Type      | Options       |
|------------|-----------|---------------|
| _id        | ObjectId  |               |
| username   | String    |{requied: true}|
| password   | String    |{requied: true}|

## Apartment Table                                                  
| Field             | Type                | Options       |
|-------------------|---------------------|---------------|
| _id               | ObjectId            |               |
| ApartmentName     | String              |{requied: true}|
| ApartmentPrice    | Number              |{requied: true}|
| ApartmentDesc.    | String              |{requied: true}|
| ApartmentOffers   | String              |{requied: true}|
| ApartmentImg      | Array[imagesSchema] | Embedded      |
| ApartmentLocation | String              |{requied: true}|
| Owner             | ObjectId            |{requied: true}|

## Images Schema (Embedded)
| Field             | Type                | Options              |
|-------------------|---------------------|----------------------|
| url               | String              | Image URL            |
| cloudinary_id     | String              |Cloudinary storage ID |



## City Table
| Field         | Type      | Options       |
|---------------|-----------|---------------|
| _id           | ObjectId  |               |
| CityName      | String    |{requied: true}|




### Relationships
- **One-to-Many**: One City can have many Apartments, but each Apartment belongs to one City.
- **One-to-Many**: One Owner can have many Apartments, but each Apartment belongs to one Owner.