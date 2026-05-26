# **Prompt** 

# **Context and Role**

Act as Senior Full Stack MERN Developer and SaaS Architect. Your job is to build an Affiliate Link Management Platform for people like content creators and affiliate marketers. This platform is also for YouTubers  bloggers  freelancers and small businesses.

The problem is that affiliate marketers have to deal with a lot of issues. They have to manage hundreds of affiliate links by hand. They lose data about how their links perform.

The platform I want to building will have a dashboard. From this dashboard users can create new affiliate links organize them make them shorter manage them and track them. They can also see how their links are doing in time.This includes things like how many peoples are clicking on the links  what kind of devices they are using what browser they have how much traffic they are getting and where the users are from.

My main goal is to make sure the platform can handle a lot of users. It has to be safe and work well. The platform also has to be easy to use on devices. It needs to have an user interface and experience. The platform will have subscription plans. It will also have analytics and a smooth user experience. The Affiliate Link Management Platform will let different users work together and have their roles. This means some users can do things than others. The platform will also let many users work together at the time.

# **Project Objective**

A Complete Full Stack SaaS Affiliate Link Management Platform: 

1. Allows users to create and shorten affiliate links instantly using a fast and reliable URL shortening system that generates unique short codes and prevents duplicate collisions.  
2. Helps users organize affiliate links into campaigns or categories so multiple marketing projects can be managed efficiently from a single dashboard.  
3. Tracks real time analytics such as total clicks  device types  browser information  timestamps  and geographic locations to help users understand campaign performance.  
4. Provides subscription based access using Razorpay payment gateway integration where users can purchase plans and receive credits or tokens for link creation.  
5. Implements secure authentication and authorization using JWT authentication and Google OAuth Single Sign On for secure and user friendly login experiences.  
6. Supports role based access management where admins can monitor the entire platform while standard users can manage only their personal campaigns and affiliate links.  
7. Ensures scalable backend architecture capable of handling high traffic  analytics processing  and real time dashboard updates efficiently.

# **Background and Real World Context**

Affiliate marketers often share links across YouTube  Instagram  blogs  newsletters  and advertisements. Managing these links manually becomes difficult when traffic grows because users cannot easily track which campaigns generate the highest engagement or conversions.

This platform acts as a centralized affiliate management solution where users can:

1. Store and organize all affiliate links in one secure location.  
2. Generate shortened URLs for better sharing and branding purposes.  
3. Analyze link performance using real time analytics dashboards.  
4. Track audience engagement based on devices  browsers  and locations.  
5. Improve campaign management and marketing decisions using accurate performance insights.

For example  a YouTuber promoting affiliate products in video descriptions can instantly monitor which videos generate the most clicks and understand audience behavior through analytics reports.

# **Application Workflow**

The complete system workflow should function as follows:

1. Users visit the platform landing page and either register manually or log in using Google OAuth authentication.  
2. After successful authentication  users access the dashboard and choose a subscription plan using Razorpay payment integration.  
3. Once payment verification is completed successfully  the backend allocates credits or tokens to the user account.  
4. Users enter long affiliate URLs into the dashboard form.  
5. The backend validates the URL and generates a unique shortened affiliate link.  
6. Users can copy and share shortened links across YouTube  Instagram  blogs  social media platforms  and advertisements.  
7. Whenever visitors click shortened links  the backend captures analytics information such as:  
   1. Click count  
   2. Device type  
   3. Browser information  
   4. Geographic location  
   5. Traffic timestamps  
8. The analytics dashboard updates dynamically in real time using charts  counters  and visual reports.  
9. Admins can monitor users  traffic  subscriptions  payments  analytics  and suspicious platform activities from a dedicated admin panel.

# **Frontend Development Requirements**

The frontend should be built using modern technologies that provide fast rendering  responsive layouts  reusable components  and smooth user experience.

### **React.js**

Use React.js for building a scalable and component based frontend architecture. 

### **Tailwind CSS**

Use Tailwind CSS to design a modern  responsive  and visually attractive user interface. 

### **Axios**

Use Axios for secure communication between frontend and backend APIs. 

**React Router**

