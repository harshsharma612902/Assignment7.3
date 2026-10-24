The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Product Listing</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="page-header">
        <h1>Featured Products</h1>
        <p>Explore our latest collection. Resize your browser window to watch the cards adapt and wrap automatically!</p>
    </header>

    <!-- Steps 3 & 4: Flexbox Container with Flex-Wrap and Gap -->
    <main class="product-grid">
        
        <!-- Product 1 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?auto=format&fit=crop&q=80&w=400" alt="Wireless Headphones">
            </div>
            <div class="product-info">
                <h3>Wireless Headphones</h3>
                <p class="price">$149.99</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

        <!-- Product 2 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&q=80&w=400" alt="Minimalist Watch">
            </div>
            <div class="product-info">
                <h3>Minimalist Watch</h3>
                <p class="price">$120.00</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

        <!-- Product 3 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f?auto=format&fit=crop&q=80&w=400" alt="Retro Camera">
            </div>
            <div class="product-info">
                <h3>Retro Camera</h3>
                <p class="price">$299.50</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

        <!-- Product 4 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?auto=format&fit=crop&q=80&w=400" alt="Running Sneakers">
            </div>
            <div class="product-info">
                <h3>Running Sneakers</h3>
                <p class="price">$85.00</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

        <!-- Product 5 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1491553895911-0055eca6402d?auto=format&fit=crop&q=80&w=400" alt="Casual Sneakers">
            </div>
            <div class="product-info">
                <h3>Casual Sneakers</h3>
                <p class="price">$75.00</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

        <!-- Product 6 -->
        <article class="product-card">
            <div class="image-container">
                <img src="https://images.unsplash.com/photo-1583394838336-acd977736f90?auto=format&fit=crop&q=80&w=400" alt="Gaming Headset">
            </div>
            <div class="product-info">
                <h3>Gaming Headset</h3>
                <p class="price">$99.99</p>
                <button class="btn">Add to Cart</button>
            </div>
        </article>

    </main>

</body>
</html>
2. The CSS File (style.css)
CSS
/* Global Reset */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f8fafc;
    color: #334155;
    padding: 40px 20px;
    line-height: 1.6;
}

.page-header {
    text-align: center;
    margin-bottom: 40px;
}

.page-header h1 {
    font-size: 2.25rem;
    color: #0f172a;
    margin-bottom: 8px;
}

.page-header p {
    color: #64748b;
    font-size: 1rem;
}

/* Steps 3 & 4: Flexbox Container with Flex-Wrap and Gap */
.product-grid {
    display: flex;
    flex-wrap: wrap;          /* Step 6: Allows cards to wrap to next line when screen shrinks */
    justify-content: center;  /* Centers items nicely on desktop */
    gap: 30px;                /* Step 4: Spacing between cards */
    max-width: 1200px;
    margin: 0 auto;
}

/* Step 5: Product Card with Flex Sizing Properties */
.product-card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    
    /* Step 5: flex-grow, flex-shrink, and flex-basis demonstration */
    flex: 1 1 280px;          
    /* 
      flex-grow: 1 (Cards can grow to fill extra space)
      flex-shrink: 1 (Cards can shrink when space gets tight)
      flex-basis: 280px (Ideal base width before wrapping)
    */
    
    max-width: 350px;         /* Prevents cards from getting too wide on large screens */
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

/* Image Container */
.image-container {
    width: 100%;
    height: 200px;
    background-color: #f1f5f9;
    overflow: hidden;
}

.image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
}

.product-card:hover .image-container img {
    transform: scale(1.05);
}

/* Product Info Section */
.product-info {
    padding: 20px;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: space-between;
}

.product-info h3 {
    font-size: 1.15rem;
    color: #0f172a;
    margin-bottom: 8px;
}

.price {
    font-size: 1.25rem;
    font-weight: 700;
    color: #2563eb;
    margin-bottom: 16px;
}

/* Button Styling */
.btn {
    background-color: #2563eb;
    color: white;
    border: none;
    padding: 10px 16px;
    border-radius: 6px;
    font-weight: 600;
    cursor: pointer;
    text-align: center;
    transition: background-color 0.2s ease;
}

.btn:hover {
    background-color: #1d4ed8;
}