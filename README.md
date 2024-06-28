# Flask App Deployment with Vercel

This repository contains a simple Flask application and instructions for deploying it on Vercel.

## Flask Application

This Flask application serves a basic "Hello World!" response.

### Code

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello World!'

if __name__ == '__main__':
    app.run()
```

## Deployment on Vercel

To deploy this Flask application on Vercel, follow these steps:

### Prerequisites

- A Vercel account. Sign up at [Vercel](https://vercel.com/signup).
- Vercel CLI installed. You can install it using npm:

  ```bash
  npm install -g vercel
  ```

### Steps

1. **Fork or Clone the Repository**:
   - Fork this repository or clone it to your local machine.

     ```bash
     git clone https://github.com/yourusername/your-repo-name.git
     cd your-repo-name
     ```

2. **Create a `vercel.json` File**:
   - Create a `vercel.json` file in the root directory of your project with the following content:

     ```json
     {
       "version": 2,
       "builds": [
         {
           "src": "app.py",
           "use": "@vercel/python"
         }
       ],
       "routes": [
         {
           "src": "/(.*)",
           "dest": "app.py"
         }
       ]
     }
     ```

3. **Login to Vercel**:
   - Log in to your Vercel account using the Vercel CLI.

     ```bash
     vercel login
     ```

4. **Deploy the Application**:
   - Deploy your application to Vercel.

     ```bash
     vercel
     ```

5. **Follow the Prompts**:
   - Follow the prompts to complete the deployment. Vercel will ask for the project name, the directory containing your project, and other settings. Accept the default settings or customize as needed.

6. **Access Your Deployed Application**:
   - After deployment is complete, Vercel will provide you with a URL where your Flask application is live.

## Additional Notes

- Ensure that your `requirements.txt` file lists all necessary dependencies for your Flask application.
- For more advanced configurations, refer to the [Vercel documentation](https://vercel.com/docs).

## License

Unlicensed
