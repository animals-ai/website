<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Moving Car with Spinning Wheels and Gas</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #fff;
      font-family: Arial, sans-serif;
    }

    /* Header Navigation Style */
    header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 60px;
      background-color: red;
      color: white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 20px;
      z-index: 10;
    }

    /* Logo and Title */
    .logo {
      font-size: 24px;
      font-weight: bold;
    }

    /* Header Links (Buy, Sell, Contact) */
    .header-links {
      position: absolute;
      right: 90px;
      display: flex;
      gap: 20px;
    }

    .header-links a {
      text-decoration: none;
      color: white;
      font-size: 16px;
      font-weight: bold;
      padding: 5px 10px;
      border-radius: 5px;
      background-color: transparent;
      transition: background-color 0.3s;
    }

    .header-links a:hover {
      background-color: rgba(255, 255, 255, 0.3);
    }

    /* Car Animation */
    .car {
      position: absolute;
      top: 10px;  /* Adjust car's position in the header */
      left: -90px; /* Initial position off-screen */
      width: 100px;
      height: 40px;
      animation: drive 3s linear infinite;
    }

    .car-top {
      width: 100px;
      height: 30px;
      background-color: white;
      border-radius: 10px 10px 0 0;
    }

    /* Wheel Styles */
    .wheel {
      width: 20px;
      height: 20px;
      background-color: white;
      border-radius: 50%;
      position: absolute;
      bottom: -10px;
      animation: spin 1s linear infinite;
    }

    .wheel.left {
      left: 10px;
    }

    .wheel.right {
      right: 10px;
    }

    /* Gas Puff */
    .gas {
      position: absolute;
      top: 50%;
      left: 100%;
      width: 20px;
      height: 20px;
      background-color: rgba(200, 200, 200, 0.7);
      border-radius: 50%;
      opacity: 0;
      animation: puff 1.5s ease-out infinite;
    }

    /* Car movement animation */
    @keyframes drive {
      from { left: -150px; }
      to { left: 25%; }  /* Moves to 1/4th of the screen width */
    }

    /* Spinning wheel animation */
    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    /* Gas Puff animation */
    @keyframes puff {
      0% {
        opacity: 1;
        transform: translateX(0) scale(1);
      }
      50% {
        opacity: 0.5;
        transform: translateX(20px) scale(1.5);
      }
      100% {
        opacity: 0;
        transform: translateX(40px) scale(2);
      }
    }
  /* Contact Form Section */
    .contact-form {
      padding: 50px 20px;
      margin-top: 80px;
      background-color: #f7f7f7;
      border-radius: 10px;
      max-width: 600px;
      margin: 50px auto;
    }

    .contact-form h2 {
      text-align: center;
      margin-bottom: 20px;
      font-size: 24px;
      color: red;
    }

    .contact-form input, .contact-form textarea {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 16px;
    }

    .contact-form button {
      background-color: red;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      font-size: 18px;
      cursor: pointer;
    }

    .contact-form button:hover {
      background-color: darkred;
    }
/* Basic reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
}

/* Footer Styles */
.footer {
  background-color: red;
  color: white;
  padding: 40px 20px;
  margin-top: 50px;
  text-align: center;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
}

.footer-info,
.footer-links,
.footer-social {
  width: 30%;
  min-width: 250px;
}

.footer-info h3,
.footer-links h3,
.footer-social h3 {
  font-size: 18px;
  margin-bottom: 10px;
  color: #fff;
}

.footer-info p,
.footer-links ul,
.footer-social ul {
  font-size: 14px;
  color: #ddd;
}

.footer-links ul {
  list-style-type: none;
}

.footer-links li,
.footer-social li {
  margin: 5px 0;
list-style-type: none;

}

.footer-links a,
.footer-social a {
  text-decoration: none;
  color: #ddd;
  transition: color 0.3s ease;
}

.footer-links a:hover,
.footer-social a:hover {
  color: #ff6347; /* A bright red/orange color for hover */
}

.footer-bottom {
  margin-top: 30px;
  font-size: 14px;
  color: #aaa;
}

.footer-bottom p {
  margin: 0;
}
  </style>
</head>
<body>

  <!-- Navigation Header -->
  <header>
    <div class="logo"> </div>
    <div class="car">
      <div class="car-top"></div>
      <div class="wheel left"></div>
      <div class="wheel right"></div>
      <div class="gas"></div>  <!-- Gas Puff -->
    </div>

    <!-- Links on the top right -->
    <div class="header-links">
      <a href="#contact-form">Buy</a>
      <a href="#">Sell</a>
      <a href="#">Contact</a>
    </div>
  </header>

  <!-- Section for Pictures and Descriptions -->
  <section style="padding: 40px 20px; margin: 30px 0;">
    <h2 style="text-align: center; font-size: 24px; margin-bottom: 20px; color: red;">LISTINGS</h2>
    
    <div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 20px;">
      <!-- Picture 1: Car Image 1 -->
      <div style="width: 250px; text-align: center;">
        <a href="https://www.lexus.com/models/LC" target="_blank">
          <img src="https://images.pexels.com/photos/1402787/pexels-photo-1402787.jpeg" alt="Car 1" style="width: 100%; border-radius: 8px;">
        </a>
        <p style="font-size: 16px; color: #555; margin-top: 10px;">Lexus LC 500h Coupe</p>
      </div>

      <!-- Picture 2: Car Image 2 -->
      <div style="width: 250px; text-align: center;">
        <a href="https://www.ferrari.com/en-US/auto/roma" target="_blank">
          <img src="https://images.unsplash.com/photo-1602174767803-002bd7a458e6?q=80&w=1170&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Car 2" style="width: 100%; border-radius: 8px;">
        </a>
        <p style="font-size: 16px; color: #555; margin-top: 10px;">Ferrari Roma</p>
      </div>

      <!-- Picture 3: Car Image 3 -->
      <div style="width: 250px; text-align: center;">
        <a href="https://www.tesla.com/model3" target="_blank">
          <img src="https://images.pexels.com/photos/10475772/pexels-photo-10475772.jpeg" alt="Car 3" style="width: 100%; border-radius: 8px;">
        </a>
        <p style="font-size: 16px; color: #555; margin-top: 10px;">Tesla Model 3</p>
      </div>
    </div>
  </section>

  <!-- Contact Form Section -->
  <section id="contact-form" class="contact-form">
    <h2>Get in touch with us if you are looking to Sell</h2>
    <form action="#" method="POST">
      <input type="text" name="name" placeholder="Your Name" required>
      <input type="email" name="email" placeholder="Your Email" required>
      <textarea name="message" rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Submit</button>
    </form>
  </section>

<!-- Footer Section -->
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-info">
        <h3>Contact Us</h3>
        <p>Email: support@example.com</p>
        <p>Phone: +1 234 567 890</p>
        <p>Address: 123 Main Street, City, Country</p>
      </div>

    <div class="footer-links">
        <h3>Quick Links</h3>
        <ul>
          <li><a href="#">About Us</a></li>
          <li><a href="#">Privacy Policy</a></li>
          <li><a href="#">Terms of Service</a></li>
          <li><a href="#">FAQ</a></li>
        </ul>
      </div>

      <div class="footer-social">
        <h3>Follow Us</h3>
        <ul>
          <li><a href="#" class="social-icon">Facebook</a></li>
          <li><a href="#" class="social-icon">Twitter</a></li>
          <li><a href="#" class="social-icon">Instagram</a></li>
          <li><a href="#" class="social-icon">LinkedIn</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2026 Your Website. All Rights Reserved.</p>
    </div>
  </footer>

</body>
</html>

