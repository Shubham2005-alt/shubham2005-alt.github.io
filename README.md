<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Welcome Page</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background-color: #f4f6f9;
    }

    /* 1. Welcome Modal Styling */
    #welcome-screen {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.8);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .welcome-card {
      background: #ffffff;
      padding: 40px;
      border-radius: 12px;
      text-align: center;
      box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    }

    .welcome-icon {
      font-size: 60px;
      margin-bottom: 15px;
    }

    .welcome-card h1 {
      margin-bottom: 10px;
      color: #333;
    }

    .welcome-card button {
      margin-top: 20px;
      padding: 10px 25px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
    }

    /* 2. Main Auth Box Styling */
    .auth-container {
      background: #ffffff;
      padding: 30px;
      border-radius: 10px;
      width: 350px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      display: none; /* Modal close hone ke baad dikhega */
    }

    .tab-buttons {
      display: flex;
      margin-bottom: 20px;
    }

    .tab-buttons button {
      flex: 1;
      padding: 10px;
      border: none;
      background: #e9ecef;
      cursor: pointer;
      font-weight: bold;
    }

    .tab-buttons button.active {
      background: #007bff;
      color: white;
    }

    .form-group {
      margin-bottom: 15px;
    }

    .form-group label {
      display: block;
      margin-bottom: 5px;
      font-size: 14px;
    }

    .form-group input {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .submit-btn {
      width: 100%;
      padding: 10px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <div id="welcome-screen">
    <div class="welcome-card">
      <div class="welcome-icon">👋</div>
      <h1>Welcome to Our Website!</h1>
      <p>Aapka hamari website par swagat hai.</p>
      <button onclick="enterSite()">Aage Badhein</button>
    </div>
  </div>

  <div class="auth-container" id="auth-box">
    <div class="tab-buttons">
      <button id="login-tab" class="active" onclick="showForm('login')">Log In</button>
      <button id="register-tab" onclick="showForm('register')">Register</button>
    </div>

    <form id="login-form">
      <div class="form-group">
        <label>Email / Username</label>
        <input type="text" placeholder="Enter email" required>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input type="password" placeholder="Enter password" required>
      </div>
      <button type="submit" class="submit-btn">Log In</button>
    </form>

    <form id="register-form" class="hidden">
      <div class="form-group">
        <label>Full Name</label>
        <input type="text" placeholder="Enter your name" required>
      </div>
      <div class="form-group">
        <label>Email</label>
        <input type="email" placeholder="Enter email" required>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input type="password" placeholder="Create password" required>
      </div>
      <button type="submit" class="submit-btn">Register</button>
    </form>
  </div>

  <script>
    // Welcome screen hatane ke liye function
    function enterSite() {
      document.getElementById('welcome-screen').style.display = 'none';
      document.getElementById('auth-box').style.display = 'block';
    }

    // Login aur Register tabs switch karne ke liye function
    function showForm(formType) {
      const loginForm = document.getElementById('login-form');
      const registerForm = document.getElementById('register-form');
      const loginTab = document.getElementById('login-tab');
      const registerTab = document.getElementById('register-tab');

      if (formType === 'login') {
        loginForm.classList.remove('hidden');
        registerForm.classList.add('hidden');
        loginTab.classList.add('active');
        registerTab.classList.remove('active');
      } else {
        loginForm.classList.add('hidden');
        registerForm.classList.remove('hidden');
        registerTab.classList.add('active');
        loginTab.classList.remove('active');
      }
    }
  </script>

</body>
</html>
