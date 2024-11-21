<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Anime Bookstore</title>
  <link rel="stylesheet" href="styles.css">
  <style>
/* Reset default styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  color: #333;
  background-image: url();
}

header {
  background: linear-gradient(90deg, #ff5f6d, #ffc3a0);
  color: white;
  padding: 20px;
  text-align: center;
}

header h1 {
  margin-bottom: 10px;
  font-size: 36px;
  font-weight: bold;
}

nav ul {
  list-style-type: none;
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

nav ul li {
  margin: 0 15px;
}

nav ul li a {
  color: white;
  text-decoration: none;
  font-size: 18px;
  transition: color 0.3s;
}

nav ul li a:hover {
  color: #ff5f6d;
}

/* Cart Icon */
.cart-icon {
  position: fixed;
  top: 20px;
  right: 20px;
  background-color: wheat; /* New color for cart icon */
  color: black;
  padding: 15px;
  border-radius: 50%;
  cursor: pointer;
  font-size: 24px;
  transition: background-color 0.3s;
}

.cart-icon.hover {
  background-color: #4388ff; /* Slightly darker shade when item is added */
}

.cart-icon:hover {
  background-color: #333e5049; /* Lighter orange shade on hover */
}

/* Hero Section */
#hero {
  background: linear-gradient(135deg, #f8cdda, #1f78b5);
  padding: 50px 20px;
  text-align: center;
  color: white;
}

#hero h2 {
  font-size: 36px;
  margin-bottom: 10px;
}

#hero p {
  font-size: 18px;
}

/* Shop Section */
#shop {
  padding: 50px 20px;
  text-align: center;
  background-color: #fff;
}

#shop h2 {
  font-size: 32px;
  margin-bottom: 30px;
  color: #333;
}

.book-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}

.book {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.3s, box-shadow 0.3s;
}

.book:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.book img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}

.book h3 {
  margin: 15px 0;
  font-size: 22px;
  color: #333;
}

.book p {
  font-size: 16px;
  color: #666;
}

