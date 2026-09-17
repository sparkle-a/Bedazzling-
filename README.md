<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luxe Bling Studio | Y2K Aesthetic & Bedazzled Art Canvas UK</title>

    <!-- Payment SDKs -->
    <script src="https://js.stripe.com/v3/"></script>
    <script src="https://www.paypal.com/sdk/js?client-id=YOUR_PAYPAL_CLIENT_ID&currency=GBP"></script>

    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,400&family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary: #ff2a8d;
            --primary-glow: #ff7be5;
            --accent-gold: #ffd700;
            --bg-dark: #0a060e;
            --card-bg: rgba(255, 255, 255, 0.04);
            --card-border: rgba(255, 42, 141, 0.35);
            --text-light: #f8f9fa;
            --text-muted: #d0c3d9;
            --shadow: 0 8px 32px 0 rgba(255, 42, 141, 0.25);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-light);
            background-image: radial-gradient(circle at 50% -20%, #4a0d33 0%, #0a060e 75%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        h1, h2, h3, .logo {
            font-family: 'Playfair Display', serif;
        }

        /* Y2K Sparkle Top Banner */
        .sparkle-bar {
            background: linear-gradient(90deg, #ff007f, #7928ca, #ff007f);
            background-size: 200% auto;
            color: #fff;
            text-align: center;
            font-size: 0.85rem;
            padding: 0.5rem;
            font-weight: 700;
            letter-spacing: 1px;
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        /* Navigation */
        nav {
            background: rgba(10, 6, 14, 0.88);
            backdrop-filter: blur(12px);
            padding: 1.2rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--card-border);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 800;
            background: linear-gradient(45deg, #fff, var(--primary-glow), var(--accent-gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 12px rgba(255, 42, 141, 0.5);
        }

        .nav-links button {
            background: transparent;
            border: 1px solid transparent;
            margin-left: 0.5rem;
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--text-muted);
            cursor: pointer;
            padding: 0.6rem 1.2rem;
            border-radius: 25px;
            transition: all 0.3s ease;
        }

        .nav-links button:hover, .nav-links button.active {
            background: rgba(255, 42, 141, 0.2);
            border-color: var(--primary);
            color: #fff;
            box-shadow: 0 0 15px rgba(255, 42, 141, 0.5);
        }

        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        .section {
            display: none;
            animation: fadeIn 0.4s ease-in-out;
        }

        .section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Hero */
        .hero {
            text-align: center;
            padding: 4rem 2rem;
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid var(--card-border);
            border-radius: 20px;
            margin-bottom: 3rem;
            box-shadow: var(--shadow);
        }

        .hero h1 {
            font-size: 3.2rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, var(--primary-glow));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 700px;
            margin: 0 auto 1.5rem auto;
        }

        /* Product Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: 16px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 42, 141, 0.4);
        }

        /* RHINESTONE / BEDAZZLED IMAGE OVERLAY EFFECT */
        .img-container {
            position: relative;
            width: 100%;
            height: 260px;
            overflow: hidden;
        }

        .img-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Animated Sparkle Effect on Pictures */
        .img-container::after {
            content: "✨";
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 1.5rem;
            text-shadow: 0 0 10px #fff, 0 0 20px var(--primary);
            animation: sparklePulse 2s infinite ease-in-out;
        }

        .img-container::before {
            content: "";
            position: absolute;
            top: 0; left: -100%;
            width: 60%; height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.35), transparent);
            transform: skewX(-25deg);
            animation: shimmerEffect 4s infinite;
        }

        @keyframes shimmerEffect {
            100% { left: 200%; }
        }

        @keyframes sparklePulse {
            0%, 100% { opacity: 0.3; transform: scale(0.9); }
            50% { opacity: 1; transform: scale(1.3); }
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
            color: #fff;
        }

        .product-desc {
            color: var(--text-muted);
            font-size: 0.88rem;
            margin-bottom: 1rem;
            line-height: 1.4;
        }

        .product-price {
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--accent-gold);
            margin-bottom: 1rem;
        }

        .btn {
            display: inline-block;
            width: 100%;
            background: linear-gradient(45deg, var(--primary), #a200ff);
            color: white;
            padding: 0.9rem;
            border: none;
            border-radius: 30px;
            font-size: 0.95rem;
            font-weight: 700;
            letter-spacing: 0.5px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            box-shadow: 0 4px 15px rgba(255, 42, 141, 0.4);
        }

        .btn:hover {
            opacity: 0.95;
            transform: scale(1.02);
            box-shadow: 0 6px 20px rgba(255, 42, 141, 0.7);
        }

        /* Custom Studio Form */
        .custom-studio {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            border-radius: 20px;
            padding: 2.5rem;
            box-shadow: var(--shadow);
            max-width: 750px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--text-light);
            font-weight: 600;
        }

        input[type="text"], input[type="email"], select, textarea {
            width: 100%;
            padding: 0.9rem;
            background: rgba(0,0,0,0.5);
            border: 1px solid var(--card-border);
            border-radius: 10px;
            color: #fff;
            font-size: 0.95rem;
        }

        /* Tracking Form */
        .tracking-card {
            background: var(--card-bg);
            border: 1px solid var(--card-border);
            padding: 3rem 2rem;
            border-radius: 20px;
            max-width: 550px;
            margin: 2rem auto;
            text-align: center;
            box-shadow: var(--shadow);
        }

        /* Admin Table */
        .admin-table {
            width: 100%;
            border-collapse: collapse;
            background: rgba(255, 255, 255, 0.02);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--card-border);
            margin-top: 1.5rem;
        }

        .admin-table th, .admin-table td {
            padding: 1rem;
            text-align: left;
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            font-size: 0.9rem;
        }

        .admin-table th {
            background: rgba(255, 42, 141, 0.25);
            color: #fff;
            font-weight: 700;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(8px);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .modal-content {
            background: #150b1d;
            border: 1px solid var(--card-border);
            padding: 2.5rem;
            border-radius: 20px;
            max-width: 480px;
            width: 90%;
            box-shadow: 0 0 30px rgba(255, 42, 141, 0.4);
        }
    </style>
</head>
<body>

    <div class="sparkle-bar">✨ Y2K RHINESTONE CANVAS PAINTINGS & BESPOKE BEDAZZLED ARTWORK UK ✨</div>

    <!-- Navigation -->
    <nav>
        <div class="logo">💎 Luxe Bling Studio</div>
        <div class="nav-links">
            <button class="active" onclick="showSection('shop')">Boutique & Art</button>
            <button onclick="showSection('custom')">Custom Canvas & Drawings</button>
            <button onclick="showSection('tracking')">Track Parcel</button>
            <button onclick="showSection('admin')">Admin Portal</button>
        </div>
    </nav>

    <div class="container">

        <!-- SHOP SECTION -->
        <div id="shop" class="section active">
            <div class="hero">
                <h1>Y2K Aesthetic & Crystal Canvas Art</h1>
                <p>Hand-crafted 3D rhinestone paintings, pop-art canvases, and iconic Y2K bedazzled fashion piece by piece.</p>
            </div>

            <h2 style="margin-bottom: 1.5rem; font-size: 2rem;">✨ Bedazzled Collection & Canvas Paintings</h2>

            <div class="products-grid">
                <!-- Product 1: Y2K Art Canvas -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1579783902614-a3fb3927b675?w=600&q=80" alt="Y2K Cherry Canvas Painting">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Y2K Pink Cherry & Dice Bedazzled Canvas</div>
                        <p class="product-desc">A3 hand-painted acrylic canvas iced out with over 2,500 pink & silver glass rhinestones.</p>
                        <div class="product-price">£65.00</div>
                        <button class="btn" onclick="openCheckout('Y2K Pink Cherry & Dice Bedazzled Canvas', 65)">Order Canvas</button>
                    </div>
                </div>

                <!-- Product 2: Diet Cola Soda Can Bedazzled Canvas -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1541701494587-cb58502866ab?w=600&q=80" alt="Pop Art Soda Painting">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Diet Cola Pop-Art Rhinestone Canvas</div>
                        <p class="product-desc">Trendy Y2K pop-art canvas painting encrusted with sparkling red & silver gems.</p>
                        <div class="product-price">£55.00</div>
                        <button class="btn" onclick="openCheckout('Diet Cola Pop-Art Rhinestone Canvas', 55)">Order Canvas</button>
                    </div>
                </div>

                <!-- Product 3: Flame & Butterfly Drawing Canvas -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1513519245088-0e12902e5a38?w=600&q=80" alt="Y2K Butterfly Canvas">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Cyber Butterfly Y2K Glitter Portrait</div>
                        <p class="product-desc">Detailed line art drawing covered in iridescent 3D rhinestones & crushed glass effect.</p>
                        <div class="product-price">£85.00</div>
                        <button class="btn" onclick="openCheckout('Cyber Butterfly Y2K Glitter Portrait', 85)">Order Canvas</button>
                    </div>
                </div>

                <!-- Product 4: Bedazzled Heels -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1543163521-1bf539c55dd2?w=600&q=80" alt="Crystal Stilettos">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Cinderella Crystal Stilettos</div>
                        <p class="product-desc">Over 3,000 hand-placed luxury AB glass crystals. Unmatched shine.</p>
                        <div class="product-price">£145.00</div>
                        <button class="btn" onclick="openCheckout('Cinderella Crystal Stilettos', 145)">Order Shoes</button>
                    </div>
                </div>

                <!-- Product 5: Bedazzled Tumbler -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1514228742587-6b1558fcca3d?w=600&q=80" alt="Rhinestone Tumbler">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Y2K Bling Insulated Tumbler 750ml</div>
                        <p class="product-desc">Double-wall thermal flask completely iced out in pink & crystal rhinestones.</p>
                        <div class="product-price">£45.00</div>
                        <button class="btn" onclick="openCheckout('Y2K Bling Insulated Tumbler 750ml', 45)">Order Tumbler</button>
                    </div>
                </div>

                <!-- Product 6: Custom Bedazzled Phone Case -->
                <div class="product-card">
                    <div class="img-container">
                        <img src="https://images.unsplash.com/photo-1580910051074-3eb694886505?w=600&q=80" alt="Bedazzled Phone Case">
                    </div>
                    <div class="product-info">
                        <div class="product-title">Custom Initial Rhinestone Phone Case</div>
                        <p class="product-desc">Heavy-duty case bedazzled with Y2K charm accents & custom initials.</p>
                        <div class="product-price">£38.00</div>
                        <button class="btn" onclick="openCheckout('Custom Initial Rhinestone Phone Case', 38)">Order Case</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- CUSTOMIZATION STUDIO & ART SECTION -->
        <div id="custom" class="section">
            <div class="custom-studio">
                <h2 style="color: var(--primary-glow); margin-bottom: 0.5rem;">🎨 Bedazzle Your Picture & Drawing Art</h2>
                <p style="color: var(--text-muted); margin-bottom: 2rem;">Upload your own drawing, Y2K aesthetic picture, or sketch and select your gem layout. We will paint and bedazzle it on canvas for you!</p>

                <form id="customForm" onsubmit="calculateCustomQuote(event)">
                    <div class="form-group">
                        <label>Select Custom Artwork Type:</label>
                        <select id="customType" onchange="updatePriceEstimate()">
                            <option value="y2k-canvas">Y2K Aesthetic Canvas Painting (A3/A4) - From £65</option>
                            <option value="portrait-art">Custom Bedazzled Portrait Drawing - From £95</option>
                            <option value="shoes-clothing">Custom Sneakers / Jacket Bedazzling - From £90</option>
                            <option value="send-item">Send In Your Own Object to Bedazzle - From £45</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label>Upload Picture, Sketch, or Drawing Reference:</label>
                        <input type="file" id="artFile" accept="image/*">
                    </div>

                    <div class="form-group">
                        <label>Select Y2K Theme Elements:</label>
                        <select id="themeSelect">
                            <option>Pink Cherries & Dice ✨</option>
                            <option>Cyber Flames & Hearts 🔥</option>
                            <option>Playing Card / Lucky Queen 🃏</option>
                            <option>Custom Monogram / Text 💎</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label>Color & Detail Notes:</label>
                        <textarea id="customNotes" rows="3" placeholder="e.g., Use Hot Pink gems for the outline and Silver AB rhinestones for the canvas background..."></textarea>
                    </div>

                    <div style="background: rgba(255,255,255,0.05); padding: 1rem; border-radius: 10px; margin-bottom: 1.5rem; border: 1px solid var(--card-border);">
                        <span style="font-size: 1.1rem;">Estimated Custom Price: </span>
                        <strong id="estimatedPrice" style="color: var(--accent-gold); font-size: 1.4rem;">£65.00</strong>
                    </div>

                    <button type="submit" class="btn">Place Custom Art Order</button>
                </form>
            </div>
        </div>

        <!-- PARCEL TRACKING SECTION -->
        <div id="tracking" class="section">
            <div class="tracking-card">
                <h2 style="color: var(--primary-glow); margin-bottom: 0.5rem;">📦 Track Your Parcel</h2>
                <p style="margin-bottom: 1.5rem; color: var(--text-muted);">Enter your Order ID (e.g. LUXE-1001) or UK Tracking Code.</p>
                
                <input type="text" id="trackingInput" placeholder="Enter Order ID or Parcel Code">
                <button class="btn" style="margin-top: 1rem;" onclick="trackParcel()">Locate Package</button>

                <div id="trackingResult" style="margin-top: 1.5rem; display: none; text-align: left; background: rgba(0,0,0,0.5); border: 1px solid var(--card-border); padding: 1.2rem; border-radius: 10px;">
                </div>
            </div>
        </div>

        <!-- ADMIN DASHBOARD SECTION -->
        <div id="admin" class="section">
            <h2 style="color: var(--primary-glow); margin-bottom: 0.5rem;">👑 Admin Sales & Shipping Dashboard</h2>
            <p style="color: var(--text-muted);">Manage sales, record payment info, and assign parcel tracking links.</p>

            <table class="admin-table">
                <thead>
                    <tr>
                        <th>Order ID</th>
                        <th>Product / Custom Art</th>
                        <th>Amount (£)</th>
                        <th>Customer Email</th>
                        <th>Status</th>
                        <th>Parcel Tracking No.</th>
                    </tr>
                </thead>
                <tbody id="adminOrderTable">
                    <!-- Populated via JavaScript -->
                </tbody>
            </table>
        </div>

    </div>

    <!-- PAYMENT MODAL -->
    <div id="paymentModal" class="modal">
        <div class="modal-content">
            <h3 id="modalProductName" style="color: var(--primary-glow); margin-bottom: 0.5rem;">Product Name</h3>
            <p id="modalProductPrice" style="font-weight: 700; color: var(--accent-gold); font-size: 1.3rem; margin-bottom: 1rem;">Total: £0.00</p>
            
            <div class="form-group">
                <label>Your Email Address (For Order Tracking Updates):</label>
                <input type="email" id="customerEmail" placeholder="e.g. name@example.co.uk" required>
            </div>

            <p style="margin: 1rem 0 0.5rem 0; font-weight: 600;">Select Payment Method:</p>
            
            <button class="btn" style="background: linear-gradient(45deg, #635bfc, #4338ca); margin-bottom: 0.8rem;" onclick="processStripePayment()">Pay via Credit/Debit Card (Stripe)</button>
            
            <div id="paypal-button-container"></div>

            <button class="btn" style="background: transparent; border: 1px solid var(--text-muted); color: var(--text-muted); margin-top: 0.8rem;" onclick="closeCheckout()">Cancel</button>
        </div>
    </div>

    <script>
        // Default Mock Orders in GBP
        let orders = [
            { id: "LUXE-1001", product: "Y2K Pink Cherry Canvas Art", amount: 65, email: "charlotte@example.co.uk", status: "Dispatched", tracking: "RM940011189956UK" },
            { id: "LUXE-1002", product: "Custom Portrait Bedazzled Painting", amount: 95, email: "sophia@example.co.uk", status: "Hand-Bedazzling", tracking: "Pending" }
        ];

        let selectedProduct = null;

        // Initialize Stripe (Replace with your live key)
        const stripe = Stripe('YOUR_STRIPE_PUBLIC_KEY');

        // Navigation
        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(sec => sec.classList.remove('active'));
            document.querySelectorAll('.nav-links button').forEach(btn => btn.classList.remove('active'));
            
            document.getElementById(sectionId).classList.add('active');
            event.target.classList.add('active');

            if(sectionId === 'admin') {
                renderAdminOrders();
            }
        }

        // Custom Pricing Estimate
        function updatePriceEstimate() {
            const type = document.getElementById('customType').value;
            let price = 65;
            if(type === 'portrait-art') price = 95;
            if(type === 'shoes-clothing') price = 90;
            if(type === 'send-item') price = 45;
            
            document.getElementById('estimatedPrice').innerText = `£${price}.00`;
        }

        function calculateCustomQuote(e) {
            e.preventDefault();
            const typeSelect = document.getElementById('customType');
            const typeText = typeSelect.options[typeSelect.selectedIndex].text;
            const estimatedPrice = parseInt(document.getElementById('estimatedPrice').innerText.replace('£', ''));

            openCheckout(`Custom Art: ${typeText}`, estimatedPrice);
        }

        // Checkout Modal
        function openCheckout(name, price) {
            selectedProduct = { name, price };
            document.getElementById('modalProductName').innerText = name;
            document.getElementById('modalProductPrice').innerText = `Total: £${price}.00`;
            document.getElementById('paymentModal').style.display = 'flex';

            renderPayPalButton(price);
        }

        function closeCheckout() {
            document.getElementById('paymentModal').style.display = 'none';
            document.getElementById('paypal-button-container').innerHTML = '';
        }

        // Stripe Payment Processing
        function processStripePayment() {
            const email = document.getElementById('customerEmail').value;
            if(!email) {
                alert('Please enter your email.');
                return;
            }

            const newOrderId = "LUXE-" + Math.floor(1000 + Math.random() * 9000);
            orders.push({
                id: newOrderId,
                product: selectedProduct.name,
                amount: selectedProduct.price,
                email: email,
                status: "Order Received",
                tracking: "Pending"
            });

            alert(`✨ Payment Successful via Stripe! Order ID: ${newOrderId}\nTracking link sent to: ${email}`);
            closeCheckout();
        }

        // PayPal Button Render
        function renderPayPalButton(price) {
            document.getElementById('paypal-button-container').innerHTML = '';
            if (window.paypal) {
                paypal.Buttons({
                    createOrder: function(data, actions) {
                        return actions.order.create({
                            purchase_units: [{
                                amount: { currency_code: 'GBP', value: price.toString() }
                            }]
                        });
                    },
                    onApprove: function(data, actions) {
                        return actions.order.capture().then(function(details) {
                            const email = document.getElementById('customerEmail').value || details.payer.email_address;
                            const newOrderId = "LUXE-" + Math.floor(1000 + Math.random() * 9000);
                            
                            orders.push({
                                id: newOrderId,
                                product: selectedProduct.name,
                                amount: selectedProduct.price,
                                email: email,
                                status: "Order Received",
                                tracking: "Pending"
                            });

                            alert(`✨ Payment Confirmed! Order ID: ${newOrderId}`);
                            closeCheckout();
                        });
                    }
                }).render('#paypal-button-container');
            }
        }

        // Track Parcel
        function trackParcel() {
            const trackingCode = document.getElementById('trackingInput').value.trim();
            const resultBox = document.getElementById('trackingResult');

            if (!trackingCode) {
                alert('Please enter an Order ID or Tracking Code.');
                return;
            }

            const matchedOrder = orders.find(o => o.id.toLowerCase() === trackingCode.toLowerCase() || o.tracking.toLowerCase() === trackingCode.toLowerCase());

            if (matchedOrder) {
                resultBox.style.display = 'block';
                resultBox.innerHTML = `
                    <h4 style="color: var(--primary-glow); margin-bottom: 0.5rem;">Status: ${matchedOrder.status}</h4>
                    <p><strong>Order ID:</strong> ${matchedOrder.id}</p>
                    <p><strong>Item:</strong> ${matchedOrder.product}</p>
                    <p><strong>Tracking #:</strong> ${matchedOrder.tracking}</p>
                `;
            } else {
                window.open(`https://www.17track.net/en/track?nums=${trackingCode}`, '_blank');
            }
        }

        // Admin Table Rendering
        function renderAdminOrders() {
            const tbody = document.getElementById('adminOrderTable');
            tbody.innerHTML = '';

            orders.forEach((order, index) => {
                tbody.innerHTML += `
                    <tr>
                        <td><strong>${order.id}</strong></td>
                        <td>${order.product}</td>
                        <td>£${order.amount}</td>
                        <td>${order.email}</td>
                        <td>
                            <select onchange="updateStatus(${index}, this.value)" style="padding:0.3rem;">
                                <option value="Order Received" ${order.status === 'Order Received' ? 'selected' : ''}>Order Received</option>
                                <option value="Hand-Bedazzling" ${order.status === 'Hand-Bedazzling' ? 'selected' : ''}>Hand-Bedazzling</option>
                                <option value="Dispatched" ${order.status === 'Dispatched' ? 'selected' : ''}>Dispatched</option>
                            </select>
                        </td>
                        <td>
                            <input type="text" value="${order.tracking}" onchange="updateTracking(${index}, this.value)" style="padding:0.3rem; margin:0; width:100%;">
                        </td>
                    </tr>
                `;
            });
        }

        function updateStatus(index, newStatus) {
            orders[index].status = newStatus;
            alert(`Updated ${orders[index].id} status to: ${newStatus}`);
        }

        function updateTracking(index, newTracking) {
            orders[index].tracking = newTracking;
            alert(`Updated tracking for ${orders[index].id} to: ${newTracking}`);
        }
    </script>
</body>
</html>
