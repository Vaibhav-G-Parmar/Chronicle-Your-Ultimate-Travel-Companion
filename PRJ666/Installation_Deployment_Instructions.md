# Installation Instructions

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Node.js
- npm
- Git

## Cloning the Repository

Clone the repository and its submodules to your local machine using the following commands:

~~~bash
git clone https://github.com/Vaibhav-G-Parmar/PRJ566-Team_4.git
cd PRJ566-Team_4
git submodule init
git submodule update
~~~

## Installation

### Front-end (Next.js App)

1. Navigate to the front-end directory:
   ~~~bash
   cd Chronicle_Web_App_Repo_SubModule 
   ~~~
   
2. Install the required packages:
   ~~~bash
   npm install
   ~~~
   
3. Configure environment variables:
   - Create a `.env` file in the front-end directory.
   - Add the necessary environment variables:
     ~~~
     NEXT_PUBLIC_API_URL="http://localhost:8080/api"
     NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=<your_google_maps_api_key>
     ~~~
   - To obtain a Google Maps API key, follow the steps outlined [here](https://developers.google.com/maps/documentation/javascript/get-api-key).

### Back-end (Express.js API)

1. Navigate to the back-end directory:
   ~~~
   cd ../Chronicle_Users_API_Repo_SubModule
   ~~~
   
2. Install the required packages:
   ~~~
   npm install
   ~~~
   
3. Configure environment variables:
   - Create a `.env` file in the back-end directory.
   - Add the necessary environment variables:
     ~~~
     MONGO_URL=<your_database_connection_string>
     REFRESH_TOKEN=<your_dropbox_refresh_token>
     APP_KEY=<your_dropbox_app_key>
     APP_SECRET=<your_dropbox_app_secret>
     ~~~
   - Obtain `REFRESH_TOKEN`, `APP_KEY`, and `APP_SECRET` by setting up your application storage at [Dropbox for Developers](https://www.dropbox.com/developers).
   - Get `MONGO_URL` by creating a cluster at [Mongo Atlas](https://www.mongodb.com/atlas/database)

## Running the Application

### Running the API

1. In the `backend` directory, start the API server:
   ~~~
   node server.js
   ~~~

### Running the Front-end

1. Open a new terminal and navigate to the `frontend` directory.
2. Start the Next.js development server:
   ~~~
   npm run dev
   ~~~

## Accessing the Application

- The front-end application will be available at [http://localhost:3000](http://localhost:3000).
- The API will be accessible at [http://localhost:8080](http://localhost:8080).

# Deployment Instructions

## Frontend Deployment on Vercel

1. Sign up or log in to your Vercel account.
2. Click on the "New Project" button.
3. Import your project from your GitHub repository.
4. Before deploying, set up your environment variables by going to the "Settings" tab of your project:
   - Click on the "Environment Variables" section.
   - Add all the necessary variables such as `NEXT_PUBLIC_API_URL` and `NEXT_PUBLIC_GOOGLE_MAPS_API_KEY`.
5. After setting your environment variables, deploy your application by clicking the "Deploy" button.

## Backend Deployment on Cyclic

1. Sign up or log in to your Cyclic account.
2. Click on "New App" and choose to import from GitHub.
3. Select your repository containing the Express.js backend.
4. Configure your environment variables in the Cyclic dashboard:
   - Navigate to the "Environment" tab of your app settings.
   - Add the environment variables such as `MONGO_URL`, `REFRESH_TOKEN`, `APP_KEY`, and `APP_SECRET`.
5. Once you've set up the environment variables, deploy your application.

## Database Setup with MongoDB Atlas

1. Sign up or log in to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Create a new cluster if you haven't already.
3. Create a new database user with read and write privileges.
4. Go to the "Network Access" section and add an IP address to allowlist from which your backend will connect.
5. Navigate to the "Clusters" section, click on "Connect" and then choose "Connect your application".
6. Copy the connection string provided.
7. Replace the `<password>` with the database user's password you created and add this to your environment variables on Cyclic as `MONGO_URL`.
