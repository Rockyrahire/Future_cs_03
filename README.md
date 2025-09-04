# Future_cs_03

Setting Up the Environment

First, ensure that you have Python installed and set up a virtual environment.

# Create a new directory for your project
mkdir secure-file-sharing-system
cd secure-file-sharing-system

# Create a virtual environment (optional but recommended)
python3 -m venv venv
source venv/bin/activate  # For Windows use `venv\Scripts\activate`

# Install required libraries
pip install Flask PyCryptodome



secure-file-sharing-system/
│
├── app.py             # Main Flask application
├── encryption.py      # Handles AES encryption/decryption
├── uploads/           # Folder to store uploaded files (encrypted)
└── requirements.txt   # List of dependencies
Requirements File (requirements.txt)

Create a requirements.txt file to manage dependencies:

Flask==2.1.2
pycryptodome==3.15.0

6. Running the Application

Make sure your Flask app is set up correctly and then run the application.

# Run the app
python app.py


This will start the Flask server, and you can interact with it through the following API endpoints:

Upload a file:

Use POST to /upload with the file included in the request body.

Example using Postman or curl:

curl -X POST -F "file=@path_to_your_file" http://localhost:5000/upload


Download a file:

Use GET to /download/<filename>, where <filename> is the name of the encrypted file you want to download.

Example using Postman or curl:

curl http://localhost:5000/download/yourfile.enc -o decrypted_file

7. Further Improvements

Key Management: In a real-world scenario, do not hardcode keys; use a secure key management solution.

Security Considerations: Make sure to use HTTPS and other security measures to protect the data in transit.

File Type Checking: Validate file types for security reasons to prevent malicious uploads.

With this, you should have a basic working Secure File Sharing System with AES encryption for file uploads/downloads.

Let me know if you need further details or help with testing!
