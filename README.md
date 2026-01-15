# 💌 Ruchu Grievance Portal

A fun grievance portal built using Flask, Python, and SQLite for managing grievances between users. The portal allows users to submit grievances, while administrators can respond to them, track their resolution, and send email notifications.

---

## 📄 Clone This Repo Into Your Own GitHub (For Beginners)

Want to customize or privately host your own version of this project? Here’s how you can copy it to your GitHub:

1. **Visit the Original Repo**: Sign in to Github and navigate to the original repo here:  
   `https://github.com/ishan-nerlekar/girlfriend-grievance-portal`
2. **Click “Fork”** (top-right corner):  
   This will create a copy of the project in your own GitHub account.
3. **(Optional) Rename the Repository**:  
   After forking, go to the "Settings" tab of your new repo and change the name if you like.
4. You now have your own private/public version of the code to deploy and modify!

---

## 🚀 Quick Deployment (Recommended)

**No coding needed! Just follow these steps:**

1. Go to [https://railway.app](https://railway.app)
2. Click **"New Project"** → **"Deploy from GitHub Repo"**
3. Link your GitHub and choose this repository
4. In the **Environment Variables** section, add the following:

```env
EMAIL_ADMIN=your.email@gmail.com
EMAIL_PASS=your-app-password
EMAIL_DEFAULT_SENDER=your.email@gmail.com
EMAIL_USER_RECEIVER=your.partner.email@gmail.com
USER_NAME=girlfriend
USER_PASSWORD=user123
ADMIN_NAME=boyfriend
ADMIN_PASSWORD=admin123
PORTAL_URL=https://your-railway-url.up.railway.app
```

💡 *To get the EMAIL_PASS, generate an App Password from your Gmail account at [https://myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords)*

5. Done! 🚀 Your private grievance portal is live and ready!

---

## 🖼️ How to Add Images

Want to personalize the portal by adding your own images (like custom banners or cute icons)? It’s easy!

1. Go to the project folder.
2. Open the `static/images/` directory. This is where all your image files are stored.
3. Copy and paste your image file into that folder.
4. Replace `home_image.webp` with the image of your choice, and so on for all the images. Do not rename the images, just replace them.

That's it! The image will now be displayed on the page.

---

## 🌐 Features

- User authentication for both user and administrator.
- Submit grievances with a title, description, mood, and priority.
- View grievances and their resolution status.
- Admin dashboard to manage grievances and send responses.
- Email notifications to both admins and users regarding grievances and responses.

## 🛠️ Technologies Used

- **Backend:** Python, Flask
- **Database:** SQLite
- **Frontend:** HTML, CSS (Bootstrap for responsiveness)
- **Email Service:** Gmail SMTP
- **Environment Variables:** `.env` for sensitive data
- **Deployment**: Railway

## 💻 Want to Run Locally? (Optional for Devs)

### Prerequisites

- Python 3.x
- pip (Python package manager)

### Steps

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/girlfriend-grievance-portal.git
   cd girlfriend-grievance-portal
   ```

2. **Create and activate a virtual environment:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # For Linux/Mac
   .\venv\Scripts\activate   # For Windows
   ```

3. **Install required dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables:**

   Edit the `.env` file in the root of the project and add the following:

    ```env
    # Gmail address to send notifications from (admin)
    EMAIL_ADMIN=admin.email@example.com

    # App-specific password generated from your Gmail account
    EMAIL_PASS=yourapppassword

    # The default sender for outgoing emails (usually same as EMAIL_ADMIN)
    EMAIL_DEFAULT_SENDER=admin.email@example.com

    # Recipient email address for user (the person submitting grievances)
    EMAIL_USER_RECEIVER=user.email@example.com

    # Username and password for user (grievance submitter)
    USER_NAME=girlfriend
    USER_PASSWORD=user123

    # Username and password for admin (responder)
    ADMIN_NAME=boyfriend
    ADMIN_PASSWORD=admin123

    # Your hosted app URL (used in email templates)
    PORTAL_URL=http://your-grievance-portal-url
    ```
   - Replace `admin.email@example.com` and `user.email@example.com` with your actual Gmail credentials.
   - Replace `girlfriend` and `boyfriend` with user and admin display names respectively, as desired. Similarly with their corresponding passwords.
   - The `EMAIL_PASS` should be your Gmail app password (not your Google account password).

    To generate a Gmail app password:  
    - Visit [Google App Passwords](https://myaccount.google.com/apppasswords)
    - Generate a 16-character password and paste it as `EMAIL_PASS`

5. **Initialize the database:**

   ```bash
   python
   >>> from app import init_db
   >>> init_db()
   ```

   This will create the necessary SQLite database for storing grievances.

6. **Run the application:**

   ```bash
   flask run
   ```

   The portal should now be running at `http://localhost:5000`.

## Usage

1. **Login:**
   - Regular users can log in with the `USER_NAME` and `USER_PASSWORD`.
   - Administrators can log in with the `ADMIN_NAME` and `ADMIN_PASSWORD`.

2. **Submit Grievance:**
   - After logging in, regular users can submit grievances with a title, description, mood, and priority.

3. **Admin Dashboard:**
   - Administrators can view all grievances, respond to them, and mark them as resolved.

4. **Email Notifications:**
   - Email notifications are sent to both the admin and user when a grievance is submitted and when a response is given.

## 📁 Project Structure

```
girlfriend-grievance-portal/
│
├── app.py                # Main application logic
├── .env                  # Environment variables
├── requirements.txt      # Python dependencies
├── .gitignore            # Git ignore file
├── templates/            # HTML templates
│   ├── home.html
│   ├── login.html
│   ├── submit.html
│   ├── thankyou.html
│   ├── my_grievances.html
│   └── dashboard.html
└── venv/                 # Virtual environment
```

### Notes:

- Make sure to set up your environment variables correctly in the `.env` file.
- If you're using Gmail for sending emails, ensure you use an app password (not your Google account password) if two-factor authentication (2FA) is enabled.

For more information, visit the official [Flask Documentation](https://flask.palletsprojects.com/).