/* Add to Cart Button */
.add-to-cart {
  background: linear-gradient(135deg, #ff5f6d, #ffc3a0); /* Gradient background */
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: all 0.3s ease-in-out; /* Smooth transition */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Soft shadow */
  margin-top: 10px;
}

.add-to-cart:hover {
  background: linear-gradient(135deg, #ff9a8b, #ffc3a0); /* Lighter gradient on hover */
  transform: translateY(-5px); /* Slightly move button up */
  box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15); /* Stronger shadow on hover */
}

.add-to-cart:active {
  background: linear-gradient(135deg, #ff5f6d, #ffc3a0); /* Reset gradient on click */
  transform: translateY(2px); /* Slightly move button down on click */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Back to original shadow */
}

.add-to-cart:focus {
  outline: none; /* Remove default outline */
  box-shadow: 0 0 0 3px rgba(255, 95, 109, 0.5); /* Custom focus ring */
}

/* Buy Now Button */
.buy-now {
  background: linear-gradient(135deg, #ff7e5f, #feb47b); /* Gradient background */
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: all 0.3s ease-in-out;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Soft shadow */
  margin-top: 10px;
}

.buy-now:hover {
  background: linear-gradient(135deg, #feb47b, #ff7e5f); /* Lighter gradient on hover */
  transform: translateY(-5px); /* Slightly move button up */
  box-shadow: 0 8px 12px rgba(0, 0, 0, 0.15); /* Stronger shadow on hover */
}

.buy-now:active {
  background: linear-gradient(135deg, #ff7e5f, #feb47b); /* Reset gradient on click */
  transform: translateY(2px); /* Slightly move button down on click */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Back to original shadow */
}

.buy-now:focus {
  outline: none; /* Remove default outline */
  box-shadow: 0 0 0 3px rgba(255, 126, 95, 0.5); /* Custom focus ring */
}

/* Cart Modal */
.cart {
  position: fixed;
  top: 50%;
  right: 20px;
  background-color: white;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
  display: none;
  width: 300px;
  transform: translateY(-50%);
}

.cart h2 {
  font-size: 24px;
  margin-bottom: 20px;
}

.cart ul {
  list-style-type: none;
  padding: 0;
}

.cart ul li {
  margin-bottom: 10px;
  font-size: 16px;
}

.cart button {
  margin-top: 20px;
  background-color: brown;
  color: white;
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.cart button:hover {
  background-color: brown;
}

/* Notification styles */
.notification {
  position: fixed;
  top: 20px; /* Move notification to top */
  left: 50%;
  transform: translateX(-50%);
  background-color: rgb(83, 160, 173); /* Colorful gradient */
  color: black;
  padding: 10px 20px;
  border-radius: 5px;
  font-size: 16px;
  opacity: 1;
  transition: opacity 0.5s ease-out;
  z-index: 9999; /* Ensure it appears above other content */
}

.notification.fade-out {
  opacity: 0;
}

/* Checkout Button */
.checkout-btn {
  background: linear-gradient(135deg, #f0e130, #ff8c00, #f44336); /* Colorful gradient background */
  color: white;
  border: none;
  padding: 15px 30px;
  border-radius: 10px;
  cursor: pointer;
  font-size: 18px;
  font-weight: bold;
  text-transform: uppercase; /* Makes the text stand out */
  transition: all 0.3s ease-in-out; /* Smooth transition */
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1); /* Soft shadow */
  margin-top: 20px;
  width: 100%;
  max-width: 300px;
}

.checkout-btn:hover {
  background: linear-gradient(135deg, #f44336, #ff8c00, #f0e130); /* Lighter gradient on hover */
  transform: translateY(-5px); /* Slightly move button up */
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Stronger shadow on hover */
}

.checkout-btn:active {
  background: linear-gradient(135deg, #f0e130, #ff8c00, #f44336); /* Reset gradient on click */
  transform: translateY(2px); /* Slightly move button down on click */
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1); /* Back to original shadow */
}

.checkout-btn:focus {
  outline: none; /* Remove default outline */
  box-shadow: 0 0 0 3px rgba(240, 225, 48, 0.5); /* Custom focus ring */
}

/* Optional: If you'd like a separate style for disabled buttons */
.checkout-btn:disabled {
  background: #cccccc; /* Grey background when disabled */
  cursor: not-allowed; /* Change cursor to indicate it's disabled */
  box-shadow: none; /* Remove shadow */
}

  </style>
</head>
<body>

  <header>
    <h1>Welcome To The jishnu Anime Store</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#shop">Shop</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <div class="cart-icon" id="cart-icon">🛒</div>

  <section id="hero">
    <h2>Welcome to the Anime Bookstore</h2>
    <p>Your one-stop shop for all things anime manga!</p>
  </section>

  <section id="shop">
    <h2>Available Books</h2>
    <div class="book-grid">
      <!-- Example Book 1 -->
      <div class="book" data-id="1" data-name="Attack on Titan" data-price="350">
        <img src="aoa.jpg" alt="Anime Book 1">
        <h3>Attack on Titan</h3>
        <p>Join Eren Yeager in his quest to defeat the Titans!</p>
        
      
      </div>

      <!-- Example Book 2 -->
      <div class="book" data-id="2" data-name="One Piece" data-price="500">
        <img src="one piece.jpg" alt="Anime Book 2">
        <h3>One Piece</h3>
        <p>Follow Luffy as he searches for the legendary One Piece!</p>
      
        
      </div>

      <!-- New Book -->
      <div class="book" data-id="3" data-name="Jujutsu Kaisen" data-price="450">
        <img src="juju.jpg" alt="Anime Book 3">
        <h3>Jujutsu Kaisen</h3>
        <p>Superheroes in a world where everyone has powers!</p>
        
        
      </div>

      <!-- New Book -->
      <div class="book" data-id="4" data-name="Naruto" data-price="700">
        <img src="naruto.jpg" alt="Anime Book 4">
        <a href="file:///C:/Users/jishn/PycharmProjects/pythonProject/lll.html#" target="_blank">
          <h3>Naruto</h3>
        </a>
        <p>The journey of Naruto Uzumaki, the ninja who dreams of becoming Hokage!</p>

       
      </div>
      <!-- Dragon Ball Book -->
<div class="book" data-id="5" data-name="Dragon Ball" data-price="350">
    <img src="image.png" alt="Anime Book 5">
    <h3>Dragon Ball</h3>
    <p>Follow Goku as he trains to become the strongest fighter in the universe!</p>

   
  </div>
  
  <!-- Bleach Book -->
  <div class="book" data-id="6" data-name="Bleach" data-price="400">
    <img src="bleach.jpg" alt="Anime Book 7">
    <h3>Bleach</h3>
    <p>The story of Ichigo Kurosaki, a substitute Soul Reaper fighting evil spirits!</p>
  
   
  </div>
  
  <!-- Sword Art Online Book -->
  <div class="book" data-id="7" data-name="Sword Art Online" data-price="600">
    <img src="sword.jpg" alt="Anime Book 9">
    <h3>Sword Art Online</h3>
    <p>A virtual world where players must survive the game to escape!</p>
  
  
  </div>
  <!-- Fullmetal Alchemist Book -->
<div class="book" data-id="10" data-name="Fullmetal Alchemist" data-price="1000">
    <img src="full metal.jpg" alt="Anime Book 10">
    <h3>Fullmetal Alchemist</h3>
    <p>Two brothers searching for the Philosopher's Stone to restore their bodies!</p>
    
   
  </div>
  
  <!-- Tokyo Revengers Book -->
  <div class="book" data-id="11" data-name="Tokyo Revengers" data-price="350">
    <img src="revengers.jpg" alt="Anime Book 11">
    <h3>Tokyo Revengers</h3>
    <p>A man who travels back in time to save his friends and change the future.</p>
    
  
  </div>
  
  <!-- My Hero Academia Book -->
  <div class="book" data-id="12" data-name="My Hero Academia" data-price="400">
    <img src="hero.jpg" alt="Anime Book 12">
    <h3>My Hero Academia</h3>
    <p>Join Izuku Midoriya in a world where everyone has a superpower!</p>
  
    
  </div>
  
  <!-- Neon Genesis Evangelion Book -->
  <div class="book" data-id="13" data-name="Neon Genesis Evangelion" data-price="500">
    <img src="neon.jpg" alt="Anime Book 13">
    <h3>Neon Genesis Evangelion</h3>
    <p>Futuristic mecha battles in a world on the brink of apocalypse.</p>
    
   
  </div>
  
  <!-- Attack on Titan - Vol. 2 Book -->
  <div class="book" data-id="14" data-name="Attack on Titan - Vol. 2" data-price="600">
    <img src="vol2.jpg" alt="Anime Book 14">
    <h3>Attack on Titan - Vol. 2</h3>
    <p>The battle against the Titans intensifies as new alliances form!</p>
    
    
  </div>
  <!-- Black Clover -->
<div class="book" data-id="15" data-name="Black Clover" data-price="1000">
    <img src="black.jpg" alt="Anime Book 15">
    <h3>Black Clover</h3>
    <p>Follow Asta, a boy born without magic in a magical world!</p>
    
    
</div>

<!-- Death Note -->
<div class="book" data-id="16" data-name="Death Note" data-price="350">
    <img src="note.jpg" alt="Anime Book 16">
    <h3>Death Note</h3>
    <p>A high school student discovers a notebook with the power to kill anyone whose name is written in it.</p>
  
    
</div>

<!-- D.Gray-man -->
<div class="book" data-id="17" data-name="D.Gray-man" data-price="400">
    <img src="nam.jpg" alt="Anime Book 17">
    <h3>D.Gray-man</h3>
    <p>Exorcists battle against the forces of evil!</p>
  
   
</div>

<!-- Naruto Shippuden -->
<div class="book" data-id="18" data-name="Naruto Shippuden" data-price="500">
    <img src="ship.jpg" alt="Anime Book 18">
    <h3>Naruto Shippuden</h3>
    <p>The next chapter in Naruto Uzumaki’s journey to become the greatest ninja!</p>

    
</div>

<!-- Fairy Tail -->
<div class="book" data-id="19" data-name="Fairy Tail" data-price="600">
    <img src="tail.jpg" alt="Anime Book 19">
    <h3>Fairy Tail</h3>
    <p>Follow Natsu Dragneel and his guild, Fairy Tail, on their magical adventures!</p>
    
  
    
</div>

<!-- Hunter x Hunter -->
<div class="book" data-id="20" data-name="Hunter x Hunter" data-price="1000">
    <img src="hunter.jpeg" alt="Anime Book 20">
    <h3>Hunter x Hunter</h3>
    <p>Gon Freecss aspires to become a Hunter and find his father!</p>
    
    
</div>

<!-- Bleach: Thousand-Year Blood War -->
<div class="book" data-id="22" data-name="Bleach: Thousand-Year Blood War" data-price="350">
    <img src="bt.jpg" alt="Anime Book 22">
    <h3>Bleach: Thousand-Year Blood War</h3>
    <p>The war between Soul Reapers and the Quincy begins! A thrilling new chapter!</p>
    
    
</div>

<!-- Vagabond -->
<div class="book" data-id="23" data-name="Vagabond" data-price="400">
    <img src="vaga.jpg" alt="Anime Book 23">
    <h3>Vagabond</h3>
    <p>The epic story of the legendary swordsman, Miyamoto Musashi!</p>
    
   
</div>

<!-- Tokyo Ghoul:re -->
<div class="book" data-id="24" data-name="Tokyo Ghoul:re" data-price="500">
    <img src="tokyo ghoul.jpg" alt="Anime Book 24">
    <h3>Tokyo Ghoul:re</h3>
    <p>Follow the journey of the new generation of ghouls and the CCG’s fight against them.</p>
    
    
</div>

<!-- Boku no Hero Academia -->
<div class="book" data-id="25" data-name="Boku no Hero Academia" data-price="600">
    <img src="my hero.jpg" alt="Anime Book 25">
    <h3>Boku no Hero Academia</h3>
    <p>Discover the inspiring story of a boy born without powers in a world full of them!</p>
    
   
</div>

<!-- Black Lagoon -->
<div class="book" data-id="26" data-name="Black Lagoon" data-price="1000">
    <img src="black.jpg" alt="Anime Book 26">
    <h3>Black Lagoon</h3>
    <p>A group of mercenaries live in a world of blood, violence, and betrayal!</p>
    
  
</div>

<!-- JoJo's Bizarre Adventure -->
<div class="book" data-id="27" data-name="JoJo's Bizarre Adventure" data-price="350">
    <img src="jojo.jpg" alt="Anime Book 27">
    <h3>JoJo's Bizarre Adventure</h3>
    <p>A supernatural epic filled with unique characters and epic battles!</p>
    
   button>
</div>

<!-- Sailor Moon -->
<div class="book" data-id="28" data-name="Sailor Moon" data-price="400">
    <img src="moon.jpg" alt="Anime Book 28">
    <h3>Sailor Moon</h3>
    <p>Follow Usagi Tsukino as she transforms into the magical warrior, Sailor Moon!</p>
    
    
</div>

<!-- Dragon Ball Super -->
<div class="book" data-id="29" data-name="Dragon Ball Super" data-price="500">
    <img src="super.jpg" alt="Anime Book 29">
    <h3>Dragon Ball Super</h3>
    <p>Goku uses the Dragon Balls to summon Shenron and learns that a ritual is performed to make the Super Saiyan God</p>
    
    
</div>

    </div>
  </section>

  <div class="cart" id="cart">
    <h2>Shopping Cart</h2>
    <ul class="cart-items"></ul>
    <p>Total: ₹<span id="cart-total">0.00</span></p>
    <button id="checkout" disabled>Checkout</button>
  </div>

  <footer>
    <p>&copy; 2024 Anime Bookstore. All rights reserved.</p>
  </footer>

  <script>
  // Initialize an empty cart
let cart = [];

// Function to update the cart display
function updateCart() {
  const cartItemsList = document.querySelector('.cart-items');
  const cartTotal = document.getElementById('cart-total');
  const checkoutButton = document.getElementById('checkout');

  cartItemsList.innerHTML = '';
  let total = 0;

  cart.forEach(item => {
    const li = document.createElement('li');
    li.textContent = `${item.name} x${item.quantity} - ₹${(item.price * item.quantity).toFixed(2)}`;
    cartItemsList.appendChild(li);
    total += item.price * item.quantity;
  });

  cartTotal.textContent = total.toFixed(2);
  checkoutButton.disabled = cart.length === 0;
}

// Function to handle adding items to the cart
function addToCart(id, name, price) {
  const existingItem = cart.find(item => item.id === id);
  if (existingItem) {
    existingItem.quantity++;
  } else {
    cart.push({ id, name, price, quantity: 1 });
  }
  updateCart();
  showNotification(name); // Show notification when item is added
  document.getElementById('cart').style.display = 'none'; // Close cart modal
}

// Function to show a notification when an item is added to the cart
function showNotification(itemName) {
  const notification = document.createElement('div');
  notification.classList.add('notification');
  notification.textContent = `${itemName} has been added to your cart!`;
  
  document.body.appendChild(notification);

  setTimeout(() => {
    notification.classList.add('fade-out');
    setTimeout(() => {
      notification.remove();
    }, 500); // Duration to wait before removing the notification
  }, 2000); // Notification stays for 2 seconds
}

// Cart Icon click event to toggle the cart visibility
document.getElementById('cart-icon').addEventListener('click', () => {
  const cartModal = document.getElementById('cart');
  cartModal.style.display = cartModal.style.display === 'none' || cartModal.style.display === '' ? 'block' : 'none';
});

// Checkout Button event
document.getElementById('checkout').addEventListener('click', () => {
  alert('Thank you for your purchase from anime store books!');
  cart = [];  // Empty cart after checkout
  updateCart();
  document.getElementById('cart').style.display = 'none';
});

// Add event listeners for the "Add to Cart" buttons
document.querySelectorAll('.add-to-cart').forEach(button => {
  button.addEventListener('click', (event) => {
    const bookElement = event.target.closest('.book');
    const id = bookElement.getAttribute('data-id');
    const name = bookElement.getAttribute('data-name');
    const price = parseFloat(bookElement.getAttribute('data-price'));

    addToCart(id, name, price);
  });
});

// Event listener for "Buy Now" buttons
document.querySelectorAll('.buy-now').forEach(button => {
  button.addEventListener('click', (event) => {
    const bookElement = event.target.closest('.book');
    const id = bookElement.getAttribute('data-id');
    const name = bookElement.getAttribute('data-name');
    const price = parseFloat(bookElement.getAttribute('data-price'));

    // Optionally, add to cart and proceed to checkout
    addToCart(id, name, price);
    alert('Proceeding to checkout...');
  });
});

// Close the cart when clicking outside of it
document.addEventListener('click', (event) => {
  const cartModal = document.getElementById('cart');
  const cartIcon = document.getElementById('cart-icon');

  // Check if the click happened outside the cart modal and the cart icon
  if (!cartModal.contains(event.target) && event.target !== cartIcon) {
    cartModal.style.display = 'none'; // Close the cart
  }
});


</script>
</body>
</html>