Use React Router for implementing client side routing and navigation across pages such as login  register  dashboard  analytics  subscriptions  admin panel  and profile settings.

**Chart.js**

Use Chart.js or Recharts for building interactive analytics dashboards.

# **Required Frontend Pages**

The application should include the following pages:

### **Landing Page**

Create a professional landing page containing a hero section  feature highlights  pricing plans  testimonials  CTA buttons  and platform overview information to attract users.

### **Login and Register Page**

Build secure login and registration pages with JWT authentication  Google OAuth Single Sign On  form validation  password protection  and responsive authentication UI.

### **User Dashboard**

Develop a centralized dashboard where users can create  manage  organize  edit  delete  and monitor affiliate links and campaign performance.

### **Analytics Dashboard**

Create a real time analytics dashboard displaying charts  click reports  device analytics  geographic traffic insights  and campaign growth statistics visually.

### **Subscription Page**

Develop a subscription and billing page where users can purchase plans using Razorpay and monitor token or credit balances.

### **Admin Panel**

Create an admin dashboard where administrators can monitor users  subscriptions  platform analytics  revenue reports  suspicious activities  and traffic logs.

### **Profile Settings Page**

Allow users to manage profile information  passwords  account preferences  and subscription details securely.

# **Backend Development Requirements**

The backend should be developed using Node.js and Express.js with scalable architecture and modular API design.

### **Node.js**

Use Node.js for building a high performance backend server capable of handling concurrent requests  analytics processing  authentication management  and real time API communication.

### **Express.js**

Use Express.js to create scalable RESTful APIs with middleware based request handling  route management  authentication validation  and structured API architecture.

### **Modular Architecture**

Organize the backend using separate folders for routes  controllers  middleware  services  utilities  and database models to improve scalability and maintainability.

### **Middleware Based Request Handling**

Implement middleware for authentication validation  authorization checks  request parsing  logging  rate limiting  and error handling throughout the application.

### **Structured API Responses**

All backend APIs should return properly structured JSON responses containing success status  messages  response data.

# **Database Requirements**

Use MongoDB as the primary database for storing all application data securely and efficiently.

### **User Data Storage**

Store user profile information  authentication credentials  roles  and subscription details securely in MongoDB collections.

### **Affiliate Link Storage**

Store long URLs  shortened URLs  campaign categories  click counts  and generated short codes efficiently for fast retrieval and redirection.

### **Analytics Data Storage**

Store analytics logs including clicks  timestamps  device types  browser information  and geographic locations for real time reporting and dashboard visualization.

### **Payment and Subscription Records**

Store Razorpay transactions  payment verification data  token balances  subscription plans  and billing history securely.

### **Database Optimization**

Use indexing  aggregation pipelines  query optimization  and efficient schema design to improve performance and scalability for large analytics datasets.

# **Authentication and Security Requirements**

The platform must implement enterprise level authentication and security standards.

### **User Registration and Login**

Create secure login and registration pages where users can create accounts using email/password authentication with proper validation and encrypted password storage.

### **JWT Based Authentication**

Use JWT authentication for secure session management between frontend and backend.

**Google OAuth Single Sign On**

Implement Google OAuth Single Sign On so users can log in quickly using Google accounts directly from the login and registration page for better user convenience and security.

### **Token Expiration and Refresh Handling**

Implement token expiration handling and refresh token mechanisms so users remain authenticated securely without frequent manual logins.

### **Protected API Routes**

Secure all private backend APIs using authentication middleware so unauthorized users cannot access dashboards  analytics  subscriptions  or admin functionality.

### **Role Based Access Control**

Implement separate access permissions for Admin and Standard Users so admins can manage the platform while users can manage only their own data.

### **Middleware Based Authorization**

Use Express middleware to validate user roles before granting access to sensitive routes and admin level operations.

# **Affiliate Link Management Requirements**

The platform should provide a complete affiliate link management system.

### **Link Creation System**

Allow users to submit long affiliate URLs and instantly generate shortened URLs using a secure short link generation algorithm.

### **Unique Short Code Generation**

Generate unique short codes for every affiliate link while preventing duplicate collisions and maintaining fast redirection performance.

### **Link Organization**

