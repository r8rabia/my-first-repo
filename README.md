from flask import Flask, render_template, request, redirect, url_for, flash

app = Flask(__name__)
app.secret_key = 'secretkey'  
app = Flask(__name__)

@app.route('/')
def home():
    return render_template('home.html', title="BACK TO HOME")

@app.route('/about')
def about():
    return render_template('about.html', title="ABOUT US")

@app.route('/services')
def services():
    return render_template('services.html' , title="SERVICES")

@app.route('/gallery')
def gallery():
    return render_template('gallery.html', title="OUR GALLERY")
user_data = {"email": "test@example.com", "password": "password123"}

def login():
    if request.method == 'POST':
        # Simulate login validation
        return "Logged in!"
    return render_template('login.html')


@app.route('/registration', methods=['GET', 'POST'])
def registration():
    if request.method == 'POST':
        name = request.form['name']
        email = request.form['email']
        position = request.form['position']
        return render_template('success.html', message="Registration Successful! We'll contact you soon.")
    return render_template('registration.html')


if __name__ == '__main__':
    app.run(debug=True)