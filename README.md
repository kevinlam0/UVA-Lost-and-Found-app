# UVA-Lost-and-Found-app

## Getting Started
### Prerequisites 
Before running this application, ensure you have the prerequisite project keys configured:
1. AWS S3 Access Key: To store and manage uploaded images, you'll need an AWS S3 bucket and access keys configured. If you don't have one, sign up for an AWS account and generate an access key in the IAM console. Ensure the access key is associated to an S3 bucket that will store your images.
2. Google Authentication Key: Obtain a Google authentication key by creating a project in the Google Developer Console and configuring OAuth credentials.
3. PostgreSQL (Optional): This project may run locally using SQLite. However, when ran in a production level platform like Heroku, this project uses PostgreSQL as the main model database. In this case, a `DATABASE_URL` configuration variable would need to be set.
4. Django Secret Key: Used for cryptographic for hashing passwords.

### Environment Variables
Once you obtained the necessary keys and credentials, set them as environment variables in your development environment. This app expects the following environment variables to be configured:
- `AWS_ACCESS_KEY_ID`: Your AWS S3 access key ID
- `AWS_SECRET_ACCESS_KEY`: Your AWS S3 secret access key
- `GOOGLE_ALLAUTH_CLIENT_ID`: Your Google OAuth client ID
- `GOOGLE_ALLAUTH_SECRET`: Your Google OAuth client secret
- `DATABASE_URL`: The URL or connection string for your PostgreSQL database (Optional)
- `DJANGO_SECRET_KEY`: Django secret key
