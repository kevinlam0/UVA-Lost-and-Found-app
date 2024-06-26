# UVA-Lost-and-Found-app
## About the project
This Django-based project was built to benefit the UVA community. Our project is here to address the issue of having no formal method of reporting lost and found items around university grounds. More details may be found in our 'About Page' of our application.

I worked along four others as the DevOps manager to implement technologies and tools that were used in this project, incorporating the software development and IT operations. On top of development of source code, I was responsible for incorporating Amazon S3, continuous integration, and deployment to Heroku. Currently, this app is no longer deployed on Heroku because it was a school-funded project. 

## Getting Started
### Python Environment
Have a Python environment to download all dependencies used and run the app. If you haven't already, you can install Python [here](https://www.python.org/downloads/). You can then install the dependencies with the command below in your terminal within this project's directory:
```bash
pip install -r requirements.txt
```
### Prerequisites 
Before running this application, ensure you have the prerequisite project keys configured:
1. AWS S3 Access Key: To store and manage uploaded images, you'll need an AWS S3 bucket and access keys configured. If you don't have one, sign up for an AWS account and generate an access key in the IAM console. Ensure the access key is associated to an S3 bucket that will store your images. How to set up S3 bucket and IAM access keys [here](https://services.northwestern.edu/TDClient/30/Portal/KB/ArticleDet?ID=2025).
2. Google Authentication Key: Obtain a Google authentication key by creating a project in the Google Developer Console and configuring OAuth credentials. More information [here](https://medium.com/@infowithkiiru/django-user-registration-with-google-67524cce5ab7).
3. PostgreSQL (Optional): This project may run locally using SQLite. However, when ran in a production level platform like Heroku, this project uses PostgreSQL as the main model database. In this case, a `DATABASE_URL` configuration variable would need to be set. How to find connection string at this [Stack Overflow](https://stackoverflow.com/questions/3582552/what-is-the-format-for-the-postgresql-connection-string-url) post.
4. Django Secret Key: Used for cryptographic for hashing passwords. More information on how to generate your own secret key [here](https://www.educative.io/answers/how-to-generate-a-django-secretkey).

### Environment Variables
Once you obtained the necessary keys and credentials, set them as environment variables in your development environment. This app expects the following environment variables to be configured from a `ProjectKeys.json` file that users will need to create manually in their local machine:
- `AWS_ACCESS_KEY_ID`: Your AWS S3 access key ID
- `AWS_SECRET_ACCESS_KEY`: Your AWS S3 secret access key
- `GOOGLE_ALLAUTH_CLIENT_ID`: Your Google OAuth client ID
- `GOOGLE_ALLAUTH_SECRET`: Your Google OAuth client secret
- `DATABASE_URL`: The URL or connection string for your PostgreSQL database (Optional)
- `DJANGO_SECRET_KEY`: Django secret key

An example `ProjectKeys.json` file would look like this:
```json
{
  "DJANGO_SECRET_KEY": "your_generated_secret_key_here",
  "AWS_ACCESS_KEY_ID": "your_aws_access_key_id_here",
  "AWS_SECRET_ACCESS_KEY": "your_aws_secret_access_key_here",
  "GOOGLE_CLIENT_ID": "your_google_client_id_here",
  "GOOGLE_CLIENT_SECRET": "your_google_client_secret_here",
  "DATABASE_URL": "your_database_url_here"
}
```

### Commands to run first time using
```bash
python manage.py initializelocations
python manage.py migrate
```

## To run
```bash
python manage.py runserver
```

# Demo
[demo](https://private-user-images.githubusercontent.com/118573022/329095212-24253d6d-311a-4fc4-b40d-5e30fad02392.mov?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTUyMTc4OTEsIm5iZiI6MTcxNTIxNzU5MSwicGF0aCI6Ii8xMTg1NzMwMjIvMzI5MDk1MjEyLTI0MjUzZDZkLTMxMWEtNGZjNC1iNDBkLTVlMzBmYWQwMjM5Mi5tb3Y_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNTA5JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDUwOVQwMTE5NTFaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hZmIyOWRjYTdhMmFmNmQzYTMzYmI3MTdiNjIyNWQ1MzJjNWFiYzkwNDUxZjYwZWI4ODdjZWZhN2RkMGVmNGRmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.Lm4LWw168j136uhSPwjipE6tSdq68eggcX_q5l_tROs)
