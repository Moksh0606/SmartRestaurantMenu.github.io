# SmartRestaurantMenu.github.io
<!DOCTYPE html> 
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>MAD Restaurant — Flipbook Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
  :root{
    --accent:#9c7b56;
    --accent-dark:#7e6645;
    --page-bg:#fffdf9;
    --muted:#666;
    --soft:#f5efe6;
    --light-gold: #f5f1e8;
    --border-color: #e8e2d5;
    --text-color:#333;
    --heading-color:#4b2e1e;
    --background: linear-gradient(180deg,#faf7f3,#f5efe6);
    
    /* Dark mode variables */
    --dark-bg: #1a1a1a;
    --dark-page-bg: #2d2d2d;
    --dark-text: #e0e0e0;
    --dark-heading: #f0f0f0;
    --dark-muted: #a0a0a0;
    --dark-soft: #3a3a3a;
    --dark-border: #444444;
    --dark-accent: #b8956f;
    --dark-accent-dark: #9c7b56;
  }

  *{box-sizing:border-box;margin:0;padding:0}
  html,body{height:100%}
  body{
    font-family: 'Montserrat',sans-serif;
    background: var(--background);
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    gap:18px;
    padding:20px;
    min-height:100vh;
    color:var(--text-color);
    transition: background-color 0.3s ease, color 0.3s ease;
  }

  /* Dark mode styles */
  body.dark-mode {
    background: linear-gradient(180deg,#1a1a1a,#2d2d2d);
    color: var(--dark-text);
  }

  body.dark-mode .page {
    background: var(--dark-page-bg);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .page h2 {
    color: var(--dark-heading);
  }

  body.dark-mode .page h2::after {
    background: var(--dark-accent);
  }

  body.dark-mode .item {
    background: var(--dark-soft);
    border-left-color: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .info .name {
    color: var(--dark-text);
  }

  body.dark-mode .info .name::before {
    background-color: var(--dark-accent);
  }

  body.dark-mode .info .desc {
    color: var(--dark-muted);
  }

  body.dark-mode .info .meta {
    color: var(--dark-accent);
  }

  body.dark-mode .controls button {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .controls button:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .controls button:disabled {
    background: #555;
    color: #888;
  }

  body.dark-mode .controls .menu-btn,
  body.dark-mode .controls .email-btn {
    background: transparent;
    border-color: var(--dark-accent);
    color: var(--dark-accent);
  }

  body.dark-mode .controls .menu-btn:hover,
  body.dark-mode .controls .email-btn:hover {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .controls .menu-btn:disabled,
  body.dark-mode .controls .email-btn:disabled {
    background: transparent;
    border-color: #555;
    color: #888;
  }

  body.dark-mode .cart-icon {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .cart-icon:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .notification {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .notification.error {
    background: #e74c3c;
  }

  body.dark-mode .notification.success {
    background: #2ecc71;
  }

  body.dark-mode .order {
    background: var(--dark-page-bg);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .order header {
    color: var(--dark-heading);
  }

  body.dark-mode .order label {
    color: var(--dark-text);
  }

  body.dark-mode .order input[type="text"], 
  body.dark-mode .order input[type="number"], 
  body.dark-mode .order textarea {
    background-color: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .order .confirm {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .order .confirm:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .bill-content .customer-info {
    background: var(--dark-soft);
    border-color: var(--dark-border);
  }

  body.dark-mode .bill-content .customer-info h3 {
    color: var(--dark-heading);
  }

  body.dark-mode .bill-item {
    border-color: var(--dark-border);
  }

  body.dark-mode .bill-total {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .empty-cart {
    color: var(--dark-muted);
  }

  body.dark-mode .empty-cart i {
    color: var(--dark-accent);
  }

  body.dark-mode .email-confirm-content,
  body.dark-mode .email-sending-content,
  body.dark-mode .email-success-content,
  body.dark-mode .confirm-dialog-content {
    background: var(--dark-page-bg);
    color: var(--dark-text);
  }

  body.dark-mode .email-confirm-content h3,
  body.dark-mode .email-sending-content h3,
  body.dark-mode .email-success-content h3,
  body.dark-mode .confirm-dialog h3 {
    color: var(--dark-heading);
  }

  body.dark-mode .email-confirm-content p,
  body.dark-mode .email-sending-content p,
  body.dark-mode .email-success-content p,
  body.dark-mode .confirm-dialog p {
    color: var(--dark-muted);
  }

  body.dark-mode .email-confirm-content .email-preview,
  body.dark-mode .email-success-content .email-details {
    background: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .email-confirm-buttons .email-send,
  body.dark-mode .confirm-dialog .confirm-yes {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .email-confirm-buttons .email-send:hover,
  body.dark-mode .confirm-dialog .confirm-yes:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .email-confirm-buttons .email-cancel,
  body.dark-mode .confirm-dialog .confirm-no {
    background: #444;
    color: var(--dark-text);
  }

  body.dark-mode .email-confirm-buttons .email-cancel:hover,
  body.dark-mode .confirm-dialog .confirm-no:hover {
    background: #555;
  }

  body.dark-mode .email-sending-content i {
    color: var(--dark-accent);
  }

  body.dark-mode .email-sending-content .progress-bar {
    background: #444;
  }

  body.dark-mode .email-sending-content .progress-fill {
    background: var(--dark-accent);
  }

  body.dark-mode .email-success-content i {
    color: #2ecc71;
  }

  body.dark-mode .email-success-content button {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .email-success-content button:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .welcome-content,
  body.dark-mode .thank-you-content,
  body.dark-mode .credits-content {
    color: var(--dark-text);
  }

  body.dark-mode .welcome-content::before,
  body.dark-mode .welcome-content::after,
  body.dark-mode .thank-you-content::before,
  body.dark-mode .thank-you-content::after,
  body.dark-mode .credits-content::before,
  body.dark-mode .credits-content::after {
    color: var(--dark-accent);
  }

  body.dark-mode .restaurant-name {
    color: var(--dark-heading);
  }

  body.dark-mode .restaurant-name::before,
  body.dark-mode .restaurant-name::after {
    background: var(--dark-accent);
  }

  body.dark-mode .restaurant-name .subtitle {
    color: var(--dark-accent);
  }

  body.dark-mode .quick-links h2 {
    color: var(--dark-heading);
  }

  body.dark-mode .link-button {
    background: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .link-button::before {
    background: var(--dark-accent);
  }

  body.dark-mode .link-button:hover {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .link-button h3 {
    color: var(--dark-heading);
  }

  body.dark-mode .link-button p {
    color: var(--dark-muted);
  }

  body.dark-mode .thank-you-content h2,
  body.dark-mode .credits-content h2 {
    color: var(--dark-accent);
  }

  body.dark-mode .thank-you-content .highlight,
  body.dark-mode .credits-content .highlight {
    color: var(--dark-accent);
  }

  body.dark-mode .thank-you-content .highlight::before,
  body.dark-mode .thank-you-content .highlight::after,
  body.dark-mode .credits-content .highlight::before,
  body.dark-mode .credits-content .highlight::after {
    color: var(--dark-accent);
  }

  body.dark-mode .thank-you-content .social-links a,
  body.dark-mode .credits-content .social-links a {
    color: var(--dark-accent);
  }

  body.dark-mode .thank-you-content .social-links a:hover,
  body.dark-mode .credits-content .social-links a:hover {
    color: var(--dark-accent-dark);
  }

  body.dark-mode .personal-details h2,
  body.dark-mode .review-section h2 {
    color: var(--dark-heading);
  }

  body.dark-mode .personal-details .intro-text {
    color: var(--dark-muted);
  }

  body.dark-mode .personal-form,
  body.dark-mode .review-form {
    background: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .form-group label {
    color: var(--dark-text);
  }

  body.dark-mode .form-group input,
  body.dark-mode .form-group select,
  body.dark-mode .review-form textarea {
    background-color: var(--dark-page-bg);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .form-group input:focus,
  body.dark-mode .form-group select:focus,
  body.dark-mode .review-form textarea:focus {
    border-color: var(--dark-accent);
    box-shadow: 0 0 0 2px rgba(184, 149, 111, 0.2);
  }

  body.dark-mode .error-message {
    color: #e74c3c;
  }

  body.dark-mode .star {
    color: #555;
  }

  body.dark-mode .star:hover,
  body.dark-mode .star.active {
    color: var(--dark-accent);
  }

  body.dark-mode .success-message {
    background-color: #2ecc7133;
    color: #2ecc71;
    border: 1px solid #2ecc71;
  }

  body.dark-mode .payment-content h2 {
    color: var(--dark-heading);
  }

  body.dark-mode .payment-content h2::after {
    background: var(--dark-accent);
  }

  body.dark-mode .payment-intro {
    color: var(--dark-muted);
  }

  body.dark-mode .payment-option {
    background: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .payment-option::before {
    background: var(--dark-accent);
  }

  body.dark-mode .payment-option:hover {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .payment-option:hover .payment-icon i {
    color: var(--dark-text);
  }

  body.dark-mode .payment-option:hover .payment-details h3,
  body.dark-mode .payment-option:hover .payment-details p {
    color: var(--dark-text);
  }

  body.dark-mode .payment-icon i {
    color: var(--dark-accent);
  }

  body.dark-mode .payment-details h3 {
    color: var(--dark-heading);
  }

  body.dark-mode .payment-details p {
    color: var(--dark-muted);
  }

  body.dark-mode .payment-form {
    background: var(--dark-soft);
    border-color: var(--dark-border);
    color: var(--dark-text);
  }

  body.dark-mode .payment-form h3 {
    color: var(--dark-heading);
  }

  body.dark-mode .payment-form h3::after {
    background: var(--dark-accent);
  }

  body.dark-mode .payment-form-buttons .cancel-btn {
    background: #444;
    color: var(--dark-text);
  }

  body.dark-mode .payment-form-buttons .cancel-btn:hover {
    background: #555;
  }

  body.dark-mode .payment-form-buttons .confirm-btn {
    background: var(--dark-accent);
    color: var(--dark-text);
  }

  body.dark-mode .payment-form-buttons .confirm-btn:hover {
    background: var(--dark-accent-dark);
  }

  body.dark-mode .qr-placeholder {
    background: var(--dark-page-bg);
    border-color: var(--dark-accent);
  }

  body.dark-mode .qr-placeholder i {
    color: var(--dark-accent);
  }

  body.dark-mode .upi-instructions {
    color: var(--dark-muted);
  }

  body.dark-mode .upi-id {
    color: var(--dark-accent);
  }

  /* Loading indicator */
  .loading-indicator {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background: rgba(156, 123, 86, 0.2);
    z-index: 10000;
    display: none;
  }
  
  .loading-bar {
    height: 100%;
    background: var(--accent);
    width: 0;
    transition: width 0.3s ease;
  }

  /* Dark mode toggle button */
  .dark-mode-toggle {
    position: fixed;
    top: 20px;
    left: 20px;
    background: var(--accent);
    color: white;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2rem;
    cursor: pointer;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    z-index: 1000;
    transition: all 0.3s ease;
  }
  
  .dark-mode-toggle:hover {
    background: var(--accent-dark);
    transform: scale(1.05);
  }
  
  body.dark-mode .dark-mode-toggle {
    background: var(--dark-accent);
  }
  
  body.dark-mode .dark-mode-toggle:hover {
    background: var(--dark-accent-dark);
  }

  /* BOOK */
  .book {
    width:92vw;
    max-width:1100px;
    height:80vh;
    max-height:820px;
    perspective:2200px;
    position:relative;
    margin-bottom:8px;
  }

  .page{
    width:100%;
    height:100%;
    position:absolute;
    top:0; left:0;
    background:var(--page-bg);
    border-radius:14px;
    box-shadow: 0 14px 40px rgba(0,0,0,0.18);
    padding:34px;
    overflow:hidden;
    transform-origin:left center;
    backface-visibility:hidden;
    transform-style:preserve-3d;
    transition: transform 1400ms cubic-bezier(.4,.2,.2,1), box-shadow 300ms;
    display:flex;
    flex-direction:column;
    border: 1px solid var(--border-color);
    background-image:
      linear-gradient(to right, rgba(248,245,240,0.8) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(248,245,240,0.8) 1px, transparent 1px);
    background-size: 20px 20px;
  }

  body.dark-mode .page {
    background-image:
      linear-gradient(to right, rgba(60, 60, 60, 0.3) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(60, 60, 60, 0.3) 1px, transparent 1px);
  }

  .page h2{
    font-family:'Playfair Display',serif;
    font-size:1.9rem;
    margin-bottom:20px;
    color:var(--heading-color);
    padding-bottom:12px;
    position: relative;
    text-align: center;
  }

  .page h2::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 60px;
    height: 2px;
    background: var(--accent);
  }

  .page .content {
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap:22px;
    align-content:start;
    margin-top:6px;
    overflow-y: auto;
    padding-right: 10px;
  }

  .item{
    display:flex;
    gap:14px;
    align-items:flex-start;
    background: var(--light-gold);
    border-radius:12px;
    padding:12px;
    cursor:pointer;
    box-shadow: 0 3px 12px rgba(0,0,0,0.06);
    transition: transform .18s ease, box-shadow .18s;
    border-left: 3px solid var(--accent);
  }
  .item:hover { transform: translateY(-6px); box-shadow:0 12px 28px rgba(0,0,0,0.12); }

  .thumb{
    width:98px;
    height:82px;
    flex-shrink:0;
    border-radius:10px;
    object-fit:cover;
    background: #eee;
    border: 1px solid var(--border-color);
  }

  body.dark-mode .thumb {
    background: #444;
    border-color: var(--dark-border);
  }

  .info .name{
    font-weight:600;
    font-size:1.03rem;
    margin-bottom:6px;
    color:#353535;
    display: flex;
    align-items: center;
  }
 
  .info .name::before {
    content: "";
    display: inline-block;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background-color: var(--accent);
    margin-right: 8px;
  }
 
  .info .desc{
    font-size:.89rem;
    color:var(--muted);
    margin-bottom:8px;
    font-style:italic;
    line-height: 1.4;
  }
 
  .info .meta{
    font-weight:700;
    color:var(--accent);
    font-size:1rem;
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
 
  .info .meta::before {
    content: "₹";
    margin-right: 2px;
  }

  /* Flip state */
  .page.flipped{
    transform: rotateY(-180deg);
    pointer-events:none;
  }

  /* stacking — higher pages should be on top initially */
  .page[data-index="0"]{ z-index:150; }
  .page[data-index="1"]{ z-index:140; }
  .page[data-index="2"]{ z-index:130; }
  .page[data-index="3"]{ z-index:120; }
  .page[data-index="4"]{ z-index:110; }
  .page[data-index="5"]{ z-index:100; }
  .page[data-index="6"]{ z-index:90; }
  .page[data-index="7"]{ z-index:80; }
  .page[data-index="8"]{ z-index:70; }
  .page[data-index="9"]{ z-index:60; }
  .page[data-index="10"]{ z-index:50; }
  .page[data-index="11"]{ z-index:40; }
  .page[data-index="12"]{ z-index:30; }
  .page[data-index="13"]{ z-index:20; }
  .page[data-index="14"]{ z-index:15; }
  .page[data-index="15"]{ z-index:10; }
  .page[data-index="16"]{ z-index:5; }

  /* controls area inside each page (bottom center) */
  .controls{
    display:flex;
    gap:14px;
    justify-content:center;
    margin-top:18px;
    flex-shrink:0;
  }
  .controls button{
    padding:10px 22px;
    border-radius:24px;
    border:0;
    background:var(--accent);
    color:white;
    font-weight:600;
    cursor:pointer;
    box-shadow: 0 6px 18px rgba(0,0,0,0.08);
    transition: all 0.3s ease;
  }
  .controls button:hover{
    background:var(--accent-dark);
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(0,0,0,0.12);
  }
  .controls button:disabled{
    opacity:0.45;
    cursor:not-allowed;
    background: #cfc1ae;
    box-shadow:none;
    transform: none;
  }

  /* Menu button styles */
  .controls .menu-btn {
    background: transparent;
    border: 2px solid var(--accent);
    color: var(--accent);
  }
  
  .controls .menu-btn:hover {
    background: var(--accent);
    color: white;
  }
  
  .controls .menu-btn:disabled {
    opacity: 0.45;
    cursor: not-allowed;
    background: transparent;
    border-color: #cfc1ae;
    color: #cfc1ae;
  }

  /* Email button styles */
  .controls .email-btn {
    background: transparent;
    border: 2px solid var(--accent);
    color: var(--accent);
  }
  
  .controls .email-btn:hover {
    background: var(--accent);
    color: white;
  }

  /* Cart icon */
  .cart-icon {
    position: fixed;
    top: 20px;
    right: 20px;
    background: var(--accent);
    color: white;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2rem;
    cursor: pointer;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    z-index: 1000;
    transition: all 0.3s ease;
  }
  
  .cart-icon:hover {
    background: var(--accent-dark);
    transform: scale(1.05);
  }
  
  .cart-count {
    position: absolute;
    top: -5px;
    right: -5px;
    background: #e74c3c;
    color: white;
    width: 22px;
    height: 22px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    font-weight: bold;
  }

  /* Notification styles */
  .notification {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background: var(--accent);
    color: white;
    padding: 12px 20px;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    z-index: 10000;
    display: flex;
    align-items: center;
    gap: 10px;
    transform: translateY(100px);
    opacity: 0;
    transition: transform 0.3s ease, opacity 0.3s ease;
    max-width: 350px;
  }
  
  .notification.show {
    transform: translateY(0);
    opacity: 1;
  }
  
  .notification i {
    font-size: 1.2rem;
  }
  
  .notification.error {
    background: #e74c3c;
  }
  
  .notification.success {
    background: #2ecc71;
  }

  /* order popup */
  .overlay{
    position:fixed; inset:0; background:rgba(0,0,0,0.32);
    display:none; align-items:center; justify-content:center; z-index:9999;
  }
  .order{
    background:white; border-radius:12px; padding:20px; width:360px;
    box-shadow:0 18px 60px rgba(0,0,0,0.35);
    border: 1px solid var(--border-color);
  }
  .order header{
    font-family:'Playfair Display',serif;
    font-size:1.25rem;
    margin-bottom:8px;
    color:#3d2b22;
    text-align: center;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--border-color);
  }
  .order label{
    display:block;
    font-weight:600;
    margin-top:8px;
    color:#555;
  }
  .order input[type="text"], .order input[type="number"], .order textarea{
    width:100%;
    padding:8px 10px;
    border-radius:8px;
    border:1.2px solid var(--border-color);
    margin-top:6px;
    background-color: var(--light-gold);
  }
  .order .row{
    display:flex;
    gap:10px;
    margin-top:12px;
  }
  .order button{
    padding:10px 16px;
    border-radius:10px;
    border:0;
    font-weight:600;
    cursor:pointer;
    transition: all 0.3s ease;
  }
  .order .confirm{
    background:var(--accent);
    color:#fff;
  }
  .order .confirm:hover {
    background: var(--accent-dark);
  }
  .order .cancel{
    background:#ddd;
    color:#333;
  }
  .order .cancel:hover {
    background: #ccc;
  }

  /* Bill page styles */
  .bill-content {
    display: flex;
    flex-direction: column;
    height: calc(100% - 80px);
    padding: 10px 0;
  }
  
  .bill-header {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .bill-header h2 {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    color: var(--accent);
    margin-bottom: 10px;
  }
  
  .customer-info {
    background: var(--light-gold);
    padding: 15px;
    border-radius: 10px;
    margin-bottom: 20px;
  }
  
  .customer-info h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    margin-bottom: 10px;
    color: #4b2e1e;
  }
  
  .customer-info p {
    margin: 5px 0;
    font-size: 1rem;
  }
  
  .bill-items {
    flex-grow: 1;
    overflow-y: auto;
    margin-bottom: 20px;
  }
  
  .bill-item {
    display: flex;
    justify-content: space-between;
    padding: 12px 15px;
    border-bottom: 1px solid var(--border-color);
  }
  
  .bill-item:last-child {
    border-bottom: none;
  }
  
  .item-details {
    flex-grow: 1;
  }
  
  .item-name {
    font-weight: 600;
    margin-bottom: 5px;
  }
  
  .item-notes {
    font-size: 0.85rem;
    color: var(--muted);
    font-style: italic;
  }
  
  .item-price {
    font-weight: 700;
    color: var(--accent);
  }
  
  .bill-total {
    background: var(--accent);
    color: white;
    padding: 15px;
    border-radius: 10px;
    text-align: center;
    font-size: 1.2rem;
    font-weight: 700;
    margin-top: auto;
  }
  
  .empty-cart {
    text-align: center;
    padding: 40px 20px;
    color: var(--muted);
  }
  
  .empty-cart i {
    font-size: 3rem;
    margin-bottom: 15px;
    color: var(--accent);
  }

  /* Email confirmation dialog */
  .email-confirm-dialog {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 10001;
  }
  
  .email-confirm-content {
    background: white;
    border-radius: 12px;
    padding: 25px;
    max-width: 450px;
    width: 90%;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    text-align: center;
  }
  
  .email-confirm-content h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    margin-bottom: 15px;
    color: #4b2e1e;
  }
  
  .email-confirm-content p {
    margin-bottom: 20px;
    color: #666;
    line-height: 1.5;
  }
  
  .email-confirm-content .email-preview {
    background: var(--light-gold);
    padding: 15px;
    border-radius: 8px;
    text-align: left;
    margin-bottom: 20px;
    font-family: monospace;
    font-size: 0.9rem;
    border: 1px solid var(--border-color);
    max-height: 200px;
    overflow-y: auto;
  }
  
  .email-confirm-buttons {
    display: flex;
    gap: 10px;
    justify-content: center;
  }
  
  .email-confirm-buttons button {
    padding: 10px 20px;
    border-radius: 8px;
    border: none;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  .email-confirm-buttons .email-send {
    background: var(--accent);
    color: white;
  }
  
  .email-confirm-buttons .email-send:hover {
    background: var(--accent-dark);
  }
  
  .email-confirm-buttons .email-cancel {
    background: #ddd;
    color: #333;
  }
  
  .email-confirm-buttons .email-cancel:hover {
    background: #ccc;
  }

  /* Email sending progress */
  .email-sending-progress {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    z-index: 10002;
    align-items: center;
    justify-content: center;
  }
  
  .email-sending-content {
    background: white;
    border-radius: 12px;
    padding: 30px;
    text-align: center;
    max-width: 400px;
    width: 90%;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  }
  
  .email-sending-content i {
    font-size: 3rem;
    color: var(--accent);
    margin-bottom: 20px;
  }
  
  .email-sending-content h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    margin-bottom: 15px;
    color: #4b2e1e;
  }
  
  .email-sending-content p {
    margin-bottom: 20px;
    color: #666;
  }
  
  .email-sending-content .progress-bar {
    height: 6px;
    background: #f0f0f0;
    border-radius: 3px;
    overflow: hidden;
    margin-bottom: 20px;
  }
  
  .email-sending-content .progress-fill {
    height: 100%;
    background: var(--accent);
    width: 0;
    border-radius: 3px;
    transition: width 0.3s ease;
  }

  /* Email success dialog */
  .email-success-dialog {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 10003;
  }
  
  .email-success-content {
    background: white;
    border-radius: 12px;
    padding: 30px;
    text-align: center;
    max-width: 400px;
    width: 90%;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  }
  
  .email-success-content i {
    font-size: 3rem;
    color: #2ecc71;
    margin-bottom: 20px;
  }
  
  .email-success-content h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    margin-bottom: 15px;
    color: #4b2e1e;
  }
  
  .email-success-content p {
    margin-bottom: 20px;
    color: #666;
  }
  
  .email-success-content .email-details {
    background: var(--light-gold);
    padding: 15px;
    border-radius: 8px;
    text-align: left;
    margin-bottom: 20px;
    font-size: 0.9rem;
    border: 1px solid var(--border-color);
  }
  
  .email-success-content .email-details p {
    margin: 5px 0;
  }
  
  .email-success-content button {
    padding: 10px 20px;
    border-radius: 8px;
    border: none;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    background: var(--accent);
    color: white;
  }
  
  .email-success-content button:hover {
    background: var(--accent-dark);
  }

  /* Styles for new pages */
  .welcome-content {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem;
    line-height: 1.6;
    color: #4b2e1e;
    text-align: center;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    overflow: hidden;
    position: relative;
  }
 
  .welcome-content::before {
    content: """;
    position: absolute;
    top: 10px;
    left: 20px;
    font-size: 80px;
    color: var(--accent);
    opacity: 0.2;
    font-family: 'Playfair Display', serif;
  }
 
  .welcome-content::after {
    content: """;
    position: absolute;
    bottom: 10px;
    right: 20px;
    font-size: 80px;
    color: var(--accent);
    opacity: 0.2;
    font-family: 'Playfair Display', serif;
  }
 
  .welcome-content p {
    margin-bottom: 15px;
    max-width: 800px;
    position: relative;
    z-index: 1;
  }
 
  .welcome-content .signature {
    font-style: italic;
    margin-top: 20px;
    align-self: flex-end;
    margin-right: 100px;
  }
 
  .restaurant-name {
    font-family: 'Playfair Display', serif;
    font-size: 5rem;
    font-weight: bold;
    color: #4b2e1e;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    letter-spacing: 3px;
    position: relative;
  }
 
  .restaurant-name::before {
    content: "";
    position: absolute;
    top: 40px;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 1px;
    background: var(--accent);
  }
 
  .restaurant-name::after {
    content: "";
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translateX(-50%);
    width: 100px;
    height: 1px;
    background: var(--accent);
  }
 
  .restaurant-name .subtitle {
    font-size: 1.5rem;
    font-weight: normal;
    margin-top: 20px;
    letter-spacing: 2px;
    color: var(--accent);
  }
 
  .quick-links {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    padding: 20px;
    overflow: hidden;
  }
 
  .quick-links h2 {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #4b2e1e;
    text-align: center;
  }
 
  .links-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
    width: 100%;
    max-width: 800px;
    overflow-y: auto;
    padding: 0 10px;
  }
 
  .link-button {
    padding: 20px;
    background: var(--soft);
    border-radius: 12px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    border: 1px solid var(--border-color);
    position: relative;
    overflow: hidden;
  }
 
  .link-button::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 4px;
    height: 100%;
    background: var(--accent);
    transform: scaleY(0);
    transition: transform 0.3s ease;
  }
 
  .link-button:hover::before {
    transform: scaleY(1);
  }
 
  .link-button:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0,0,0,0.12);
    background: var(--accent);
    color: white;
  }
 
  .link-button h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    margin-bottom: 8px;
  }
 
  .link-button p {
    font-size: 0.9rem;
    color: var(--muted);
  }
 
  .link-button:hover p {
    color: rgba(255, 255, 255, 0.9);
  }

  .thank-you-content {
    font-family: 'Playfair Display', serif;
    font-size: 1.0rem;
    line-height: 1.6;
    color: #4b2e1e;
    text-align: center;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    overflow: hidden;
    position: relative;
  }
 
  .thank-you-content::before {
    content: "";
    position: absolute;
    top: 20px;
    left: 20px;
    right: 20px;
    height: 1px;
    background: var(--border-color);
  }
 
  .thank-you-content::after {
    content: "";
    position: absolute;
    bottom: 20px;
    left: 20px;
    right: 20px;
    height: 1px;
    background: var(--border-color);
  }
 
  .thank-you-content h2 {
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: var(--accent);
  }
 
  .thank-you-content p {
    margin-bottom: 15px;
    max-width: 800px;
  }
 
  .thank-you-content .highlight {
    font-weight: bold;
    color: var(--accent);
    font-size: 1.6rem;
    margin: 20px 0;
    position: relative;
    display: inline-block;
    padding: 0 20px;
  }
 
  .thank-you-content .highlight::before,
  .thank-you-content .highlight::after {
    content: "✦";
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: var(--accent);
    opacity: 0.6;
  }
 
  .thank-you-content .highlight::before {
    left: 0;
  }
 
  .thank-you-content .highlight::after {
    right: 0;
  }
 
  .thank-you-content .signature {
    font-style: italic;
    margin-top: 20px;
    align-self: flex-end;
    margin-right: 100px;
  }
  
  .thank-you-content .social-links {
    display: flex;
    gap: 15px;
    margin-top: 20px;
  }
  
  .thank-you-content .social-links a {
    color: var(--accent);
    font-size: 1.5rem;
    transition: transform 0.3s ease, color 0.3s ease;
  }
  
  .thank-you-content .social-links a:hover {
    transform: scale(1.2);
    color: var(--accent-dark);
  }

  /* Credits Page Styles */
  .credits-content {
    font-family: 'Playfair Display', serif;
    font-size: 1.0rem;
    line-height: 1.6;
    color: #4b2e1e;
    text-align: center;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    overflow: hidden;
    position: relative;
    background-image: url('https://z-cdn-media.chatglm.cn/files/64572ee9-87a7-4f1a-a6bc-027341cf07f6_WhatsApp%20Image%202025-09-25%20at%2020.58.08_3dcac9b7.jpg?auth_key=1790350153-a2274b2c616f4848aabab729bddbdf99-0-cb0a68e7e137d90ec8d99ecdf489f8ca');
    background-size: cover;
    background-position: center 45%;
    background-repeat: no-repeat;
    border-radius: 14px;
  }
 
  .credits-content::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(255, 253, 249, 0.7);
    border-radius: 14px;
    z-index: 1;
  }
 
  body.dark-mode .credits-content::before {
    background: rgba(45, 45, 45, 0.7);
  }
 
  .credits-content h2 {
    font-size: 2.5rem;
    margin-bottom: 20px;
    color: var(--accent);
    position: relative;
    z-index: 2;
  }
 
  .credits-content p {
    margin-bottom: 15px;
    max-width: 800px;
    position: relative;
    z-index: 2;
  }
 
  .credits-content .highlight {
    font-weight: bold;
    color: var(--accent);
    font-size: 1.6rem;
    margin: 20px 0;
    position: relative;
    display: inline-block;
    padding: 0 20px;
    z-index: 2;
  }
 
  .credits-content .highlight::before,
  .credits-content .highlight::after {
    content: "✦";
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    color: var(--accent);
    opacity: 0.6;
  }
 
  .credits-content .highlight::before {
    left: 0;
  }
 
  .credits-content .highlight::after {
    right: 0;
  }
 
  .credits-content .signature {
    font-style: italic;
    margin-top: 20px;
    align-self: flex-end;
    margin-right: 100px;
    position: relative;
    z-index: 2;
  }
  
  .credits-content .social-links {
    display: flex;
    gap: 15px;
    margin-top: 240px;
    position: relative;
    z-index: 2;
  }
  
  .credits-content .social-links a {
    color: var(--accent);
    font-size: 1.5rem;
    transition: transform 0.3s ease, color 0.3s ease;
  }
  
  .credits-content .social-links a:hover {
    transform: scale(1.2);
    color: var(--dark-accent);
  }
  
  /* Credits Bubble Styles */
  .credits-content .bubbles-container {
    position: absolute;
    bottom: 30px;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    gap: 30px;
    z-index: 2;
    margin: 0;
  }

  .name-bubble {
    background-color: var(--light-gold);
    border-radius: 50px;
    padding: 15px 25px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: all 0.3s ease;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;
    min-width: 150px;
    border: 2px solid var(--accent);
  }

  .name-bubble:hover {
    transform: translateY(-10px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
    background-color: var(--accent);
    color: white;
  }

  .name-bubble:hover .number {
    color: rgba(255, 255, 255, 0.9);
  }

  .name {
    font-size: 18px;
    font-weight: bold;
    margin-bottom: 5px;
    color: black !important;
  }

  .number {
    font-size: 19px;
    color: black !important;
  }

  .from-text {
    font-size: 18px;
    position: absolute;
    bottom: 100px;
    left: 0;
    right: 0;
    text-align: center;
    color: var(--heading-color);
    position: relative;
    z-index: 2;
    margin: 0;
  }

  /* Personal Details Form Styles */
  .personal-details {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    height: 100%;
    padding: 20px 20px 0 20px;
    overflow: hidden;
  }

  .personal-details h2 {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    margin-bottom: 15px;
    color: #4b2e1e;
    text-align: center;
  }
  
  .personal-details .intro-text {
    text-align: center;
    margin-bottom: 20px;
    color: var(--muted);
    font-style: italic;
    max-width: 80%;
  }

  .personal-form {
    width: 100%;
    max-width: 500px;
    background: var(--light-gold);
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    border: 1px solid var(--border-color);
    flex-grow: 1;
    overflow-y: auto;
    padding-bottom: 30px;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .form-group label {
    display: block;
    font-weight: 600;
    margin-bottom: 8px;
    color: #4b2e1e;
  }

  .form-group input,
  .form-group select {
    width: 100%;
    padding: 10px;
    border-radius: 8px;
    border: 1.2px solid var(--border-color);
    background-color: white;
    font-family: 'Montserrat', sans-serif;
    font-size: 1rem;
  }

  .form-group input:focus,
  .form-group select:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 2px rgba(156, 123, 86, 0.2);
  }

  .radio-group {
    display: flex;
    gap: 15px;
    margin-top: 8px;
  }

  .radio-option {
    display: flex;
    align-items: center;
    gap: 5px;
  }

  .radio-option input[type="radio"] {
    width: auto;
  }

  .error-message {
    color: #e74c3c;
    font-size: 0.85rem;
    margin-top: 5px;
    display: none;
  }

  /* Review Form Styles */
  .review-section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: calc(100% - 80px);
    padding: 20px;
    overflow: hidden;
  }

  .review-section h2 {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    margin-bottom: 30px;
    color: #4b2e1e;
    text-align: center;
  }

  .review-form {
    width: 100%;
    max-width: 600px;
    background: var(--light-gold);
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    border: 1px solid var(--border-color);
  }

  .rating-group {
    margin-bottom: 20px;
  }

  .rating-group label {
    display: block;
    font-weight: 600;
    margin-bottom: 10px;
    color: #4b2e1e;
  }

  .star-rating {
    display: flex;
    gap: 5px;
    font-size: 1.5rem;
  }

  .star {
    color: #ddd;
    cursor: pointer;
    transition: color 0.2s;
  }

  .star:hover,
  .star.active {
    color: var(--accent);
  }

  .review-form textarea {
    width: 100%;
    padding: 12px;
    border-radius: 8px;
    border: 1.2px solid var(--border-color);
    background-color: white;
    font-family: 'Montserrat', sans-serif;
    font-size: 1rem;
    min-height: 120px;
    resize: vertical;
  }

  .review-form textarea:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 2px rgba(156, 123, 86, 0.2);
  }

  .success-message {
    background-color: #d4edda;
    color: #155724;
    padding: 15px;
    border-radius: 8px;
    margin-bottom: 20px;
    text-align: center;
    display: none;
  }

  /* Confirmation dialog */
  .confirm-dialog {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: none;
    align-items: center;
    justify-content: center;
    z-index: 10001;
  }
  
  .confirm-dialog-content {
    background: white;
    border-radius: 12px;
    padding: 25px;
    max-width: 400px;
    width: 90%;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    text-align: center;
  }
  
  .confirm-dialog h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    margin-bottom: 15px;
    color: #4b2e1e;
  }
  
  .confirm-dialog p {
    margin-bottom: 20px;
    color: #666;
  }
  
  .confirm-dialog-buttons {
    display: flex;
    gap: 10px;
    justify-content: center;
  }
  
  .confirm-dialog button {
    padding: 10px 20px;
    border-radius: 8px;
    border: none;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
  }
  
  .confirm-dialog .confirm-yes {
    background: var(--accent);
    color: white;
  }
  
  .confirm-dialog .confirm-yes:hover {
    background: var(--accent-dark);
  }
  
  .confirm-dialog .confirm-no {
    background: #ddd;
    color: #333;
  }
  
  .confirm-dialog .confirm-no:hover {
    background: #ccc;
  }

  /* Payment Page Styles */
  .payment-content {
    display: flex;
    flex-direction: column;
    height: calc(100% - 80px);
    padding: 15px;
    overflow: hidden;
  }

  .payment-content h2 {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem;
    margin-bottom: 10px;
    color: #4b2e1e;
    text-align: center;
    position: relative;
  }

  .payment-content h2::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 60px;
    height: 2px;
    background: var(--accent);
  }

  .payment-intro {
    text-align: center;
    margin-bottom: 15px;
    color: var(--muted);
    font-style: italic;
    font-size: 1rem;
  }

  .payment-options {
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
    justify-content: center;
    margin-bottom: 15px;
  }

  .payment-option {
    flex: 1;
    min-width: 180px;
    max-width: 220px;
    background: var(--light-gold);
    border-radius: 12px;
    padding: 15px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    border: 1px solid var(--border-color);
    position: relative;
    overflow: hidden;
  }

  .payment-option::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 4px;
    height: 100%;
    background: var(--accent);
    transform: scaleY(0);
    transition: transform 0.3s ease;
  }

  .payment-option:hover::before {
    transform: scaleY(1);
  }

  .payment-option:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0,0,0,0.12);
    background: var(--accent);
    color: white;
  }

  .payment-option:hover .payment-icon i {
    color: white;
  }

  .payment-option:hover .payment-details h3,
  .payment-option:hover .payment-details p {
    color: white;
  }

  .payment-icon {
    font-size: 2rem;
    margin-bottom: 10px;
    color: var(--accent);
  }

  .payment-details h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    margin-bottom: 5px;
    color: #4b2e1e;
  }

  .payment-details p {
    color: var(--muted);
    font-size: 0.85rem;
  }

  .payment-form {
    background: var(--light-gold);
    border-radius: 12px;
    padding: 15px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    border: 1px solid var(--border-color);
    margin-top: 10px;
    flex-grow: 1;
    overflow-y: auto;
    background-image:
      linear-gradient(to right, rgba(248,245,240,0.8) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(248,245,240,0.8) 1px, transparent 1px);
    background-size: 20px 20px;
  }

  body.dark-mode .payment-form {
    background-image:
      linear-gradient(to right, rgba(60, 60, 60, 0.3) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(60, 60, 60, 0.3) 1px, transparent 1px);
  }

  .payment-form h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    margin-bottom: 15px;
    color: #4b2e1e;
    text-align: center;
    position: relative;
  }

  .payment-form h3::after {
    content: "";
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 40px;
    height: 2px;
    background: var(--accent);
  }

  .form-row {
    display: flex;
    gap: 15px;
  }

  .form-row .form-group {
    flex: 1;
  }

  .payment-form-buttons {
    display: flex;
    gap: 15px;
    justify-content: center;
    margin-top: 15px;
  }

  .payment-form-buttons button {
    padding: 8px 16px;
    border-radius: 8px;
    border: none;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    font-family: 'Montserrat', sans-serif;
  }

  .payment-form-buttons .cancel-btn {
    background: #ddd;
    color: #333;
  }

  .payment-form-buttons .cancel-btn:hover {
    background: #ccc;
  }

  .payment-form-buttons .confirm-btn {
    background: var(--accent);
    color: white;
  }

  .payment-form-buttons .confirm-btn:hover {
    background: var(--accent-dark);
  }

  .upi-qr-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .qr-placeholder {
    width: 180px;
    height: 180px;
    background: white;
    border: 2px dashed var(--accent);
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 15px;
    position: relative;
  }

  .qr-placeholder img {
    max-width: 100%;
    max-height: 100%;
    border-radius: 8px;
  }

  .qr-placeholder i {
    font-size: 3rem;
    color: var(--accent);
    margin-bottom: 10px;
  }

  .upi-instructions {
    margin-bottom: 10px;
    color: #555;
    font-size: 0.95rem;
  }

  .upi-id {
    font-weight: 600;
    color: var(--accent);
    margin-top: 5px;
    font-size: 1rem;
  }

  /* Print styles */
  @media print {
    body * {
      visibility: hidden;
    }
    
    .bill-content, .bill-content * {
      visibility: visible;
    }
    
    .bill-content {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: visible;
    }
    
    .controls, .cart-icon, .dark-mode-toggle {
      display: none;
    }
  }

  /* Responsive styles */
  @media(min-width: 1200px) {
    .book {
      height: 85vh;
      max-height: 900px;
    }
  }
  
  @media(max-width: 1100px) {
    .book {
      max-width: 95vw;
    }
  }

  @media(max-width: 860px){
    .page{ padding:22px }
    .content{ grid-template-columns: 1fr; }
    .thumb{ width:84px; height:72px; }
    .restaurant-name { font-size: 3.5rem; }
    .welcome-content { font-size: 1.1rem; padding: 15px; }
    .links-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); }
    .thank-you-content, .credits-content { font-size: 1.2rem; }
    .thank-you-content h2, .credits-content h2 { font-size: 2rem; }
    .controls button { padding: 8px 16px; font-size: 0.9rem; }
    .personal-details h2, .review-section h2 { font-size: 2rem; }
    .personal-form, .review-form { padding: 20px; }
    .cart-icon { width: 40px; height: 40px; font-size: 1rem; }
    .cart-count { width: 18px; height: 18px; font-size: 0.7rem; }
    .notification { max-width: 280px; }
    .payment-content h2 { font-size: 2rem; }
    .payment-options { gap: 15px; }
    .payment-option { min-width: 180px; max-width: 280px; }
    .payment-icon { font-size: 2.2rem; }
    .payment-details h3 { font-size: 1.2rem; }
    .payment-form { padding: 20px; }
    .form-row { flex-direction: column; gap: 0; }
    .dark-mode-toggle { width: 40px; height: 40px; font-size: 1rem; }
    .credits-content .bubbles-container { gap: 20px; }
    .name-bubble { min-width: 130px; padding: 12px 20px; }
  }
  
  @media(max-width: 768px) {
    .book {
      height: 75vh;
      max-height: 700px;
    }
    
    .page {
      padding: 18px;
      border-radius: 10px;
    }
    
    .page h2 {
      font-size: 1.6rem;
      margin-bottom: 15px;
    }
    
    .controls {
      gap: 10px;
      margin-top: 15px;
    }
    
    .controls button {
      padding: 8px 14px;
      font-size: 0.85rem;
      border-radius: 20px;
    }
    
    .item {
      padding: 10px;
      gap: 10px;
    }
    
    .thumb {
      width: 70px;
      height: 60px;
    }
    
    .info .name {
      font-size: 0.95rem;
    }
    
    .info .desc {
      font-size: 0.85rem;
    }
    
    .info .meta {
      font-size: 0.9rem;
    }
    
    .restaurant-name {
      font-size: 2.8rem;
    }
    
    .restaurant-name .subtitle {
      font-size: 1.2rem;
    }
    
    .welcome-content {
      font-size: 1rem;
      padding: 15px;
    }
    
    .welcome-content::before,
    .welcome-content::after {
      font-size: 60px;
    }
    
    .quick-links h2 {
      font-size: 1.8rem;
      margin-bottom: 20px;
    }
    
    .links-grid {
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 15px;
    }
    
    .link-button {
      padding: 15px;
    }
    
    .link-button h3 {
      font-size: 1.1rem;
    }
    
    .link-button p {
      font-size: 0.85rem;
    }
    
    .thank-you-content, .credits-content {
      font-size: 1rem;
      padding: 15px;
    }
    
    .thank-you-content h2, .credits-content h2 {
      font-size: 1.8rem;
    }
    
    .thank-you-content .highlight, .credits-content .highlight {
      font-size: 1.4rem;
    }
    
    .personal-details h2,
    .review-section h2 {
      font-size: 1.8rem;
      margin-bottom: 20px;
    }
    
    .personal-form,
    .review-form {
      padding: 18px;
    }
    
    .form-group label {
      font-size: 0.9rem;
    }
    
    .form-group input,
    .form-group select,
    .review-form textarea {
      padding: 8px;
      font-size: 0.9rem;
    }
    
    .star-rating {
      font-size: 1.3rem;
    }
    
    .cart-icon {
      width: 36px;
      height: 36px;
      font-size: 0.9rem;
    }
    
    .cart-count {
      width: 16px;
      height: 16px;
      font-size: 0.65rem;
    }
    
    .notification {
      max-width: 240px;
      padding: 10px 15px;
    }
    
    .notification i {
      font-size: 1rem;
    }
    
    .order {
      width: 90%;
      max-width: 340px;
      padding: 18px;
    }
    
    .order header {
      font-size: 1.1rem;
    }
    
    .order label {
      font-size: 0.9rem;
    }
    
    .order input,
    .order textarea {
      padding: 8px;
      font-size: 0.9rem;
    }
    
    .order button {
      padding: 8px 14px;
      font-size: 0.9rem;
    }
    .payment-content h2 { font-size: 1.8rem; }
    .payment-intro { font-size: 1rem; }
    .payment-option { min-width: 160px; max-width: 250px; padding: 15px; }
    .payment-icon { font-size: 2rem; margin-bottom: 10px; }
    .payment-details h3 { font-size: 1.1rem; }
    .payment-form { padding: 18px; margin-top: 15px; }
    .qr-placeholder { width: 180px; height: 180px; }
    .qr-placeholder i { font-size: 3.5rem; }
    .upi-instructions { font-size: 0.9rem; }
    .upi-id { font-size: 1rem; }
    .dark-mode-toggle { width: 36px; height: 36px; font-size: 0.9rem; }
    .credits-content .bubbles-container { flex-direction: column; align-items: center; gap: 15px; margin: 20px 0; }
    .name-bubble { min-width: 200px; }
  }
  
  @media(max-width: 576px) {
    body {
      padding: 10px;
      gap: 10px;
    }
    
    .book {
      height: 70vh;
      max-height: 600px;
      perspective: 1500px;
    }
    
    .page {
      padding: 15px;
      border-radius: 8px;
    }
    
    .page h2 {
      font-size: 1.4rem;
      margin-bottom: 12px;
    }
    
    .page h2::after {
      width: 40px;
    }
    
    .controls {
      gap: 8px;
      margin-top: 12px;
      flex-wrap: wrap;
    }
    
    .controls button {
      padding: 6px 12px;
      font-size: 0.8rem;
      border-radius: 18px;
    }
    
    .item {
      padding: 8px;
      gap: 8px;
    }
    
    .thumb {
      width: 60px;
      height: 50px;
    }
    
    .info .name {
      font-size: 0.9rem;
    }
    
    .info .name::before {
      width: 6px;
      height: 6px;
    }
    
    .info .desc {
      font-size: 0.8rem;
    }
    
    .info .meta {
      font-size: 0.85rem;
    }
    
    .restaurant-name {
      font-size: 2.2rem;
      letter-spacing: 2px;
    }
    
    .restaurant-name::before,
    .restaurant-name::after {
      width: 70px;
    }
    
    .restaurant-name .subtitle {
      font-size: 1rem;
      letter-spacing: 1px;
    }
    
    .welcome-content {
      font-size: 0.9rem;
      padding: 12px;
    }
    
    .welcome-content::before,
    .welcome-content::after {
      font-size: 50px;
    }
    
    .welcome-content p {
      margin-bottom: 12px;
    }
    
    .quick-links h2 {
      font-size: 1.5rem;
      margin-bottom: 15px;
    }
    
    .links-grid {
      grid-template-columns: 1fr;
      gap: 12px;
    }
    
    .link-button {
      padding: 12px;
    }
    
    .link-button h3 {
      font-size: 1rem;
    }
    
    .link-button p {
      font-size: 0.8rem;
    }
    
    .thank-you-content, .credits-content {
      font-size: 0.9rem;
      padding: 12px;
    }
    
    .thank-you-content h2, .credits-content h2 {
      font-size: 1.5rem;
    }
    
    .thank-you-content .highlight, .credits-content .highlight {
      font-size: 1.2rem;
    }
    
    .thank-you-content .social-links a, .credits-content .social-links a {
      font-size: 1.2rem;
    }
    
    .personal-details h2,
    .review-section h2 {
      font-size: 1.5rem;
      margin-bottom: 15px;
    }
    
    .personal-form,
    .review-form {
      padding: 15px;
    }
    
    .form-group {
      margin-bottom: 15px;
    }
    
    .form-group label {
      font-size: 0.85rem;
    }
    
    .form-group input,
    .form-group select,
    .review-form textarea {
      padding: 8px;
      font-size: 0.85rem;
    }
    
    .radio-group {
      flex-direction: column;
      gap: 8px;
    }
    
    .star-rating {
      font-size: 1.2rem;
    }
    
    .cart-icon {
      width: 32px;
      height: 32px;
      font-size: 0.8rem;
      top: 15px;
      right: 15px;
    }
    
    .cart-count {
      width: 14px;
      height: 14px;
      font-size: 0.6rem;
      top: -4px;
      right: -4px;
    }
    
    .notification {
      max-width: 220px;
      padding: 8px 12px;
      bottom: 15px;
      right: 15px;
    }
    
    .notification i {
      font-size: 0.9rem;
    }
    
    .order {
      width: 95%;
      max-width: 320px;
      padding: 15px;
    }
    
    .order header {
      font-size: 1rem;
    }
    
    .order label {
      font-size: 0.85rem;
    }
    
    .order input,
    .order textarea {
      padding: 8px;
      font-size: 0.85rem;
    }
    
    .order button {
      padding: 8px 12px;
      font-size: 0.85rem;
    }
    
    .email-confirm-content,
    .email-sending-content,
    .email-success-content,
    .confirm-dialog-content {
      width: 95%;
      padding: 20px;
    }
    
    .email-confirm-content h3,
    .email-sending-content h3,
    .email-success-content h3,
    .confirm-dialog h3 {
      font-size: 1.2rem;
    }
    
    .email-confirm-content p,
    .email-sending-content p,
    .email-success-content p,
    .confirm-dialog p {
      font-size: 0.9rem;
    }
    
    .email-confirm-buttons button,
    .confirm-dialog button {
      padding: 8px 15px;
      font-size: 0.85rem;
    }
    .payment-content { padding: 15px; }
    .payment-content h2 { font-size: 1.6rem; }
    .payment-intro { font-size: 0.9rem; margin-bottom: 20px; }
    .payment-options { flex-direction: column; gap: 15px; }
    .payment-option { min-width: 100%; max-width: 100%; }
    .payment-form { padding: 15px; }
    .payment-form h3 { font-size: 1.2rem; }
    .payment-form-buttons { flex-direction: column; gap: 10px; }
    .qr-placeholder { width: 160px; height: 160px; }
    .dark-mode-toggle { width: 32px; height: 32px; font-size: 0.8rem; top: 15px; left: 15px; }
    .credits-content .bubbles-container { margin: 15px 0; }
    .name-bubble { min-width: 180px; padding: 10px 15px; }
    .name { font-size: 16px; }
    .number { font-size: 14px; }
  }
  
  @media(max-width: 380px) {
    .book {
      height: 65vh;
      max-height: 500px;
    }
    
    .page {
      padding: 12px;
    }
    
    .page h2 {
      font-size: 1.2rem;
    }
    
    .controls button {
      padding: 5px 10px;
      font-size: 0.75rem;
    }
    
    .item {
      flex-direction: column;
      padding: 10px;
    }
    
    .thumb {
      width: 100%;
      height: 100px;
      margin-bottom: 8px;
    }
    
    .info {
      width: 100%;
    }
    
    .restaurant-name {
      font-size: 1.8rem;
    }
    
    .restaurant-name .subtitle {
      font-size: 0.9rem;
    }
    
    .welcome-content {
      font-size: 0.85rem;
    }
    
    .quick-links h2 {
      font-size: 1.3rem;
    }
    
    .personal-details h2,
    .review-section h2 {
      font-size: 1.3rem;
    }
    
    .personal-form,
    .review-form {
      padding: 12px;
    }
    
    .star-rating {
      font-size: 1.1rem;
    }
    .payment-content { padding: 12px; }
    .payment-content h2 { font-size: 1.4rem; }
    .payment-option { padding: 12px; }
    .payment-icon { font-size: 1.8rem; }
    .payment-details h3 { font-size: 1rem; }
    .payment-form { padding: 12px; }
    .qr-placeholder { width: 140px; height: 140px; }
    .qr-placeholder i { font-size: 3rem; }
    .dark-mode-toggle { width: 28px; height: 28px; font-size: 0.75rem; }
    .credits-content .bubbles-container { margin: 10px 0; gap: 10px; }
    .name-bubble { min-width: 150px; padding: 8px 12px; }
    .name { font-size: 14px; }
    .number { font-size: 12px; }
  }
  
  /* Landscape mode adjustments */
  @media(max-height: 600px) and (orientation: landscape) {
    .book {
      height: 90vh;
      max-height: none;
    }
    
    .page {
      padding: 15px;
    }
    
    .page h2 {
      font-size: 1.3rem;
      margin-bottom: 10px;
    }
    
    .controls {
      margin-top: 10px;
    }
    
    .controls button {
      padding: 6px 12px;
      font-size: 0.8rem;
    }
    
    .restaurant-name {
      font-size: 2.5rem;
    }
    
    .restaurant-name .subtitle {
      font-size: 1rem;
    }
    
    .welcome-content {
      font-size: 0.9rem;
    }
    
    .quick-links h2 {
      font-size: 1.5rem;
      margin-bottom: 15px;
    }
    
    .links-grid {
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
    }
    
    .link-button {
      padding: 10px;
    }
    
    .link-button h3 {
      font-size: 0.9rem;
    }
    
    .link-button p {
      font-size: 0.75rem;
    }
    
    .thank-you-content, .credits-content {
      font-size: 0.9rem;
    }
    
    .thank-you-content h2, .credits-content h2 {
      font-size: 1.5rem;
    }
    
    .thank-you-content .highlight, .credits-content .highlight {
      font-size: 1.2rem;
    }
    
    .personal-details h2,
    .review-section h2 {
      font-size: 1.5rem;
      margin-bottom: 15px;
    }
    
    .personal-form,
    .review-form {
      padding: 15px;
    }
    
    .form-group {
      margin-bottom: 12px;
    }
    
    .star-rating {
      font-size: 1.2rem;
    }
    .payment-content h2 { font-size: 1.5rem; }
    .payment-options { gap: 15px; }
    .payment-option { min-width: 160px; max-width: 200px; padding: 15px; }
    .payment-icon { font-size: 2rem; }
    .payment-details h3 { font-size: 1.1rem; }
    .payment-form { padding: 15px; }
    .payment-form-buttons { margin-top: 15px; }
    .qr-placeholder { width: 150px; height: 150px; }
    .qr-placeholder i { font-size: 3rem; }
    .dark-mode-toggle { width: 36px; height: 36px; font-size: 0.9rem; }
    .credits-content .bubbles-container { margin: 15px 0; }
  }
</style>
</head>
<body>

<div class="loading-indicator" id="loading-indicator">
  <div class="loading-bar" id="loading-bar"></div>
</div>

<div class="dark-mode-toggle" id="dark-mode-toggle" aria-label="Toggle dark mode">
  <i class="fas fa-moon" id="dark-mode-icon"></i>
</div>

<div class="notification" id="notification">
  <i class="fas fa-check-circle"></i>
  <span id="notification-message">Item added to cart</span>
</div>

<div class="cart-icon" onclick="showCart()" aria-label="View cart">
  <i class="fas fa-shopping-cart"></i>
  <span class="cart-count" id="cart-count">0</span>
</div>

<div class="book" aria-live="polite" aria-label="MAD Restaurant menu book">

  <!-- Page 0: Restaurant Name -->
  <section class="page" data-index="0" aria-labelledby="p0-title">
    <div class="restaurant-name">
      MAD RESTAURANT
      <div class="subtitle">Where Flavor Meets Passion</div>
    </div>

    <div class="controls" aria-hidden="false">
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 1: Personal Details Form -->
  <section class="page" data-index="1" aria-labelledby="p1-title">
    <div class="personal-details">
      <h2 id="p1-title">Personal Details</h2>
      <p class="intro-text">Please fill the details below to access our menu card. We assure you this information will be kept confidential.</p>
      <div class="personal-form">
        <form id="personalDetailsForm">
          <div class="form-group">
            <label for="name">Full Name</label>
            <input type="text" id="name" name="name" required aria-required="true">
            <div class="error-message" id="name-error">Please enter your full name</div>
          </div>
          
          <div class="form-group">
            <label for="age">Age</label>
            <input type="number" id="age" name="age" min="1" max="120" required aria-required="true">
            <div class="error-message" id="age-error">Please enter a valid age</div>
          </div>
          
          <div class="form-group">
            <label>Gender</label>
            <div class="radio-group" role="radiogroup" aria-required="true">
              <div class="radio-option">
                <input type="radio" id="male" name="gender" value="male" required aria-required="true">
                <label for="male">Male</label>
              </div>
              <div class="radio-option">
                <input type="radio" id="female" name="gender" value="female" required aria-required="true">
                <label for="female">Female</label>
              </div>
              <div class="radio-option">
                <input type="radio" id="other" name="gender" value="other" required aria-required="true">
                <label for="other">Other</label>
              </div>
            </div>
            <div class="error-message" id="gender-error">Please select your gender</div>
          </div>
          
          <div class="form-group">
            <label for="contact">Contact Number</label>
            <input type="tel" id="contact" name="contact" pattern="[0-9]{10}" required aria-required="true">
            <div class="error-message" id="contact-error">Please enter a valid 10-digit contact number</div>
          </div>
          
          <div class="form-group">
            <label for="email">Email ID</label>
            <input type="email" id="email" name="email" required aria-required="true">
            <div class="error-message" id="email-error">Please enter a valid email address</div>
          </div>
        </form>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="next-btn" onclick="validateAndProceed()" aria-label="Proceed to next page">Next →</button>
    </div>
  </section>

  <!-- Page 2: Welcome Message -->
  <section class="page" data-index="2" aria-labelledby="p2-title">
    <div class="welcome-content">
      <h2 id="p2-title">Welcome!</h2>
      <p>We're so glad you're here. Our kitchen is filled with love, fresh ingredients, and flavors that bring people together.</p>
      <p>Whether you're here for a quick bite, a cozy meal with friends, or a special celebration, we hope you feel at home.</p>
      <p>Take your time, explore our menu, and let your taste buds travel. Every dish is made with care, just for you.</p>
      <p>Thank you for letting us share a little bit of joy, flavor, and warmth with you today.</p>
      <p>Bon Appétit!</p>
      <div class="signature">~The MAD Team</div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 3: Quick Links -->
  <section class="page" data-index="3" aria-labelledby="p3-title">
    <div class="quick-links">
      <h2 id="p3-title">Menu Sections</h2>
      <div class="links-grid">
        <div class="link-button" onclick="goToPage(4)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(4)">
          <h3>Broths</h3>
          <p>Warm and comforting soups</p>
        </div>
        <div class="link-button" onclick="goToPage(5)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(5)">
          <h3>Munching Bites</h3>
          <p>Perfect appetizers</p>
        </div>
        <div class="link-button" onclick="goToPage(6)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(6)">
          <h3>Large Plates</h3>
          <p>Hearty main courses</p>
        </div>
        <div class="link-button" onclick="goToPage(7)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(7)">
          <h3>Italian Pies</h3>
          <p>Freshly baked pizzas</p>
        </div>
        <div class="link-button" onclick="goToPage(8)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(8)">
          <h3>Signature Dishes</h3>
          <p>Our chef's specialties</p>
        </div>
        <div class="link-button" onclick="goToPage(9)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(9)">
          <h3>Sides</h3>
          <p>Perfect accompaniments</p>
        </div>
        <div class="link-button" onclick="goToPage(10)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(10)">
          <h3>Sweet Treats</h3>
          <p>Decadent desserts</p>
        </div>
        <div class="link-button" onclick="goToPage(11)" tabindex="0" onkeypress="if(event.key==='Enter') goToPage(11)">
          <h3>Drinks</h3>
          <p>Refreshing beverages</p>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 4: Broths -->
  <section class="page" data-index="4" aria-labelledby="p4-title">
    <h2 id="p4-title">Broths</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Tomato Basil Soup" data-price="319" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Tomato Basil Soup', 319)">
        <img class="thumb" src="https://www.cubesnjuliennes.com/wp-content/uploads/2022/09/Tomato-Basil-Soup-2.jpg" alt="Tomato Basil Soup">
        <div class="info">
          <div class="name">Tomato Basil Soup</div>
          <div class="desc">Tangy, creamy tomato with fresh basil — a broth that is comforting and smooth.</div>
          <div class="meta">319</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Mushroom Soup" data-price="349" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Mushroom Soup', 349)">
        <img class="thumb" src="https://www.skinnytaste.com/wp-content/uploads/2013/03/Creamy-Chicken-and-Mushroom-Soup-6.jpg" alt="Mushroom Soup">
        <div class="info">
          <div class="name">Mushroom Soup</div>
          <div class="desc">Earthy, creamy mushroom broth with herbs.</div>
          <div class="meta">349</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Broccoli Cheddar Soup" data-price="349" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Broccoli Cheddar Soup', 349)">
        <img class="thumb" src="https://www.orchidsandsweettea.com/wp-content/uploads/2022/10/Broccoli-Cheddar-Soup-7-of-7-e1665030835273.jpg" alt="Broccoli Cheddar Soup">
        <div class="info">
          <div class="name">Broccoli Cheddar Soup</div>
          <div class="desc">Rich, velvety broccoli and cheddar soup with a comforting cheesy hug in every spoon.</div>
          <div class="meta">349</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Veg Manchow Soup" data-price="319" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Veg Manchow Soup', 319)">
        <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTd7FtOYjL6yNX104zCDIj4lkwz0zIGImIEew&s" alt="Veg Manchow Soup">
        <div class="info">
          <div class="name">Veg Manchow Soup</div>
          <div class="desc">Classic Indo-Chinese spicy broth finished with crunchy fried noodles.</div>
          <div class="meta">319</div>
        </div>
      </div>
    </div>

    <div class="controls" aria-hidden="false">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 5: Munching Bites -->
  <section class="page" data-index="5" aria-labelledby="p5-title">
    <h2 id="p5-title">Munching Bites</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Bruschetta" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Bruschetta', 389)">
        <img class="thumb" src="https://www.simplyorganic.com/media/recipe/resized/520x520/wysiwyg/tmp/simply-oragnic-Roasted-Tomato-Bruschetta-1080x1080-thumbnail.jpg" alt="Bruschetta">
        <div class="info">
          <div class="name">Bruschetta</div>
          <div class="desc">Fresh, zesty tomatoes and basil on perfectly toasted bread with a hint of garlic.</div>
          <div class="meta">389</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Veg Dimsums" data-price="489" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Veg Dimsums', 489)">
        <img class="thumb" src="https://b.zmtcdn.com/data/pictures/chains/5/18247015/6dd7cd760bb34e40e8ba8bf0cfcff920.jpg" alt="Veg Dimsums">
        <div class="info">
          <div class="name">Veg Dimsums</div>
          <div class="desc">Soft, flavorful dumplings bursting with classic fillings in every bite.</div>
          <div class="meta">489</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Mexican Nachos" data-price="419" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Mexican Nachos', 419)">
        <img class="thumb" src="https://www.oliveandmango.com/images/uploads/2020_05_03_sheet_pan_nachos_supreme_6.jpg" alt="Mexican Nachos">
        <div class="info">
          <div class="name">Mexican Nachos</div>
          <div class="desc">Crispy tortilla chips loaded with cheese, jalapeños, and tangy salsa.</div>
          <div class="meta">419</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Paneer Tikka" data-price="459" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Paneer Tikka', 459)">
        <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRJ2WY2YmIJtXrpmDToEHwJIOAcyBefjpFwXg&s" alt="Paneer Tikka">
        <div class="info">
          <div class="name">Paneer Tikka</div>
          <div class="desc">Smoky, traditional Indian flavored paneer cubes served hot off the grill.</div>
          <div class="meta">459</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 6: Large Plates -->
  <section class="page" data-index="6" aria-labelledby="p6-title">
    <h2 id="p6-title">Large Plates</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Pesto Pappardelle" data-price="649" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Pesto Pappardelle', 649)">
        <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRfSvr3f8e5PuGclOiQXWXm25KPKGnyUvlNgA&s" alt="Pesto Pappardelle">
        <div class="info">
          <div class="name">Pesto Pappardelle</div>
          <div class="desc">A fragrant blend of Al dente pasta tossed in rich pesto, and a hint of garlic.</div>
          <div class="meta">649</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Enchiladas" data-price="589" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Enchiladas', 589)">
        <img class="thumb" src="https://www.elcomal.com/wp-content/uploads/2021/11/Enchiladas-2-2000x1335.jpg" alt="Enchiladas">
        <div class="info">
          <div class="name">Enchiladas</div>
          <div class="desc">Tender tortillas stuffed with seasoned kidney beans and topped with spicy sauce and melted cheese.</div>
          <div class="meta">589</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Blue Pea Rice With Japanese Curry" data-price="689" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Blue Pea Rice With Japanese Curry', 689)">
        <img class="thumb" src="https://b.zmtcdn.com/data/dish_photos/859/3ea211ebbe6e50ec358ff09e6963d859.jpeg?fit=around|130:130&crop=130:130;*,*" alt="Blue Pea Rice With Japanese Curry">
        <div class="info">
          <div class="name">Blue Pea Rice With Japanese Curry</div>
          <div class="desc">Vibrant blue pea-infused rice served with rich, savory Japanese curry.</div>
          <div class="meta">689</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Desi Wok Tossed Noodles" data-price="569" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Desi Wok Tossed Noodles', 569)">
        <img class="thumb" src="https://www.whiskaffair.com/wp-content/uploads/2020/02/Chilli-Garlic-Noodles-2-1-1200x1800.jpg" alt="Desi Wok Tossed Noodles">
        <div class="info">
          <div class="name">Desi Wok Tossed Noodles</div>
          <div class="desc">Tender noodles, crunchy vegetables, and aromatic desi seasonings in every bite.</div>
          <div class="meta">569</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 7: Italian Pies -->
  <section class="page" data-index="7" aria-labelledby="p7-title">
    <h2 id="p7-title">Italian Pies</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Classic Margherita Pizza" data-price="629" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Classic Margherita Pizza', 629)">
        <img class="thumb" src="https://ooni.com/cdn/shop/articles/20220211142347-margherita-9920_ba86be55-674e-4f35-8094-2067ab41a671.jpg?v=1737104576" alt="Classic Margherita Pizza">
        <div class="info">
          <div class="name">Classic Margherita Pizza</div>
          <div class="desc">A timeless classic of gooey cheese, tangy tomatoes, and fragrant basil.</div>
          <div class="meta">629</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Truffle Pizza" data-price="689" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Truffle Pizza', 689)">
        <img class="thumb" src="https://images.squarespace-cdn.com/content/v1/55be995de4b071c106b3b4c0/1607620549016-GKSGISFJAM5R01SSUT9T/Truffle+Mushroom+and+Ricotta+Pizza+-+Eat+Cho+Food+Blog" alt="Truffle Pizza">
        <div class="info">
          <div class="name">Truffle Pizza</div>
          <div class="desc">A luxurious blend of earthy truffle, creamy cheese, and crisp golden crust.</div>
          <div class="meta">689</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Paneer Tandoori Pizza" data-price="659" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Paneer Tandoori Pizza', 659)">
        <img class="thumb" src="https://b.zmtcdn.com/data/dish_photos/be9/c8af5ef52bec6145db8f1475af721be9.jpeg" alt="Paneer Tandoori Pizza">
        <div class="info">
          <div class="name">Paneer Tandoori Pizza</div>
          <div class="desc">Crispy pizza base topped with smoky tandoori paneer, onions, and peppers.</div>
          <div class="meta">659</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Veggie Supreme Pizza" data-price="659" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Veggie Supreme Pizza', 659)">
        <img class="thumb" src="https://www.nordicware.com/wp-content/uploads/2021/05/46400_traditional_pizza_pan_02_e.jpg" alt="Veggie Supreme Pizza">
        <div class="info">
          <div class="name">Veggie Supreme Pizza</div>
          <div class="desc">A veggie lover's dream—peppers, onions, olives, and more on a melty base.</div>
          <div class="meta">659</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 8: Signature Dishes -->
  <section class="page" data-index="8" aria-labelledby="p8-title">
    <h2 id="p8-title">Signature Dishes</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Veg Ramen" data-price="749" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Veg Ramen', 749)">
        <img class="thumb" src="https://thefoodiediaries.co/wp-content/uploads/2020/08/img_4288.jpg" alt="Veg Ramen">
        <div class="info">
          <div class="name">Veg Ramen</div>
          <div class="desc">A comforting Japanese broth with noodles, fresh vegetables, and umami depth.</div>
          <div class="meta">749</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="24 Hours Slow Cooked Dal Makhani" data-price="719" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('24 Hours Slow Cooked Dal Makhani', 719)">
        <img class="thumb" src="https://www.sharmispassions.com/wp-content/uploads/2012/05/dal-makhani7.jpg" alt="24 Hours Slow Cooked Dal Makhani">
        <div class="info">
          <div class="name">24 Hours Slow Cooked Dal Makhani</div>
          <div class="desc">A luxuriously creamy dal, slow-cooked overnight for deep, smoky richness.</div>
          <div class="meta">719</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Cheetos California Cream Cheese Sushi" data-price="749" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Cheetos California Cream Cheese Sushi', 749)">
        <img class="thumb" src="https://cdn.britannica.com/54/171754-050-8581F347/California-rolls-sushi.jpg" alt="Cheetos California Cream Cheese Sushi">
        <div class="info">
          <div class="name">Cheetos California Cream Cheese Sushi</div>
          <div class="desc">A unique fusion of crunchy Cheetos, fresh California rolls, and creamy cheese.</div>
          <div class="meta">749</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Vodka Spinach Cannelloni" data-price="749" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Vodka Spinach Cannelloni', 749)">
        <img class="thumb" src="https://www.theburntbuttertable.com/wp-content/uploads/2025/02/Ricotta-Spinach-Ricotta-2.jpg" alt="Vodka Spinach Cannelloni">
        <div class="info">
          <div class="name">Vodka Spinach Cannelloni</div>
          <div class="desc">Pasta tubes stuffed with creamy spinach, baked under a lush vodka-tomato cream sauce.</div>
          <div class="meta">749</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 9: Sides & Accompaniments -->
  <section class="page" data-index="9" aria-labelledby="p9-title">
    <h2 id="p9-title">Sides & Accompaniments</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Quinoa Avocado Salad" data-price="419" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Quinoa Avocado Salad', 419)">
        <img class="thumb" src="https://foolproofliving.com/wp-content/uploads/2020/04/Quinoa-Avocado-Salad-Recipe-Image-500x500.jpg" alt="Quinoa Avocado Salad">
        <div class="info">
          <div class="name">Quinoa Avocado Salad</div>
          <div class="desc">Protein-packed quinoa mixed with buttery avocado and vibrant veggies.</div>
          <div class="meta">419</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Garlic Bread" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Garlic Bread', 389)">
        <img class="thumb" src="https://www.ambitiouskitchen.com/wp-content/uploads/2023/02/Garlic-Bread-4.jpg" alt="Garlic Bread">
        <div class="info">
          <div class="name">Garlic Bread</div>
          <div class="desc">Warm, toasted bread bursting with rich garlic flavor and melted butter.</div>
          <div class="meta">389</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Parmesan French Fries" data-price="319" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Parmesan French Fries', 319)">
        <img class="thumb" src="https://cravingsjournal.com/wp-content/uploads/2023/08/garlic-parmesan-french-fries-2-500x500.jpg" alt="Parmesan French Fries">
        <div class="info">
          <div class="name">Parmesan French Fries</div>
          <div class="desc">Crispy fries loaded with freshly grated Parmesan and a touch of herbs.</div>
          <div class="meta">319</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Assorted Desi Bread Basket" data-price="519" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Assorted Desi Bread Basket', 519)">
        <img class="thumb" src="https://images.picxy.com/cache/2020/7/10/2f9a656ceb1583441f2569900de0f2b0.jpg" alt="Assorted Desi Bread Basket">
        <div class="info">
          <div class="name">Assorted Desi Bread Basket</div>
          <div class="desc">A warm assortment of traditional Indian breads—naan, paratha, and more—fresh from the tandoor.</div>
          <div class="meta">519</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 10: Sweet Treats -->
  <section class="page" data-index="10" aria-labelledby="p10-title">
    <h2 id="p10-title">Sweet Treats</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Chocolate Pistachio Cake with Raspberry Compote" data-price="619" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Chocolate Pistachio Cake with Raspberry Compote', 619)">
        <img class="thumb" src="https://i.pinimg.com/564x/72/01/b7/7201b73f4be4cf07c7fa16d6cd0ba5e9.jpg" alt="Chocolate Pistachio Cake with Raspberry Compote">
        <div class="info">
          <div class="name">Chocolate Pistachio Cake with Raspberry Compote</div>
          <div class="desc">Decadent chocolate and nutty pistachio cake finished with a vibrant raspberry glaze.</div>
          <div class="meta">619</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Hazelnut Nutella Cheesecake" data-price="589" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Hazelnut Nutella Cheesecake', 589)">
        <img class="thumb" src="https://www.tamingtwins.com/wp-content/uploads/2024/05/nutella-cheesecake-9.jpg" alt="Hazelnut Nutella Cheesecake">
        <div class="info">
          <div class="name">Hazelnut Nutella Cheesecake</div>
          <div class="desc">A heavenly blend of cheesecake, Nutella, and roasted hazelnuts in every bite.</div>
          <div class="meta">589</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Biscoff Ice Cream" data-price="469" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Biscoff Ice Cream', 469)">
        <img class="thumb" src="https://www.tablefortwoblog.com/wp-content/uploads/2023/07/biscoff-ice-cream-recipe-photo-tablefortwoblog-11-scaled.jpg" alt="Biscoff Ice Cream">
        <div class="info">
          <div class="name">Biscoff Ice Cream</div>
          <div class="desc">A sweet, buttery ice cream delight inspired by classic Biscoff cookies.</div>
          <div class="meta">469</div>
        </div>
      </div>
   
      <div class="item" role="listitem" data-name="Tiramisu Pull Me Up" data-price="619" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Tiramisu Pull Me Up', 619)">
        <img class="thumb" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTA9d48jw_MeI2WqRw_vIAEIa8_jneGziK74g&s" alt="Tiramisu Pull Me Up">
        <div class="info">
          <div class="name">Tiramisu Pull Me Up</div>
          <div class="desc">Coffee-soaked tiramisu layered with creamy mascarpone and cocoa dust.</div>
          <div class="meta">619</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 11: Drinks -->
  <section class="page" data-index="11" aria-labelledby="p11-title">
    <h2 id="p11-title">Drinks</h2>
    <div class="content" role="list">
      <div class="item" role="listitem" data-name="Peach Me Up" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Peach Me Up', 389)">
        <img class="thumb" src="https://lifestyleofafoodie.com/wp-content/uploads/2021/08/Homemade-peach-iced-tea-15-of-19-1.jpg" alt="Peach Me Up">
        <div class="info">
          <div class="name">Peach Me Up</div>
          <div class="desc">Refreshing iced tea infused with the sweet, juicy flavor of ripe peaches.</div>
          <div class="meta">389</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Virgin Bloody Mary" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Virgin Bloody Mary', 389)">
        <img class="thumb" src="https://www.allrecipes.com/thmb/BKwSLEiCfsWT1p1wlAA2Wic51c4=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/65037-classic-bloody-mary-DDMFS-4x3-850b39f3825e4e098b7a2acf03073a12.jpg" alt="Virgin Bloody Mary">
        <div class="info">
          <div class="name">Virgin Bloody Mary</div>
          <div class="desc">Bold and tangy, garnished with juicy olives and a hint of smoky flavor.</div>
          <div class="meta">389</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Fresh Lime Soda" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Fresh Lime Soda', 389)">
        <img class="thumb" src="https://gunjanchopra.com/content/images/2022/08/FI-2.jpg" alt="Fresh Lime Soda">
        <div class="info">
          <div class="name">Fresh Lime Soda</div>
          <div class="desc">Zesty lime juice blended with sparkling soda for a refreshing burst.</div>
          <div class="meta">389</div>
        </div>
      </div>

      <div class="item" role="listitem" data-name="Hibiscus Bliss" data-price="389" tabindex="0" onkeypress="if(event.key==='Enter') openOrder('Hibiscus Bliss', 389)">
        <img class="thumb" src="https://mocktailcraze.com/wp-content/uploads/2024/12/Hibiscus-Kiss-Mocktail.webp" alt="Hibiscus Bliss">
        <div class="info">
          <div class="name">Hibiscus Bliss</div>
          <div class="desc">A vibrant, floral mocktail with refreshing hibiscus and a hint of citrus.</div>
          <div class="meta">389</div>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="menu-btn" onclick="goToPage(3)" aria-label="Go to menu sections">Menu Sections</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 12: Review Section -->
  <section class="page" data-index="12" aria-labelledby="p12-title">
    <div class="review-section">
      <h2 id="p12-title">Share Your Experience</h2>
      <div class="success-message" id="review-success">
        Thank you for your feedback! Your review has been submitted successfully.
      </div>
      <div class="review-form">
        <form id="reviewForm">
          <div class="rating-group">
            <label>Rate Your Experience</label>
            <div class="star-rating" role="radiogroup" aria-label="Rating">
              <span class="star" data-rating="1" role="radio" aria-label="1 star" tabindex="0">★</span>
              <span class="star" data-rating="2" role="radio" aria-label="2 stars" tabindex="0">★</span>
              <span class="star" data-rating="3" role="radio" aria-label="3 stars" tabindex="0">★</span>
              <span class="star" data-rating="4" role="radio" aria-label="4 stars" tabindex="0">★</span>
              <span class="star" data-rating="5" role="radio" aria-label="5 stars" tabindex="0">★</span>
            </div>
          </div>
          
          <div class="form-group">
            <label for="comments">Your Comments</label>
            <textarea id="comments" name="comments" placeholder="Tell us about your experience..." aria-label="Your comments"></textarea>
          </div>
          
          <div class="controls" style="margin-top: 20px;">
            <button type="button" class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
            <button type="submit" class="confirm" aria-label="Submit review">Submit Review</button>
            <button type="button" class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
          </div>
        </form>
      </div>
    </div>
  </section>

  <!-- Page 13: Bill -->
  <section class="page" data-index="13" aria-labelledby="p13-title">
    <div class="bill-content">
      <div class="bill-header">
        <h2 id="p13-title">Your Order</h2>
      </div>
      
      <div class="customer-info" id="customer-info">
        <h3>Customer Information</h3>
        <p><strong>Name:</strong> <span id="bill-name"></span></p>
        <p><strong>Contact:</strong> <span id="bill-contact"></span></p>
        <p><strong>Email:</strong> <span id="bill-email"></span></p>
      </div>
      
      <div class="bill-items" id="bill-items">
        <div class="empty-cart">
          <i class="fas fa-receipt"></i>
          <p>Your cart is empty</p>
          <p>Add items from the menu to see them here</p>
        </div>
      </div>
      
      <div class="bill-total" id="bill-total" style="display: none;">
        Total: ₹<span id="total-amount">0.00</span>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="email-btn" onclick="showEmailConfirmDialog()" aria-label="Email bill">
        <i class="fas fa-envelope"></i> Email Bill
      </button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 14: Payment Mode Selection -->
  <section class="page" data-index="14" aria-labelledby="p14-title">
    <div class="payment-content">
      <h2 id="p14-title">Select Payment Method</h2>
      <p class="payment-intro">Please choose your preferred payment method to complete your order.</p>
      
      <div class="payment-options">
        <div class="payment-option" onclick="selectPaymentMode('card')" tabindex="0" onkeypress="if(event.key==='Enter') selectPaymentMode('card')">
          <div class="payment-icon">
            <i class="fas fa-credit-card"></i>
          </div>
          <div class="payment-details">
            <h3>Card Payment</h3>
            <p>Pay using credit or debit card</p>
          </div>
        </div>
        
        <div class="payment-option" onclick="selectPaymentMode('upi')" tabindex="0" onkeypress="if(event.key==='Enter') selectPaymentMode('upi')">
          <div class="payment-icon">
            <i class="fas fa-qrcode"></i>
          </div>
          <div class="payment-details">
            <h3>UPI Payment</h3>
            <p>Scan QR code to pay</p>
          </div>
        </div>
        
        <div class="payment-option" onclick="selectPaymentMode('cash')" tabindex="0" onkeypress="if(event.key==='Enter') selectPaymentMode('cash')">
          <div class="payment-icon">
            <i class="fas fa-money-bill-wave"></i>
          </div>
          <div class="payment-details">
            <h3>Cash Payment</h3>
            <p>Pay with cash at counter</p>
          </div>
        </div>
      </div>
      
      <!-- Card Payment Form (Hidden by default) -->
      <div class="payment-form" id="card-payment-form" style="display: none;">
        <h3>Card Details</h3>
        <form id="card-form">
          <div class="form-group">
            <label for="card-number">Card Number</label>
            <input type="text" id="card-number" placeholder="1234 5678 9012 3456" maxlength="19" required>
            <div class="error-message" id="card-number-error">Please enter a valid card number</div>
          </div>
          
          <div class="form-row">
            <div class="form-group">
              <label for="card-name">Cardholder Name</label>
              <input type="text" id="card-name" placeholder="John Doe" required>
              <div class="error-message" id="card-name-error">Please enter the cardholder name</div>
            </div>
            
            <div class="form-group">
              <label for="card-expiry">Expiry Date</label>
              <input type="text" id="card-expiry" placeholder="MM/YY" maxlength="5" required>
              <div class="error-message" id="card-expiry-error">Please enter a valid expiry date</div>
            </div>
            
            <div class="form-group">
              <label for="card-cvv">CVV</label>
              <input type="text" id="card-cvv" placeholder="123" maxlength="3" required>
              <div class="error-message" id="card-cvv-error">Please enter a valid CVV</div>
            </div>
          </div>
          
          <div class="form-group">
            <label for="billing-address">Billing Address</label>
            <textarea id="billing-address" placeholder="Enter your billing address" rows="2"></textarea>
          </div>
          
          <div class="payment-form-buttons">
            <button type="button" class="cancel-btn" onclick="cancelCardPayment()">Cancel</button>
            <button type="submit" class="confirm-btn">Process Payment</button>
          </div>
        </form>
      </div>
      
      <!-- UPI Payment (Hidden by default) -->
      <div class="payment-form" id="upi-payment-form" style="display: none;">
        <h3>Scan to Pay</h3>
        <div class="upi-qr-container">
          <div class="qr-placeholder" id="qr-code-container">
            <i class="fas fa-qrcode"></i>
            <p>UPI QR Code</p>
          </div>
          <p class="upi-instructions">Scan this QR code using any UPI app to complete your payment</p>
          <p class="upi-id">UPI ID: madrestaurant@paytm</p>
        </div>
        
        <div class="payment-form-buttons">
          <button type="button" class="cancel-btn" onclick="cancelUPIPayment()">Cancel</button>
          <button type="button" class="confirm-btn" onclick="confirmUPIPayment()">I've Paid</button>
        </div>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page" id="payment-next-btn" disabled>Next →</button>
    </div>
  </section>

  <!-- Page 15: Thank You -->
  <section class="page" data-index="15" aria-labelledby="p15-title">
    <div class="thank-you-content">
      <h2 id="p15-title">Thank You for Dining With Us!</h2>
      <p>We hope you enjoyed your culinary journey at MAD Restaurant.</p>
      <p>It was our pleasure to have served you today.</p>
      <div class="highlight">Come back soon!</div>
      <p>Follow us on social media for updates on special events, seasonal menus, and exclusive offers.</p>
      <div class="social-links">
        <a href="#" aria-label="Facebook"><i class="fab fa-facebook"></i></a>
        <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
        <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
      </div>
      <p>We look forward to welcoming you back for another delightful dining experience.</p>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
      <button class="next-btn" onclick="nextPage()" aria-label="Next page">Next →</button>
    </div>
  </section>

  <!-- Page 16: Credits -->
  <section class="page" data-index="16" aria-labelledby="p16-title">
    <div class="credits-content">
      <h2 id="p16-title">CREDITS</h2>
      <div class="highlight">THIS WEBSITE IS CREATED BY</div>
      
      
      
      <div class="bubbles-container">
        <div class="name-bubble">
          <div class="name">AARYAN SHAH</div>
          <div class="number">50</div>
        </div>
        
        <div class="name-bubble">
          <div class="name">DIA SAVLA</div>
          <div class="number">48</div>
        </div>
        
        <div class="name-bubble">
          <div class="name">MOKSH SHAH</div>
          <div class="number">51</div>
        </div>
      </div>
      
      <div class="social-links">
        <a href="#" aria-label="Facebook"><i class="fab fa-facebook"></i></a>
        <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
        <a href="#" aria-label="Twitter"><i class="fab fa-twitter"></i></a>
      </div>
    </div>

    <div class="controls">
      <button class="prev-btn" onclick="prevPage()" aria-label="Previous page">← Prev</button>
    </div>
  </section>

</div>

<!-- ORDER POPUP -->
<div class="overlay" id="overlay" role="dialog" aria-modal="true" aria-hidden="true" aria-labelledby="order-title">
  <div class="order" role="document">
    <header id="order-title">Add to Order</header>
    <form id="orderForm">
      <label for="order-item">Item</label>
      <input id="order-item" type="text" name="item" readonly>

      <label for="order-price">Price (₹)</label>
      <input id="order-price" type="text" name="price" readonly>

      <label for="order-qty">Quantity</label>
      <input id="order-qty" type="number" name="qty" min="1" value="1" required aria-required="true">

      <label for="order-notes">Notes</label>
      <textarea id="order-notes" name="notes" rows="3" placeholder="Any preferences or allergies?" aria-label="Special notes or preferences"></textarea>

      <div class="row" style="justify-content:flex-end;">
        <button type="button" class="cancel" id="cancelBtn">Cancel</button>
        <button type="submit" class="confirm">Add to Order</button>
      </div>
    </form>
  </div>
</div>

<!-- CART POPUP -->
<div class="overlay" id="cart-overlay" role="dialog" aria-modal="true" aria-hidden="true" aria-labelledby="cart-title">
  <div class="order" role="document">
    <header id="cart-title">Your Order</header>
    <div id="cart-items" style="max-height: 300px; overflow-y: auto; margin-bottom: 15px;">
      <div class="empty-cart">
        <p>Your cart is empty</p>
      </div>
    </div>
    <div class="bill-total" id="cart-total" style="display: none; margin-bottom: 15px;">
      Total: ₹<span id="cart-total-amount">0.00</span>
    </div>
    <div class="row" style="justify-content:flex-end;">
      <button type="button" class="cancel" id="cart-close-btn">Close</button>
      <button type="button" class="confirm" id="checkout-btn" onclick="goToPage(13); closeCart();" aria-label="View bill">View Bill</button>
    </div>
  </div>
</div>

<!-- EMAIL CONFIRMATION DIALOG -->
<div class="email-confirm-dialog" id="email-confirm-dialog">
  <div class="email-confirm-content">
    <h3>Confirm Email Bill</h3>
    <p>Your bill will be emailed to <strong id="email-recipient"></strong>. Please review the bill details below before sending.</p>
    
    <div class="email-preview" id="email-preview">
      <!-- Email content will be populated here -->
    </div>
    
    <div class="email-confirm-buttons">
      <button class="email-cancel" onclick="closeEmailConfirmDialog()">Cancel</button>
      <button class="email-send" id="email-send-btn">Send Email</button>
    </div>
  </div>
</div>

<!-- EMAIL SENDING PROGRESS -->
<div class="email-sending-progress" id="email-sending-progress">
  <div class="email-sending-content">
    <i class="fas fa-envelope-open-text"></i>
    <h3>Sending Email...</h3>
    <p>Please wait while we send your bill to <span id="sending-email-recipient"></span></p>
    <div class="progress-bar">
      <div class="progress-fill" id="email-progress-fill"></div>
    </div>
    <p>This may take a few moments.</p>
  </div>
</div>

<!-- EMAIL SUCCESS DIALOG -->
<div class="email-success-dialog" id="email-success-dialog">
  <div class="email-success-content">
    <i class="fas fa-check-circle"></i>
    <h3>Email Sent Successfully!</h3>
    <p>Your bill has been sent to the customer's email address.</p>
    
    <div class="email-details">
      <p><strong>Recipient:</strong> <span id="success-email-recipient"></span></p>
      <p><strong>Subject:</strong> MAD Restaurant - Your Order Bill</p>
      <p><strong>Sent at:</strong> <span id="email-sent-time"></span></p>
    </div>
    
    <button onclick="closeEmailSuccessDialog()">OK</button>
  </div>
</div>

<!-- CONFIRMATION DIALOG -->
<div class="confirm-dialog" id="confirm-dialog">
  <div class="confirm-dialog-content">
    <h3>Confirm Action</h3>
    <p id="confirm-message">Are you sure you want to proceed?</p>
    <div class="confirm-dialog-buttons">
      <button class="confirm-no" onclick="closeConfirmDialog()">Cancel</button>
      <button class="confirm-yes" id="confirm-yes-btn">Confirm</button>
    </div>
  </div>
</div>

<script>
  // Pages
  const pages = Array.from(document.querySelectorAll('.page'));
  const prevBtns = Array.from(document.querySelectorAll('.prev-btn'));
  const nextBtns = Array.from(document.querySelectorAll('.next-btn'));
  let current = 0;
  let isAnimating = false; // Flag to prevent multiple animations at once
  let selectedRating = 0;
  let customerDetails = {};
  let cart = []; // Array to store cart items
  let selectedPaymentMode = ''; // For payment mode selection
  let isDarkMode = false; // For dark mode toggle

  // Initialize z-indexes programmatically (safer than relying only on CSS)
  function initZIndexes(){
    pages.forEach((p,i)=>{
      // Give descending z-index so first page visually sits on top
      p.style.zIndex = (pages.length - i) * 10;
    });
  }

  function updatePages(){
    pages.forEach((p,i)=>{
      if(i < current){
        p.classList.add('flipped');
        // flipped pages go behind
        p.style.zIndex = i; // lower z-index when flipped
      } else {
        p.classList.remove('flipped');
        p.style.zIndex = (pages.length - i) * 10; // higher when not flipped
      }
    });

    // Update prev/next button disabled states
    prevBtns.forEach(btn => btn.disabled = current === 0);
    nextBtns.forEach(btn => btn.disabled = current === pages.length - 1);

    // Accessibility: indicate which page is visible
    pages.forEach((p,i) => p.setAttribute('aria-hidden', i !== current));
    
    // Update bill display if we're on the bill page
    if (current === 13) {
      updateBillDisplay();
    }
    
    // Save current page to localStorage
    localStorage.setItem('currentPage', current);
  }

  function showLoadingIndicator() {
    const indicator = document.getElementById('loading-indicator');
    const bar = document.getElementById('loading-bar');
    indicator.style.display = 'block';
    
    // Animate the loading bar
    setTimeout(() => {
      bar.style.width = '100%';
    }, 10);
    
    // Hide after animation completes
    setTimeout(() => {
      indicator.style.display = 'none';
      bar.style.width = '0';
    }, 1400);
  }

  function nextPage(){
    if(current < pages.length - 1 && !isAnimating){
      isAnimating = true;
      showLoadingIndicator();
     
      // Get current and next page
      const currentPage = pages[current];
      const nextPage = pages[current + 1];
     
      // Make sure current page is on top during animation
      currentPage.style.zIndex = 1000;
     
      // Start the flip animation
      currentPage.classList.add('flipped');
     
      // After animation completes, update current and fix z-indexes
      setTimeout(() => {
        current++;
        updatePages();
        isAnimating = false;
      }, 1400); // Match the transition duration
    }
  }
 
  function prevPage(){
    if(current > 0 && !isAnimating){
      isAnimating = true;
      showLoadingIndicator();
     
      // Get current and previous page
      const currentPage = pages[current];
      const prevPage = pages[current - 1];
     
      // Make sure previous page is on top during animation
      prevPage.style.zIndex = 1000;
     
      // Start the flip animation
      prevPage.classList.remove('flipped');
     
      // After animation completes, update current and fix z-indexes
      setTimeout(() => {
        current--;
        updatePages();
        isAnimating = false;
      }, 1400); // Match the transition duration
    }
  }
 
  function goToPage(pageIndex) {
    if (pageIndex >= 0 && pageIndex < pages.length && !isAnimating) {
      isAnimating = true;
      showLoadingIndicator();
     
      // Determine if we're going forward or backward
      if (pageIndex > current) {
        // Going forward - flip current pages one by one
        let pageToFlip = current;
       
        function flipNextPage() {
          if (pageToFlip < pageIndex) {
            const currentPage = pages[pageToFlip];
            currentPage.style.zIndex = 1000;
            currentPage.classList.add('flipped');
           
            pageToFlip++;
           
            if (pageToFlip < pageIndex) {
              setTimeout(flipNextPage, 300); // Small delay between flips
            } else {
              setTimeout(() => {
                current = pageIndex;
                updatePages();
                isAnimating = false;
              }, 1400);
            }
          }
        }
       
        flipNextPage();
      } else if (pageIndex < current) {
        // Going backward - unflip pages one by one
        let pageToUnflip = current - 1;
       
        function unflipPrevPage() {
          if (pageToUnflip >= pageIndex) {
            const prevPage = pages[pageToUnflip];
            prevPage.style.zIndex = 1000;
            prevPage.classList.remove('flipped');
           
            pageToUnflip--;
           
            if (pageToUnflip >= pageIndex) {
              setTimeout(unflipPrevPage, 300); // Small delay between flips
            } else {
              setTimeout(() => {
                current = pageIndex;
                updatePages();
                isAnimating = false;
              }, 1400);
            }
          }
        }
       
        unflipPrevPage();
      }
    }
  }

  // Personal details form validation
  function validateAndProceed() {
    const form = document.getElementById('personalDetailsForm');
    const name = document.getElementById('name').value.trim();
    const age = document.getElementById('age').value;
    const gender = document.querySelector('input[name="gender"]:checked');
    const contact = document.getElementById('contact').value.trim();
    const email = document.getElementById('email').value.trim();
    
    let isValid = true;
    
    // Reset error messages
    document.querySelectorAll('.error-message').forEach(el => {
      el.style.display = 'none';
    });
    
    // Validate name
    if (!name) {
      document.getElementById('name-error').style.display = 'block';
      isValid = false;
    }
    
    // Validate age
    if (!age || age < 1 || age > 120) {
      document.getElementById('age-error').style.display = 'block';
      isValid = false;
    }
    
    // Validate gender
    if (!gender) {
      document.getElementById('gender-error').style.display = 'block';
      isValid = false;
    }
    
    // Validate contact (10-digit number)
    const contactRegex = /^[0-9]{10}$/;
    if (!contact || !contactRegex.test(contact)) {
      document.getElementById('contact-error').style.display = 'block';
      isValid = false;
    }
    
    // Validate email
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!email || !emailRegex.test(email)) {
      document.getElementById('email-error').style.display = 'block';
      isValid = false;
    }
    
    if (isValid) {
      // Store customer details
      customerDetails = {
        name: name,
        age: age,
        gender: gender.value,
        contact: contact,
        email: email
      };
      
      // Save to localStorage
      localStorage.setItem('customerDetails', JSON.stringify(customerDetails));
      
      // Update bill page with customer info
      document.getElementById('bill-name').textContent = name;
      document.getElementById('bill-contact').textContent = contact;
      document.getElementById('bill-email').textContent = email;
      
      // Show success notification
      showNotification('Personal details saved successfully!', 'success');
      
      // Proceed to next page
      nextPage();
    } else {
      // Show error notification
      showNotification('Please correct the errors in the form', 'error');
    }
  }

  // Star rating functionality
  document.addEventListener('DOMContentLoaded', function() {
    const stars = document.querySelectorAll('.star');
    
    stars.forEach(star => {
      star.addEventListener('click', function() {
        selectedRating = parseInt(this.getAttribute('data-rating'));
        updateStarDisplay();
      });
      
      star.addEventListener('mouseover', function() {
        const rating = parseInt(this.getAttribute('data-rating'));
        highlightStars(rating);
      });
      
      // Add keyboard support
      star.addEventListener('keydown', function(e) {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          selectedRating = parseInt(this.getAttribute('data-rating'));
          updateStarDisplay();
        }
      });
    });
    
    document.querySelector('.star-rating').addEventListener('mouseleave', function() {
      updateStarDisplay();
    });
    
    function highlightStars(rating) {
      stars.forEach((star, index) => {
        if (index < rating) {
          star.classList.add('active');
        } else {
          star.classList.remove('active');
        }
      });
    }
    
    function updateStarDisplay() {
      highlightStars(selectedRating);
    }

    // Card payment form formatting and validation
    const cardNumber = document.getElementById('card-number');
    const cardExpiry = document.getElementById('card-expiry');
    const cardCVV = document.getElementById('card-cvv');
    const cardForm = document.getElementById('card-form');
    
    // Format card number with spaces
    cardNumber.addEventListener('input', function() {
      let value = this.value.replace(/\s+/g, '').replace(/[^0-9]/gi, '');
      let formattedValue = value.match(/.{1,4}/g)?.join(' ') || value;
      this.value = formattedValue;
    });
    
    // Format expiry date
    cardExpiry.addEventListener('input', function() {
      let value = this.value.replace(/\s+/g, '').replace(/[^0-9]/gi, '');
      if (value.length >= 2) {
        value = value.substring(0, 2) + '/' + value.substring(2, 4);
      }
      this.value = value;
    });
    
    // Only allow numbers in CVV
    cardCVV.addEventListener('input', function() {
      this.value = this.value.replace(/[^0-9]/g, '');
    });
    
    // Handle card form submission
    cardForm.addEventListener('submit', function(e) {
      e.preventDefault();
      
      // Reset error messages
      document.querySelectorAll('#card-payment-form .error-message').forEach(el => {
        el.style.display = 'none';
      });
      
      // Get form values
      const cardNum = cardNumber.value.replace(/\s+/g, '');
      const cardName = document.getElementById('card-name').value.trim();
      const cardExp = cardExpiry.value;
      const cvv = cardCVV.value;
      
      let isValid = true;
      
      // Validate card number (basic check for 16 digits)
      if (!cardNum || cardNum.length !== 16 || isNaN(cardNum)) {
        document.getElementById('card-number-error').style.display = 'block';
        isValid = false;
      }
      
      // Validate cardholder name
      if (!cardName) {
        document.getElementById('card-name-error').style.display = 'block';
        isValid = false;
      }
      
      // Validate expiry date (MM/YY format)
      const expiryRegex = /^(0[1-9]|1[0-2])\/\d{2}$/;
      if (!cardExp || !expiryRegex.test(cardExp)) {
        document.getElementById('card-expiry-error').style.display = 'block';
        isValid = false;
      } else {
        // Check if expiry date is in the future
        const [month, year] = cardExp.split('/').map(num => parseInt(num, 10));
        const currentDate = new Date();
        const currentYear = currentDate.getFullYear() % 100; // Get last two digits
        const currentMonth = currentDate.getMonth() + 1;
        
        if (year < currentYear || (year === currentYear && month < currentMonth)) {
          document.getElementById('card-expiry-error').textContent = 'Card has expired';
          document.getElementById('card-expiry-error').style.display = 'block';
          isValid = false;
        }
      }
      
      // Validate CVV (3 digits)
      if (!cvv || cvv.length !== 3 || isNaN(cvv)) {
        document.getElementById('card-cvv-error').style.display = 'block';
        isValid = false;
      }
      
      if (isValid) {
        // Show processing notification
        showNotification('Processing card payment...', 'success');
        
        // Simulate payment processing
        setTimeout(() => {
          showNotification('Card payment successful!', 'success');
          // Enable next button
          document.getElementById('payment-next-btn').disabled = false;
          
          // Save payment method
          localStorage.setItem('paymentMethod', 'Card');
          
          // Reset form
          cardForm.reset();
        }, 2000);
      } else {
        showNotification('Please correct the errors in the form', 'error');
      }
    });

    // Dark mode toggle functionality
    const darkModeToggle = document.getElementById('dark-mode-toggle');
    const darkModeIcon = document.getElementById('dark-mode-icon');
    
    // Load saved dark mode preference
    const savedDarkMode = localStorage.getItem('darkMode');
    if (savedDarkMode === 'true') {
      isDarkMode = true;
      document.body.classList.add('dark-mode');
      darkModeIcon.classList.remove('fa-moon');
      darkModeIcon.classList.add('fa-sun');
    }
    
    darkModeToggle.addEventListener('click', function() {
      isDarkMode = !isDarkMode;
      
      if (isDarkMode) {
        document.body.classList.add('dark-mode');
        darkModeIcon.classList.remove('fa-moon');
        darkModeIcon.classList.add('fa-sun');
        showNotification('Dark mode enabled', 'success');
      } else {
        document.body.classList.remove('dark-mode');
        darkModeIcon.classList.remove('fa-sun');
        darkModeIcon.classList.add('fa-moon');
        showNotification('Light mode enabled', 'success');
      }
      
      // Save preference to localStorage
      localStorage.setItem('darkMode', isDarkMode);
    });
  });

  // Keyboard navigation: left/right
  document.addEventListener('keydown', (e) => {
    if(e.key === 'ArrowRight') nextPage();
    if(e.key === 'ArrowLeft') prevPage();
    if(e.key === 'Escape' && overlay.style.display === 'flex') closeOrder();
    if(e.key === 'Escape' && document.getElementById('cart-overlay').style.display === 'flex') closeCart();
    if(e.key === 'Escape' && document.getElementById('confirm-dialog').style.display === 'flex') closeConfirmDialog();
    if(e.key === 'Escape' && document.getElementById('email-confirm-dialog').style.display === 'flex') closeEmailConfirmDialog();
  });

  // Order popup
  const overlay = document.getElementById('overlay');
  const orderForm = document.getElementById('orderForm');
  const orderItem = document.getElementById('order-item');
  const orderPrice = document.getElementById('order-price');
  const orderQty = document.getElementById('order-qty');
  const orderNotes = document.getElementById('order-notes');
  const cancelBtn = document.getElementById('cancelBtn');

  function openOrder(name, price){
    orderItem.value = name;
    orderPrice.value = price;
    orderQty.value = 1;
    orderNotes.value = '';
    overlay.style.display = 'flex';
    overlay.setAttribute('aria-hidden','false');
    orderQty.focus();
  }

  function closeOrder(){
    overlay.style.display = 'none';
    overlay.setAttribute('aria-hidden','true');
  }
  cancelBtn.addEventListener('click', closeOrder);
  overlay.addEventListener('click', (e) => {
    if(e.target === overlay) closeOrder();
  });

  // Cart functionality
  function addToCart(name, price, quantity, notes) {
    // Check if item already exists in cart
    const existingItemIndex = cart.findIndex(item => item.name === name);
    
    if (existingItemIndex !== -1) {
      // Update quantity if item already exists
      cart[existingItemIndex].quantity += quantity;
    } else {
      // Add new item to cart
      cart.push({
        name: name,
        price: parseFloat(price),
        quantity: quantity,
        notes: notes
      });
    }
    
    // Save cart to localStorage
    localStorage.setItem('cart', JSON.stringify(cart));
    
    // Update cart count
    updateCartCount();
    
    // Update cart display if cart popup is open
    updateCartDisplay();
    
    // Update bill display if on bill page
    if (current === 13) {
      updateBillDisplay();
    }
  }

  function removeFromCart(index) {
    // Show confirmation dialog
    showConfirmDialog('Are you sure you want to remove this item from your cart?', () => {
      cart.splice(index, 1);
      updateCartCount();
      updateCartDisplay();
      
      // Save updated cart to localStorage
      localStorage.setItem('cart', JSON.stringify(cart));
      
      if (current === 13) {
        updateBillDisplay();
      }
      
      showNotification('Item removed from cart', 'success');
    });
  }

  function updateCartCount() {
    const count = cart.reduce((total, item) => total + item.quantity, 0);
    document.getElementById('cart-count').textContent = count;
  }

  function updateCartDisplay() {
    const cartItemsContainer = document.getElementById('cart-items');
    const cartTotalContainer = document.getElementById('cart-total');
    const cartTotalAmount = document.getElementById('cart-total-amount');
    
    if (cart.length === 0) {
      cartItemsContainer.innerHTML = '<div class="empty-cart"><p>Your cart is empty</p></div>';
      cartTotalContainer.style.display = 'none';
    } else {
      let itemsHTML = '';
      let total = 0;
      
      cart.forEach((item, index) => {
        const itemTotal = item.price * item.quantity;
        total += itemTotal;
        
        itemsHTML += `
          <div class="bill-item">
            <div class="item-details">
              <div class="item-name">${item.name} x ${item.quantity}</div>
              ${item.notes ? `<div class="item-notes">${item.notes}</div>` : ''}
            </div>
            <div class="item-price">₹${itemTotal.toFixed(2)}</div>
            <button onclick="removeFromCart(${index});" style="background: #e74c3c; color: white; border: none; border-radius: 50%; width: 24px; height: 24px; margin-left: 10px; cursor: pointer;" aria-label="Remove item">×</button>
          </div>
        `;
      });
      
      cartItemsContainer.innerHTML = itemsHTML;
      cartTotalAmount.textContent = total.toFixed(2);
      cartTotalContainer.style.display = 'block';
    }
  }

  function updateBillDisplay() {
    const billItemsContainer = document.getElementById('bill-items');
    const billTotalContainer = document.getElementById('bill-total');
    const totalAmountElement = document.getElementById('total-amount');
    
    if (cart.length === 0) {
      billItemsContainer.innerHTML = `
        <div class="empty-cart">
          <i class="fas fa-receipt"></i>
          <p>Your cart is empty</p>
          <p>Add items from the menu to see them here</p>
        </div>
      `;
      billTotalContainer.style.display = 'none';
    } else {
      let itemsHTML = '';
      let total = 0;
      
      cart.forEach(item => {
        const itemTotal = item.price * item.quantity;
        total += itemTotal;
        
        itemsHTML += `
          <div class="bill-item">
            <div class="item-details">
              <div class="item-name">${item.name} x ${item.quantity}</div>
              ${item.notes ? `<div class="item-notes">${item.notes}</div>` : ''}
            </div>
            <div class="item-price">₹${itemTotal.toFixed(2)}</div>
          </div>
        `;
      });
      
      billItemsContainer.innerHTML = itemsHTML;
      totalAmountElement.textContent = total.toFixed(2);
      billTotalContainer.style.display = 'block';
    }
  }

  function showCart() {
    const cartOverlay = document.getElementById('cart-overlay');
    cartOverlay.style.display = 'flex';
    cartOverlay.setAttribute('aria-hidden', 'false');
    updateCartDisplay();
  }

  function closeCart() {
    const cartOverlay = document.getElementById('cart-overlay');
    cartOverlay.style.display = 'none';
    cartOverlay.setAttribute('aria-hidden', 'true');
  }

  document.getElementById('cart-close-btn').addEventListener('click', closeCart);
  document.getElementById('cart-overlay').addEventListener('click', (e) => {
    if(e.target === document.getElementById('cart-overlay')) closeCart();
  });

  // Add click listeners to every .item (delegation)
  document.addEventListener('click', (e) => {
    const itemEl = e.target.closest('.item');
    if(!itemEl) return;
    const name = itemEl.dataset.name || itemEl.querySelector('.name')?.textContent?.trim();
    const price = itemEl.dataset.price || itemEl.querySelector('.meta')?.textContent?.replace(/[^\d.]/g,'');
    if(name && price) openOrder(name, price);
  });

  orderForm.addEventListener('submit', (e) => {
    e.preventDefault();
    const name = orderItem.value;
    const price = parseFloat(orderPrice.value || 0);
    const qty = parseInt(orderQty.value || 1, 10);
    if(!qty || qty < 1){ 
      showNotification('Please enter a valid quantity.', 'error');
      orderQty.focus(); 
      return; 
    }
    const notes = orderNotes.value.trim();
    
    // Add to cart
    addToCart(name, price, qty, notes);
    
    // Show notification
    showNotification(`${qty} x ${name} added to your order`, 'success');
    
    closeOrder();
  });

  // Review form submission
  document.getElementById('reviewForm').addEventListener('submit', function(e) {
    e.preventDefault();
    
    const comments = document.getElementById('comments').value.trim();
    
    if (selectedRating === 0) {
      showNotification('Please select a rating.', 'error');
      return;
    }
    
    // In a real application, you would send this data to a server
    const reviewData = {
      customer: customerDetails,
      rating: selectedRating,
      comments: comments,
      timestamp: new Date().toISOString()
    };
    
    console.log('Review submitted:', reviewData);
    
    // Save review to localStorage
    const reviews = JSON.parse(localStorage.getItem('reviews') || '[]');
    reviews.push(reviewData);
    localStorage.setItem('reviews', JSON.stringify(reviews));
    
    // Show success message
    document.getElementById('review-success').style.display = 'block';
    
    // Reset form
    document.getElementById('comments').value = '';
    selectedRating = 0;
    document.querySelectorAll('.star').forEach(star => {
      star.classList.remove('active');
    });
    
    // Hide success message after 5 seconds
    setTimeout(() => {
      document.getElementById('review-success').style.display = 'none';
    }, 5000);
    
    showNotification('Thank you for your feedback!', 'success');
  });

  // Email bill functionality
  function showEmailConfirmDialog() {
    if (cart.length === 0) {
      showNotification('Your cart is empty. Add items before emailing the bill.', 'error');
      return;
    }
    
    if (!customerDetails.email) {
      showNotification('Customer email not found. Please fill in your details first.', 'error');
      return;
    }
    
    // Generate bill content
    let billContent = `MAD RESTAURANT - BILL\n\n`;
    billContent += `========================================\n`;
    billContent += `CUSTOMER INFORMATION\n`;
    billContent += `========================================\n`;
    billContent += `Name: ${customerDetails.name}\n`;
    billContent += `Contact: ${customerDetails.contact}\n`;
    billContent += `Email: ${customerDetails.email}\n\n`;
    billContent += `========================================\n`;
    billContent += `ORDER DETAILS\n`;
    billContent += `========================================\n`;
    
    let total = 0;
    cart.forEach(item => {
      const itemTotal = item.price * item.quantity;
      total += itemTotal;
      billContent += `${item.name} x ${item.quantity} - ₹${itemTotal.toFixed(2)}\n`;
      if (item.notes) {
        billContent += `Notes: ${item.notes}\n`;
      }
      billContent += `----------------------------------------\n`;
    });
    
    billContent += `\nTOTAL AMOUNT: ₹${total.toFixed(2)}\n`;
    billContent += `========================================\n\n`;
    billContent += `Thank you for dining with us!\n`;
    billContent += `MAD Restaurant - Where Flavor Meets Passion\n\n`;
    billContent += `Date: ${new Date().toLocaleDateString()}\n`;
    billContent += `Time: ${new Date().toLocaleTimeString()}`;
    
    // Set email recipient
    document.getElementById('email-recipient').textContent = customerDetails.email;
    
    // Set email preview
    document.getElementById('email-preview').textContent = billContent;
    
    // Show dialog
    document.getElementById('email-confirm-dialog').style.display = 'flex';
    
    // Set send button action
    document.getElementById('email-send-btn').onclick = function() {
      sendEmailBill(billContent);
    };
  }

  function sendEmailBill(billContent) {
    // Close confirmation dialog
    closeEmailConfirmDialog();
    
    // Show sending progress
    document.getElementById('sending-email-recipient').textContent = customerDetails.email;
    document.getElementById('email-sending-progress').style.display = 'flex';
    
    // Animate progress bar
    const progressFill = document.getElementById('email-progress-fill');
    progressFill.style.width = '0%';
    
    setTimeout(() => {
      progressFill.style.width = '30%';
    }, 500);
    
    setTimeout(() => {
      progressFill.style.width = '60%';
    }, 1000);
    
    setTimeout(() => {
      progressFill.style.width = '90%';
    }, 1500);
    
    // Simulate email sending process
    setTimeout(() => {
      // Hide sending progress
      document.getElementById('email-sending-progress').style.display = 'none';
      
      // Generate HTML bill for the new tab
      let total = 0;
      let itemsHTML = '';
      
      cart.forEach(item => {
        const itemTotal = item.price * item.quantity;
        total += itemTotal;
        
        itemsHTML += `
          <tr>
            <td>${item.name}</td>
            <td>${item.quantity}</td>
            <td>₹${item.price.toFixed(2)}</td>
            <td>₹${itemTotal.toFixed(2)}</td>
          </tr>
        `;
        
        if (item.notes) {
          itemsHTML += `
            <tr>
              <td colspan="4" style="font-style: italic; color: #666; font-size: 0.9rem; padding-left: 20px;">Notes: ${item.notes}</td>
            </tr>
          `;
        }
      });
      
      const htmlBill = `
        <!DOCTYPE html>
        <html lang="en">
        <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>MAD Restaurant - Bill</title>
          <style>
            body {
              font-family: 'Montserrat', sans-serif;
              line-height: 1.6;
              color: #333;
              max-width: 800px;
              margin: 0 auto;
              padding: 20px;
              background-color: #fffdf9;
            }
            .header {
              text-align: center;
              margin-bottom: 30px;
              border-bottom: 2px solid #9c7b56;
              padding-bottom: 20px;
            }
            .restaurant-name {
              font-family: 'Playfair Display', serif;
              font-size: 2.5rem;
              color: #4b2e1e;
              margin-bottom: 10px;
            }
            .subtitle {
              font-style: italic;
              color: #9c7b56;
            }
            .section-title {
              font-family: 'Playfair Display', serif;
              font-size: 1.2rem;
              color: #4b2e1e;
              margin-top: 25px;
              margin-bottom: 10px;
              border-bottom: 1px solid #e8e2d5;
              padding-bottom: 5px;
            }
            .customer-info {
              margin-bottom: 20px;
            }
            .customer-info p {
              margin: 5px 0;
            }
            table {
              width: 100%;
              border-collapse: collapse;
              margin-bottom: 20px;
            }
            th, td {
              padding: 10px;
              text-align: left;
              border-bottom: 1px solid #e8e2d5;
            }
            th {
              background-color: #f5f1e8;
              font-weight: 600;
            }
            .total-row {
              font-weight: bold;
              background-color: #f5f1e8;
            }
            .total-row td {
              font-size: 1.1rem;
              color: #9c7b56;
            }
            .footer {
              margin-top: 40px;
              text-align: center;
              font-style: italic;
              color: #666;
              border-top: 1px solid #e8e2d5;
              padding-top: 20px;
            }
            .print-btn {
              display: block;
              margin: 20px auto;
              padding: 10px 20px;
              background-color: #9c7b56;
              color: white;
              border: none;
              border-radius: 4px;
              cursor: pointer;
              font-family: 'Montserrat', sans-serif;
              font-weight: 600;
            }
            .print-btn:hover {
              background-color: #7e6645;
            }
            @media print {
              .print-btn {
                display: none;
              }
              body {
                background-color: white;
              }
            }
          </style>
        </head>
        <body>
          <div class="header">
            <div class="restaurant-name">MAD RESTAURANT</div>
            <div class="subtitle">Where Flavor Meets Passion</div>
          </div>
          
          <div class="customer-info">
            <div class="section-title">CUSTOMER INFORMATION</div>
            <p><strong>Name:</strong> ${customerDetails.name}</p>
            <p><strong>Contact:</strong> ${customerDetails.contact}</p>
            <p><strong>Email:</strong> ${customerDetails.email}</p>
          </div>
          
          <div class="order-details">
            <div class="section-title">ORDER DETAILS</div>
            <table>
              <thead>
                <tr>
                  <th>Item</th>
                  <th>Quantity</th>
                  <th>Price</th>
                  <th>Total</th>
                </tr>
              </thead>
              <tbody>
                ${itemsHTML}
                <tr class="total-row">
                  <td colspan="3">TOTAL AMOUNT</td>
                  <td>₹${total.toFixed(2)}</td>
                </tr>
              </tbody>
            </table>
          </div>
          
          <div class="footer">
            <p>Thank you for dining with us!</p>
            <p>MAD Restaurant - Where Flavor Meets Passion</p>
            <p>Date: ${new Date().toLocaleDateString()}</p>
            <p>Time: ${new Date().toLocaleTimeString()}</p>
          </div>
          
          <button class="print-btn" onclick="window.print()">Print Bill</button>
        </body>
        </html>
      `;
      
      // Create a new tab with the bill
      const billTab = window.open();
      billTab.document.write(htmlBill);
      billTab.document.close();
      
      // Show success dialog
      document.getElementById('success-email-recipient').textContent = customerDetails.email;
      document.getElementById('email-sent-time').textContent = new Date().toLocaleString();
      document.getElementById('email-success-dialog').style.display = 'flex';
      
      // Save sent email record
      const sentEmails = JSON.parse(localStorage.getItem('sentEmails') || '[]');
      sentEmails.push({
        recipient: customerDetails.email,
        subject: 'MAD Restaurant - Your Order Bill',
        content: billContent,
        timestamp: new Date().toISOString()
      });
      localStorage.setItem('sentEmails', JSON.stringify(sentEmails));
      
      showNotification('Bill sent successfully to ' + customerDetails.email, 'success');
    }, 2000);
  }

  function closeEmailConfirmDialog() {
    document.getElementById('email-confirm-dialog').style.display = 'none';
  }

  function closeEmailSuccessDialog() {
    document.getElementById('email-success-dialog').style.display = 'none';
  }

  // Notification system
  function showNotification(message, type = 'success') {
    const notification = document.getElementById('notification');
    const notificationMessage = document.getElementById('notification-message');
    const icon = notification.querySelector('i');
    
    // Set message
    notificationMessage.textContent = message;
    
    // Set type and icon
    notification.className = 'notification';
    if (type === 'error') {
      notification.classList.add('error');
      icon.className = 'fas fa-exclamation-circle';
    } else {
      notification.classList.add('success');
      icon.className = 'fas fa-check-circle';
    }
    
    // Show notification
    notification.classList.add('show');
    
    // Hide after 3 seconds
    setTimeout(() => {
      notification.classList.remove('show');
    }, 3000);
  }

  // Confirmation dialog
  function showConfirmDialog(message, onConfirm) {
    const dialog = document.getElementById('confirm-dialog');
    const messageElement = document.getElementById('confirm-message');
    const confirmButton = document.getElementById('confirm-yes-btn');
    
    // Set message
    messageElement.textContent = message;
    
    // Set confirm action
    confirmButton.onclick = function() {
      onConfirm();
      closeConfirmDialog();
    };
    
    // Show dialog
    dialog.style.display = 'flex';
  }

  function closeConfirmDialog() {
    const dialog = document.getElementById('confirm-dialog');
    dialog.style.display = 'none';
  }

  // Payment mode selection
  function selectPaymentMode(mode) {
    selectedPaymentMode = mode;
    
    // Hide all payment forms
    document.getElementById('card-payment-form').style.display = 'none';
    document.getElementById('upi-payment-form').style.display = 'none';
    
    // Handle different payment modes
    if (mode === 'cash') {
      // Show confirmation dialog
      showConfirmDialog('Are you sure you want to pay with cash? You will be redirected to the bill page.', () => {
        showNotification('Cash payment selected. Please pay at the counter.', 'success');
        // Go back to bill page
        setTimeout(() => {
          goToPage(13);
        }, 1500);
      });
    } else if (mode === 'card') {
      // Show card payment form
      document.getElementById('card-payment-form').style.display = 'block';
      // Disable next button until payment is processed
      document.getElementById('payment-next-btn').disabled = true;
    } else if (mode === 'upi') {
      // Show UPI payment form
      document.getElementById('upi-payment-form').style.display = 'block';
      // Disable next button until payment is confirmed
      document.getElementById('payment-next-btn').disabled = true;
      
      // Generate QR code
      generateQRCode();
    }
  }

  function generateQRCode() {
    const qrContainer = document.getElementById('qr-code-container');
    
    // Generate a random transaction ID
    const transactionId = 'MAD' + Math.random().toString(36).substr(2, 9).toUpperCase();
    
    // Calculate total amount from cart
    const totalAmount = cart.reduce((total, item) => total + (item.price * item.quantity), 0).toFixed(2);
    
    // UPI payment details
    const upiDetails = {
      pa: 'madrestaurant@paytm',  // UPI ID
      pn: 'MAD Restaurant',        // Payee name
      tr: transactionId,           // Transaction ID
      tn: 'Payment for MAD Restaurant', // Transaction note
      am: totalAmount,             // Amount
      cu: 'INR'                    // Currency
    };
    
    // Create UPI payment URL
    const upiUrl = `upi://pay?pa=${upiDetails.pa}&pn=${encodeURIComponent(upiDetails.pn)}&tr=${upiDetails.tr}&tn=${encodeURIComponent(upiDetails.tn)}&am=${upiDetails.am}&cu=${upiDetails.cu}`;
    
    // Generate QR code using QRServer API
    const qrApiUrl = `https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=${encodeURIComponent(upiUrl)}`;
    
    // Create QR code image
    const qrImage = document.createElement('img');
    qrImage.src = qrApiUrl;
    qrImage.alt = 'UPI Payment QR Code';
    qrImage.style.maxWidth = '100%';
    qrImage.style.maxHeight = '100%';
    qrImage.style.borderRadius = '8px';
    
    // Clear previous QR code and add new one
    qrContainer.innerHTML = '';
    qrContainer.appendChild(qrImage);
    
    // Store transaction ID for later reference
    localStorage.setItem('currentTransactionId', transactionId);
    
    // Show notification that QR code is generated
    showNotification('QR code generated successfully!', 'success');
  }

  function cancelCardPayment() {
    document.getElementById('card-payment-form').style.display = 'none';
    selectedPaymentMode = '';
  }

  function cancelUPIPayment() {
    document.getElementById('upi-payment-form').style.display = 'none';
    selectedPaymentMode = '';
  }

  function confirmUPIPayment() {
    // Show processing notification
    showNotification('Processing UPI payment...', 'success');
    
    // Simulate payment processing
    setTimeout(() => {
      showNotification('UPI payment successful!', 'success');
      // Enable next button
      document.getElementById('payment-next-btn').disabled = false;
      
      // Save payment method
      localStorage.setItem('paymentMethod', 'UPI');
    }, 2000);
  }

  // Load saved data on page load
  function loadSavedData() {
    // Load saved page
    const savedPage = localStorage.getItem('currentPage');
    if (savedPage && !isNaN(savedPage)) {
      current = parseInt(savedPage);
      updatePages();
    }
    
    // Load customer details
    const savedCustomerDetails = localStorage.getItem('customerDetails');
    if (savedCustomerDetails) {
      customerDetails = JSON.parse(savedCustomerDetails);
      
      // Update form fields
      document.getElementById('name').value = customerDetails.name || '';
      document.getElementById('age').value = customerDetails.age || '';
      if (customerDetails.gender) {
        document.getElementById(customerDetails.gender).checked = true;
      }
      document.getElementById('contact').value = customerDetails.contact || '';
      document.getElementById('email').value = customerDetails.email || '';
      
      // Update bill page
      document.getElementById('bill-name').textContent = customerDetails.name || '';
      document.getElementById('bill-contact').textContent = customerDetails.contact || '';
      document.getElementById('bill-email').textContent = customerDetails.email || '';
    }
    
    // Load cart
    const savedCart = localStorage.getItem('cart');
    if (savedCart) {
      cart = JSON.parse(savedCart);
      updateCartCount();
    }
  }

  // Initialize
  initZIndexes();
  updatePages();
  loadSavedData();

  // Expose for inline onclick handlers
  window.nextPage = nextPage;
  window.prevPage = prevPage;
  window.goToPage = goToPage;
  window.validateAndProceed = validateAndProceed;
  window.showCart = showCart;
  window.closeCart = closeCart;
  window.removeFromCart = removeFromCart;
  window.showConfirmDialog = showConfirmDialog;
  window.closeConfirmDialog = closeConfirmDialog;
  window.showEmailConfirmDialog = showEmailConfirmDialog;
  window.closeEmailConfirmDialog = closeEmailConfirmDialog;
  window.closeEmailSuccessDialog = closeEmailSuccessDialog;
  window.sendEmailBill = sendEmailBill;
  window.selectPaymentMode = selectPaymentMode;
  window.cancelCardPayment = cancelCardPayment;
  window.cancelUPIPayment = cancelUPIPayment;
  window.confirmUPIPayment = confirmUPIPayment;
</script>

</body>
</html>

