<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>Library System</title>
</head>
<body>
  <nav class="sticky-nav">
    <ul>
      <li><a href="#books">Books</a></li>
      <li><a href="#register">Register</a></li>
    </ul>
  </nav>

  <section id="books">
    <h1>Books</h1>
    <table class="book-table">
      <thead>
        <tr>
          <th>Book ID</th>
          <th>Title</th>
          <th>Author</th>
          <th>Genre</th>
          <th>Availability</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>
            Book Title 1<br>
            <table class="nested-table">
              <tr>
                <td>Publication Date:</td>
                <td>2000</td>
              </tr>
              <tr>
                <td>Page Count:</td>
                <td>250</td>
              </tr>
              <tr>
                <td>ISBN:</td>
                <td>123-4567890123</td>
              </tr>
            </table>
          </td>
          <td>Author Name 1</td>
          <td>Genre 1</td>
          <td>Available</td>
        </tr>
        <tr>
          <td>2</td>
          <td>
            Book Title 2<br>
            <table class="nested-table">
              <tr>
                <td>Publication Date:</td>
                <td>2005</td>
              </tr>
              <tr>
                <td>Page Count:</td>
                <td>300</td>
              </tr>
              <tr>
                <td>ISBN:</td>
                <td>123-4567890456</td>
              </tr>
            </table>
          </td>
          <td>Author Name 2</td>
          <td>Genre 2</td>
          <td>Not Available</td>
        </tr>
        <tr>
          <td>3</td>
          <td>
            Book Title 3<br>
            <table class="nested-table">
              <tr>
                <td>Publication Date:</td>
                <td>2010</td>
              </tr>
              <tr>
                <td>Page Count:</td>
                <td>350</td>
              </tr>
              <tr>
                <td>ISBN:</td>
                <td>123-4567890789</td>
              </tr>
            </table>
          </td>
          <td>Author Name 3</td>
          <td>Genre 3</td>
          <td>Available</td>
        </tr>
      </tbody>
    </table>
  </section>

  <section id="register">
    <h1>Register</h1>
    <form class="registration-form">
      <label for="first-name">First Name:</label>
      <input type="text" id="first-name" name="first-name" required>

      <!-- Other input fields... -->
      
      <label for="age">Age:</label>
      <input type="number" id="age" name="age" min="5" max="100" required>

      <label for="password">Password:</label>
      <input type="password" id="password" name="password" required>

      <label for="confirm-password">Confirm Password:</label>
      <input type="password" id="confirm-password" name="confirm-password" required>

      <button type="submit">Register</button>
    </form>
  </section>

  <script>
    // Smooth scrolling for navigation links
    document.querySelectorAll('nav a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        document.querySelector(this.getAttribute('href')).scrollIntoView({
          behavior: 'smooth'
        });
      });
    });

    // Form validation
    document.querySelector('.registration-form').addEventListener('submit', function (e) {
      const password = document.getElementById('password').value;
      const confirmPassword = document.getElementById('confirm-password').value;

      if (password !== confirmPassword) {
        alert('Passwords do not match');
        e.preventDefault(); // Prevent form submission
      }
    });
  </script>
</body>
</html>
/* Add your general styling here */

.sticky-nav {
  position: sticky;
  top: 0;
  background-color: #333;
  z-index: 100;
}

.sticky-nav ul {
  list-style: none;
  display: flex;
  justify-content: space-around;
  padding: 10px 0;
}

.sticky-nav a {
  text-decoration: none;
  color: white;
}

.sticky-nav a:hover {
  text-decoration: underline;
}

/* Style for the Books table */
.book-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
  border: 1px solid #ccc;
}

.book-table th, .book-table td {
  border: 1px solid #ccc;
  padding: 8px;
  text-align: center;
}

.nested-table {
  border: none;
  width: auto;
}

/* Style for the Registration form */
.registration-form {
  width: 50%;
  margin: auto;
  margin-top: 20px;
  border: 1px solid #ccc;
  padding: 20px;
}

.registration-form label, .registration-form input, .registration-form button {
  display: block;
  margin-bottom: 10px;
}

.registration-form button {
  background-color: #333;
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
}

.registration-form button:hover {
  background-color: #555;
}
