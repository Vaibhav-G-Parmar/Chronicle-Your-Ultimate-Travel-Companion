# Installation Instructions

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Node.js (recommend version X.X or higher)
- npm (comes with Node.js)
- Git

## Cloning the Repository

Clone the repository and its submodules to your local machine using the following commands:

\```bash
git clone https://github.com/Vaibhav-G-Parmar/PRJ566-Team_4.git
cd PRJ566-Team_4
git submodule init
git submodule update
\```

## Installation

### Front-end (Next.js App)

1. Navigate to the front-end directory:
   \```bash
   cd Chronicle_Web_App_Repo_SubModule 
   \```
   
2. Install the required packages:
   \```bash
   npm install
   \```
   
3. Configure environment variables:
   - Create a `.env` file in the front-end directory.
   - Add the necessary environment variables:
     \```
     NEXT_PUBLIC_API_URL="http://localhost:8080/api"
     NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=<your_google_maps_api_key>
     \```
   - To obtain a Google Maps API key, follow the steps outlined [here](https://developers.google.com/maps/documentation/javascript/get-api-key).

### Back-end (Express.js API)

1. Navigate to the back-end directory:
   \```bash
   cd ../Chronicle_Users_API_Repo_SubModule
   \```
   
2. Install the required packages:
   \```bash
   npm install
   \```
   
3. Configure environment variables:
   - Create a `.env` file in the back-end directory.
   - Add the necessary environment variables:
     \```
     MONGO_URL=<your_database_connection_string>
     REFRESH_TOKEN=<your_dropbox_refresh_token>
     APP_KEY=<your_dropbox_app_key>
     APP_SECRET=<your_dropbox_app_secret>
     \```
   - Obtain `REFRESH_TOKEN`, `APP_KEY`, and `APP_SECRET` by setting up your application storage at [Dropbox for Developers](https://www.dropbox.com/developers).

## Running the Application

### Running the API

1. In the `backend` directory, start the API server:
   \```bash
   node server.js
   \```

### Running the Front-end

1. Open a new terminal and navigate to the `frontend` directory.
2. Start the Next.js development server:
   \```bash
   npm run dev
   \```

## Accessing the Application

- The front-end application will be available at [http://localhost:3000](http://localhost:3000).
- The API will be accessible at [http://localhost:8080](http://localhost:8080).
