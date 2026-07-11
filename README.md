# CreatorFund

CreatorFund is a full-stack creator support platform built with Next.js. It allows creators to sign in using GitHub, create a public profile page, and receive support from users through Razorpay-powered payments.

## Features

* GitHub Authentication using NextAuth
* Creator Dashboard for profile management
* Dynamic Creator Pages based on username
* MongoDB database integration using Mongoose
* Razorpay payment integration
* Supporter messages and donation tracking
* Responsive UI built with Tailwind CSS

## Tech Stack

* Next.js 14
* React
* NextAuth
* MongoDB
* Mongoose
* Razorpay
* Tailwind CSS

## Project Flow

### 1. User Authentication

Users sign in using their GitHub account through NextAuth.

### 2. Dashboard

After logging in, users can manage:

* Name
* Username
* Profile Picture URL
* Cover Picture URL
* Razorpay Key ID
* Razorpay Key Secret

### 3. Creator Page

Each user gets a personalized page:

```bash
http://localhost:3000/[username]
```

Example:

```bash
http://localhost:3000/mnegi1723
```

Visitors can:

* View creator information
* Send support messages
* Make payments

### 4. Payments

The application uses Razorpay to process payments.

For payments to work, the creator must configure:

* Razorpay Key ID
* Razorpay Key Secret

inside the dashboard.

## Installation

### Clone the Repository

```bash
git clone <repository-url>
cd CreatorFund-main
```

### Install Dependencies

```bash
npm install
```

### Configure Environment Variables

Create a `.env` file in the project root:

```env
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_secret_key

GITHUB_ID=your_github_client_id
GITHUB_SECRET=your_github_client_secret
```

### Start MongoDB

Ensure MongoDB is running locally.

The project connects to MongoDB using the database configuration defined in the project.

### Run the Application

```bash
npm run dev
```

Open:

```bash
http://localhost:3000
```

## Authentication Setup

This project uses GitHub OAuth.

Create a GitHub OAuth App and configure:

### Homepage URL

```text
http://localhost:3000
```

### Authorization Callback URL

```text
http://localhost:3000/api/auth/callback/github
```

Add the generated credentials to the `.env` file.

## Razorpay Setup

To enable payments:

1. Create a Razorpay account.
2. Obtain your Razorpay Key ID and Key Secret.
3. Save them from the Dashboard after login.

Without these credentials, payment processing will not work.

## Database

The application stores:

### Users

* Email
* Username
* Name
* Profile Picture
* Cover Picture
* Razorpay Key ID
* Razorpay Key Secret

### Payments

* Supporter Name
* Message
* Amount
* Payment Status
* Recipient User

## Folder Structure

```text
app/
├── api/
├── dashboard/
├── login/
├── [username]/

components/
db/
models/
actions/
public/
```

## Learning Outcomes

This project demonstrates:

* OAuth Authentication with NextAuth
* Dynamic Routing in Next.js
* MongoDB Integration
* Server Actions
* Payment Gateway Integration
* Full-Stack Application Development

## Author

Mayank Singh Negi   

B.Tech CSE, Graphic Era Hill University

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
