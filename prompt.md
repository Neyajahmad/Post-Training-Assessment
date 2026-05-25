# **Prompt**

## **Project Overview**

You are a skilled Full Stack MERN Developer.  
Your task is to build a modern SaaS-based Affiliate Link Management Platform for content creators, affiliate marketers, freelancers, and small businesses.

The platform should help users:

1. Create short affiliate links  
2. Manage and organize links easily  
3. Track clicks and visitor activity  
4. View analytics in real time  
5. Manage subscriptions and payments  
6. Securely access their dashboard using authentication

The system should be scalable, secure, user-friendly, and production-ready.

# **Main Goal**

Build a complete full-stack web application where users can:

1. Shorten long affiliate URLs  
2. Track performance of links  
3. View analytics dashboards  
4. Purchase subscription plans  
5. Manage campaigns  
6. Access role-based dashboards  
7. Use secure login/signup functionality

The application should support both normal users and admins.

# 

# **Authentication System**

Create a secure authentication system with:

## **Features**

1. User Registration  
2. Login System  
3. JWT Authentication  
4. Google Login (OAuth)  
5. Forgot Password  
6. Reset Password  
7. Persistent Login Sessions  
8. Protected Routes  
9. Logout Functionality

## **Roles**

### **Admin**

Can manage:

1. Users  
2. Reports  
3. Analytics  
4. Subscriptions  
5. Platform activities

### **User**

Can:

1. Create links  
2. Track analytics  
3. Manage profile  
4. Buy subscriptions

## **Security**

The application must protect against:

1. XSS attacks  
2. CSRF attacks  
3. SQL/NoSQL Injection  
4. Token tampering  
5. Unauthorized API access

Also implement:

1. Password hashing  
2. Secure token storage  
3. API rate limiting  
4. Input validation

# **Affiliate Link Management**

Users should be able to:

1. Add affiliate URLs  
2. Generate short links instantly  
3. Copy links easily  
4. Edit links  
5. Delete links  
6. Organize links by category or campaign

## **URL Features**

1. Unique short codes  
2. Fast redirection  
3. URL validation  
4. Duplicate prevention

# **Analytics Dashboard**

Build a modern analytics dashboard that shows:

1. Total clicks  
2. Daily clicks  
3. Monthly traffic  
4. Device type analytics  
5. Browser analytics  
6. Country/location tracking  
7. Traffic growth

## **Charts Required**

Use charts like:

1. Line Charts  
2. Bar Charts  
3. Pie Charts  
4. Real-time counters

Use libraries like:

1. Recharts  
2. Chart.js

# **Click Tracking System**

The backend should:

1. Track every click  
2. Store timestamps  
3. Store device information  
4. Store browser information  
5. Store IP/location details  
6. Handle high traffic efficiently

# **Subscription & Payment System**

Integrate Razorpay subscription system.

## **Features**

1. Subscription plans  
2. Monthly/yearly plans  
3. Secure payment flow  
4. Payment verification  
5. Subscription tracking  
6. Transaction history  
7. Failed payment handling

## **Credit System**

After successful payment:

1. Users receive credits/tokens  
2. Credits are consumed during link creation  
3. Dashboard shows remaining credits

# **Admin Panel**

Create a separate admin dashboard.

## **Admin Features**

Admin should be able to:

1. View all users  
2. Manage subscriptions  
3. Monitor traffic  
4. View reports  
5. Block suspicious users  
6. Remove users  
7. Monitor platform analytics  
8. View revenue statistics

# 

# **Frontend Requirements**

Build a clean modern responsive UI.

## **Pages Required**

1. Landing Page  
2. Login Page  
3. Register Page  
4. User Dashboard  
5. Analytics Dashboard  
6. Subscription Page  
7. Admin Panel  
8. Profile Settings Page

## **UI Features**

1. Responsive Design  
2. Mobile Friendly  
3. Dark/Light Mode  
4. Smooth Animations  
5. Dashboard Cards  
6. Real-time Updates

## **Accessibility**

1. Semantic HTML  
2. ARIA labels  
3. Keyboard support  
4. Accessible forms

# **Backend Requirements**

Build scalable REST APIs using Node.js and Express.js.

## **Backend Features**

1. Modular architecture  
2. Middleware handling  
3. Request validation  
4. Error handling middleware  
5. Structured API responses

# **Database Requirements**

Use MongoDB for storing:

1. User data  
2. Affiliate links  
3. Analytics data  
4. Subscription details  
5. Payment records

# **Error Handling**

Handle errors properly for:

1. Invalid login  
2. Expired tokens  
3. Invalid URLs  
4. Payment failures  
5. API failures  
6. Database issues

API responses should return:

1. Success status  
2. Message  
3. Error details (if needed)

# **Performance Optimization**

The application should:

1. Support high traffic  
2. Load fast  
3. Optimize frontend rendering  
4. Use lazy loading  
5. Reduce unnecessary re-renders  
6. Optimize database queries  
7. Use indexing where needed

# **SEO Optimization**

Implement:

1. SEO-friendly metadata  
2. Fast loading pages  
3. Optimized images  
4. Mobile optimization  
5. Clean URL structures

# **Tech Stack**

## **Frontend**

1. React.js  
2. Tailwind CSS  
3. Axios  
4. React Router  
5. Recharts / Chart.js

## **Backend**

1. Node.js  
2. Express.js  
3. JWT Authentication  
4. Razorpay SDK

## **Database**

1. MongoDB

## **Authentication**

1. Google OAuth  
2. JWT

# **Final Expected Result**

The final project should include:

1. Fully working SaaS affiliate platform  
2. Secure authentication system  
3. Real-time analytics dashboard  
4. Razorpay payment integration  
5. Admin/User role management  
6. Scalable backend structure  
7. Modern responsive UI  
8. Production-ready deployment setup

