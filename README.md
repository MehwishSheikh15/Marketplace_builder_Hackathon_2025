
# Comforty: A Modern E-Commerce Platform

## Overview
Comforty is a sleek, responsive, and feature-rich e-commerce platform developed as part of the **Governor Sindh Initiative AI Course Hackathon**. It leverages modern technologies to deliver an intuitive shopping experience for users and an efficient management system for admins.

## Features
### User Features
- **Authentication**: Secure login and signup with Firebase Authentication.
- **Product Catalog**: Browse products with filtering and sorting options.
- **Cart and Checkout**: Add products to the cart, calculate shipping, and make payments.
- **Order Tracking**: View order history and track shipments in real-time.
### Admin Features
- **Product Management**: Add, update, or delete products.
- **Order Management**: View and update order statuses.
- **User Management**: Block/unblock users and reset passwords.
- **Analytics Dashboard**: Monitor sales and user activity.

## Technology Stack
### Frontend
- **Next.js**: Framework for server-side rendering and static site generation.
- **Tailwind CSS**: Utility-first CSS framework for responsive design.

### Backend
- **Sanity CMS**: Content management for product and promotional data.
- **Next.js API Routes**: Custom backend for business logic.
  
 ### Third-Party Integrations
- **Payments**: EasyPaisa, JazzCash, HBL.
- **Shipping**: ShipEngine for real-time rates, labels, and tracking.
- **Hosting**: Vercel for deployment.

## Database Schema
### Sanity CMS Schema
#### Product Schema
```javascript
export default {
  name: 'product',
  type: 'document',
  title: 'Product',fields: [
    { name: 'title', type: 'string', title: 'Title' },
    { name: 'description', type: 'text', title: 'Description' },
    { name: 'price', type: 'number', title: 'Price' },
    { name: 'category', type: 'reference', to: [{ type: 'category' }], title: 'Category' },
    { name: 'image', type: 'image', title: 'Image' },
    { name: 'stock', type: 'number', title: 'Stock' },
  ],
};
```
#### Category Schema
```javascript
export default {
  name: 'category',
  type: 'document',
  title: 'Category',
  fields: [
    { name: 'title', type: 'string', title: 'Title' },
    { name: 'description', type: 'text', title: 'Description' },
  ],
};
```

#### Order Schema
```javascript
export default {
  name: 'order',
  type: 'document',
  title: 'Order',
  fields: [
    { name: 'user', type: 'reference', to: [{ type: 'user' }], title: 'User' },
    { name: 'products', type: 'array', of: [{ type: 'reference', to: [{ type: 'product' }] }], title: 'Products' },
    { name: 'totalPrice', type: 'number', title: 'Total Price' },
    { name: 'status', type: 'string', options: { list: ['Pending', 'Shipped', 'Delivered'] }, title: 'Status' },
    { name: 'shippingAddress', type: 'text', title: 'Shipping Address' },
  ],
};
```

#### User Schema
```javascript
export default {
  name: 'user',
  type: 'document',
  title: 'User',
  fields: [
    { name: 'name', type: 'string', title: 'Name' },
    { name: 'email', type: 'string', title: 'Email' },
    { name: 'role', type: 'string', options: { list: ['User', 'Admin'] }, title: 'Role' },
  ],

## Getting Started
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/MehwishSheikh15/Marketplace_builder_Hackathon_2025/tree/main
   cd comforty-ecommerce
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Environment Setup**:
   Create a `.env.local` file with:
   ```
   NEXT_PUBLIC_SANITY_PROJECT_ID=your_sanity_project_id
   NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
   NEXT_PUBLIC_SHIPENGINE_API_KEY=your_shipengine_api_key
   ```

4. **Run Locally**:
   ```bash
   npm run dev
   ```

5. **Access Locally**:
   Open [http://localhost:3000](http://localhost:3000) in your browser.

## Deployment
- **Frontend**: Deployed on [Vercel](https://vercel.com).
- **Sanity CMS**: Hosted on Sanity’s cloud platform.
- **APIs**: Managed by respective providers (e.g., EasyPaisa, ShipEngine).

## Contributors
- **Mehwish Sheikh**  
  **Roll Number**: 223558  
  **Faculty Mentors**: Ameen Alam, Ali Jawwad, Nida Rizwan, Naeem Hussain, Asharib Ali, Zia Khan.

## License
This project is for educational purposes as part of the **Governor Sindh Initiative AI Course Hackathon**.

