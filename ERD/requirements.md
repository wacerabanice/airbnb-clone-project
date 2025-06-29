### 🎨ERD (Entity-Relationship Diagram)

### Entities:

1. **User**
2. **Property**
3. **Booking**
4. **Payment**
5. **Review**
6. **Message**

### ERD Overview:

```plaintext
User (user_id PK)
 ├─< Property (host_id FK)
 ├─< Booking (user_id FK)
 ├─< Review (user_id FK)
 ├─< Message (sender_id, recipient_id FK)

Property (property_id PK)
 ├─< Booking (property_id FK)
 ├─< Review (property_id FK)

Booking (booking_id PK)
 ├─< Payment (booking_id FK)