Allow users to categorize and organize affiliate links using campaigns  folders  or categories for better management.

# **Analytics and Tracking Requirements**

The analytics system should provide real time performance monitoring and traffic insights.

### **Real Time Click Tracking**

Track every click on affiliate links instantly and update dashboard analytics dynamically without requiring manual page refreshes.

### **Device Type Analytics**

Capture visitor device information such as desktop  mobile  and tablet usage and display it visually using charts and graphs.

### **Browser Analytics**

Track browser usage information to help users understand audience browsing behavior.

### **Geographic Location Tracking**

Capture geographic location data using IP based tracking to identify regions generating the most traffic.

### **Interactive Dashboard Charts**

Use charts and visual analytics to display traffic growth  click performance  user engagement  and campaign trends clearly. 

# **Razorpay Payment Integration Requirements**

Implement a secure subscription based payment system using Razorpay.

### **Subscription Plan Selection**

Create subscription plans with different pricing and token allocation systems for users based on their affiliate marketing needs.

### **Secure Payment Processing**

Use Razorpay APIs for secure online payment processing and transaction handling.

### **Payment Verification**

Verify Razorpay payment signatures securely on the backend before activating subscriptions or allocating user credits.

### **Transaction History**

Allow users to monitor payment records  subscription history  invoices  and billing activities from the dashboard.

### **Failed Payment Handling**

Handle failed transactions gracefully by displaying proper error messages and retry options for users.

### **Token and Credit Allocation**

After successful payment  automatically allocate tokens or credits that users consume while generating affiliate links.

# **Admin Panel Requirements**

The admin dashboard should provide complete platform monitoring and management capabilities.

### **User Management**

Allow admins to monitor registered users  block suspicious accounts  manage roles  and remove harmful activities from the platform.

### **Subscription Monitoring**

Admins should monitor subscription plans  payment activities  failed transactions  and revenue reports centrally.

### **Platform Analytics**

Provide platform wide analytics such as active users  total traffic  revenue growth  affiliate link usage  and click performance.

# **Data Processing Flow**

The application should follow a structured frontend to backend processing architecture.

### **Frontend Request Handling**

The React frontend collects user input and sends API requests securely using Axios.

### **Backend Validation**

Express middleware validates authentication tokens  request data  URLs  and user permissions before processing requests.

### **Business Logic Processing**

Backend services process link generation  analytics tracking  payment verification  and role based operations efficiently.

### **Database Communication**

MongoDB stores user data  affiliate links  analytics logs  subscriptions  and payment records securely.

### **Analytics Processing**

Whenever a shortened link is clicked  the backend captures tracking data and updates analytics collections dynamically.

### **Dashboard Visualization**

The frontend dashboard fetches analytics APIs and visualizes updated reports using charts and counters in real time.

# **Error Handling and Input Validation**

The system must gracefully handle invalid operations and unexpected failures.

### **URL Validation**

Validate all affiliate URLs before shortening to ensure only valid and safe URLs are accepted.

### **Authentication Error Handling**

Display proper error messages for invalid credentials  expired tokens  unauthorized access  and failed authentication requests.

### **Payment Error Handling**

Handle Razorpay payment failures securely and provide meaningful retry messages to users.

### **API Error Handling**

Implement centralized backend error handling middleware that returns structured JSON responses with proper HTTP status codes.

### **Database Error Handling**

Handle database connection failures  query errors  and unexpected server crashes without affecting overall platform stability.

### **User Friendly Notifications**

Use toast notifications  alerts  and validation messages on the frontend to provide clear feedback for successful and failed operations.

# **Expected Final Output**

The final project should deliver:

* A fully functional SaaS Affiliate Link Management Platform with modern UI and scalable architecture.  
* Secure authentication system using JWT and Google OAuth Single Sign On.  
* Real time analytics dashboard with charts  traffic reports  and audience insights.  
* Razorpay subscription and payment integration with token based access management.  
* Role based admin and user management system with secure permissions.  
* Fast and optimized affiliate link generation and tracking system.  
* Responsive frontend supporting desktop  tablet  and mobile devices.  
* Production ready deployment with secure backend architecture and optimized database performance.