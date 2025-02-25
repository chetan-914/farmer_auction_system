# Farmer Auction Platform

A web-based auction platform connecting farmers directly with customers, allowing agricultural products to be sold through a transparent bidding system. This application enables farmers to showcase their products and customers to bid on fresh, local produce.

## 📋 Features

### For Farmers
- **Account Management**: Create and manage farmer profiles with details about their farm and experience
- **Product Management**: Add, edit, and delete agricultural products with details like quantity, quality, and harvest dates
- **Auction Management**: Create auctions for products with customizable start/end times and minimum bid prices
- **Dashboard**: Track active auctions, bids, and sales in a centralized dashboard
- **Transaction Tracking**: Monitor payments and completed sales

### For Customers
- **Browse Auctions**: View all active auctions with product details and current bid information
- **Bidding System**: Place bids on desired products with real-time validation
- **Dashboard**: Track participating auctions and won items
- **Transaction Management**: Complete payments for won auctions
- **Review System**: Rate and review transactions

## 🛠️ Technology Stack

- **Backend**: Python with Flask framework
- **Database**: MySQL with SQLAlchemy ORM
- **Frontend**: HTML templates with Tailwind CSS
- **Authentication**: Session-based authentication system

## 🗂️ Project Structure

```
farmer-auction/
├── app.py                 # Main application file with routes and controllers
├── models.py              # Database models and relationships
├── templates/             # HTML templates
│   ├── farmer/            # Farmer-specific templates
│   ├── customer/          # Customer-specific templates
│   └── ...                # Shared templates
├── README.md              # Project documentation
└── requirements.txt       # Python dependencies
```

## 🔧 Setup and Installation

### Prerequisites
- Python 3.7+
- MySQL Server
- pip (Python package manager)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/chetan-914/farmer_auction_system.git
   cd farmer-auction
   ```

2. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the database**
   - Create a MySQL database named `farmer_auction`
   - Update the database connection string in `app.py` if necessary:
     ```python
     app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://username:password@localhost:3306/farmer_auction'
     ```

5. **Initialize the database**
   ```bash
   # Run the following in a Python shell
   from app import app, db
   with app.app_context():
       db.create_all()
   ```

6. **Run the application**
   ```bash
   python app.py
   ```

7. **Access the application**
   - Open your browser and navigate to `http://localhost:5000`

## 🔐 Security Notes

- Update the secret key in `app.py` for production:
  ```python
  app.secret_key = 'your-secure-secret-key'
  ```
- Consider implementing password hashing before deployment (code is commented out but present in the project)

## 🌱 Database Schema

The application uses several interconnected tables:

- **Users**: Stores user accounts (both farmers and customers)
- **FarmerProfiles**: Extended information for farmer users
- **Categories**: Product categories with hierarchical structure
- **Products**: Agricultural products listed by farmers
- **Auctions**: Time-bound auctions for products
- **Bids**: Individual bids placed by customers
- **Transactions**: Completed sales after successful auctions
- **Reviews**: Feedback and ratings after transactions

## 📝 Development Notes

### Stored Procedures
The application utilizes several MySQL stored procedures:
- `get_all_active_auctions()`: Retrieves all currently active auctions
- `place_bid()`: Handles bid placement with validation
- `cancel_auction()`: Cancels an auction with appropriate checks
- `start_auction()`: Creates a new auction for a product

### User Types
- **Farmers**: Can list products and create auctions
- **Customers**: Can browse products and place bids

## 🚀 Future Enhancements

- Implement real-time bidding notifications
- Add product image upload functionality
- Create an admin dashboard for platform management
- Implement advanced search and filtering capabilities
- Add payment gateway integration
- Implement review page
- Modify payment templete
