# airbnb-clone-project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. This is a project built as part of my learning roadmap, developed as a hands-on project to learn and demonstrate core web development and data engineering skills.



## 🚀 Project Goals

- Recreate key features of Airbnb: user login, property listings, booking system
- Practice full-stack development, data pipelines, and deployment
- Build a real-world project to showcase in portfolio

## 🛠 Tech Stack

### Frontend:
- HTML, CSS, JavaScript
- React.js

### Backend:
- Node.js + Express OR Python + Flask/Django
- MongoDB or PostgreSQL

### Tools:
- Git, GitHub
- Docker
- Render, Netlify, or Railway (deployment)
- API integrations (e.g., Google Maps, Stripe)

-------------------------------------------------------
## 👥 Team Roles
A summary of each role and their responsibility in the project:

### 🔐Business analyst (BA)
- Understands customer’s business processes
- Translates customer business needs into requirements

### 🧠 Product owner (PO)
- Holds responsibility for a product vision and evolution
- Makes sure the final product meets customer requirements

### Project manager (PM)
- Makes sure a product or its part is delivered on time and within budget
- Manages and motivates the software development team

### 🎨 UI/UX designer
- Transforms a product vision into user-friendly designs
- Creates user journeys for the best user experience and highest conversion rates

 ### 🖥️ Software architect
- Designs a high-level software architecture
- Selects appropriate tools and platforms to implement the product vision
- Sets up code quality standards and performs code reviews

### 🛠️ Software developer
- Engineers and stabilizes the product
- Solves any technical problems emerging during the development lifecycle

###  🧪 Quality assurance (QA) engineer
- Makes sure an application performs according to requirements
- Spots functional and non-functional defects

###  🧪 Test automation engineer
- Designs a test automation ecosystem
- Writes and maintains test scripts for automated testing

###  🗃️ DevOps engineer
- Facilitates cooperation between development and operations teams
- Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery

---------------------------------------------
## 🧰 Technology Stack

### 🌐 Frontend - Structure and style the layout of the website
- **HTML5 & CSS3**  
- **JavaScript (ES6+)**  
- **React.js**  
  
### 🧪 Backend - runtime that lets you run JavaScript server-side. Express is a minimalist framework for creating RESTful APIs.In addition, used for rapid development and clean, secure architecture. While Restful APIs enable communication between the frontend and backend — used for listing properties, user authentication, and bookings.

- **Node.js + Express.js** *(OR Python + Django)*  
- **RESTful API** 
- **GraphQL**

### 🗄️ Database & Storage - storing of data 

- **MongoDB** *(OR PostgreSQL)*  
 - **Cloudinary or Amazon S3** *(Optional)*  
 
### ⚙️ DevOps & Deployment

- **Git & GitHub**   - Version control and collaboration
- **Render / Railway / Netlify**  - Hosting platforms for deploying the frontend, backend, and database. Simplifies CI/CD 
  - **Docker** - containerize the application, making development and deployment more consistent

### 📊 Analytics & Monitoring *(Optional)* - Track user behavior and performance metrics

- **Google Analytics / LogRocket**  
  Track user behavior and performance metrics.

  --------------------------------
  ## 🗃️ Database Design

This section outlines the key data entities in the Airbnb Clone application and how they relate to each other.

### 🔐 Users
Represents both property owners (hosts) and renters (guests).

**Fields:**
- `id`: Unique identifier
- `name`: Full name of the user
- `email`: Email address (used for login)
- `password_hash`: Encrypted password
- `role`: Enum value (`host`, `guest`, or both)

**Relationships:**
- A user can list multiple properties (host)
- A user can make multiple bookings (guest)
- A user can write multiple reviews


### 🏡 Properties
Represents listings created by hosts.

**Fields:**
- `id`: Unique identifier
- `title`: Property title (e.g., "Modern Apartment in Accra")
- `description`: Full description of the property
- `location`: Address or coordinates
- `price_per_night`: Cost of booking per night
- `host_id`: Foreign key referencing `Users.id`

**Relationships:**
- Each property is owned by one user (host)
- A property can have many bookings
- A property can have many reviews


### 📅 Bookings
Represents a reservation made by a guest.

**Fields:**
- `id`: Unique identifier
- `guest_id`: Foreign key referencing `Users.id`
- `property_id`: Foreign key referencing `Properties.id`
- `check_in_date`: Start date of booking
- `check_out_date`: End date of booking
- `total_price`: Calculated total cost

**Relationships:**
- A booking is linked to one user (guest)
- A booking is linked to one property


### 📝 Reviews
Feedback from guests about a property.

**Fields:**
- `id`: Unique identifier
- `guest_id`: Foreign key referencing `Users.id`
- `property_id`: Foreign key referencing `Properties.id`
- `rating`: Numeric score (e.g., 1–5 stars)
- `comment`: Written feedback
- `created_at`: Timestamp

**Relationships:**
- A user can leave one review per booking
- A property can have many reviews

### 💳 Payments
Tracks the financial transactions for bookings.

**Fields:**
- `id`: Unique identifier
- `booking_id`: Foreign key referencing `Bookings.id`
- `payment_date`: Date of transaction
- `amount`: Amount paid
- `status`: Payment status (`pending`, `completed`, `failed`)

**Relationships:**
- Each payment is linked to one booking
- Each booking can have one associated payment

### 🔄 Entity Relationships Summary

- **Users** (1) ↔ (Many) **Properties**  
- **Users** (1) ↔ (Many) **Bookings**  
- **Properties** (1) ↔ (Many) **Bookings**  
- **Properties** (1) ↔ (Many) **Reviews**  
- **Users** (1) ↔ (Many) **Reviews**  
- **Bookings** (1) ↔ (1) **Payments**

