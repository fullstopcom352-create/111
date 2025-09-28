<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard Page</title>
  <!-- Bootstrap CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      background-color: #111;
      color: white;
    }
    .navbar {
      background-color: #000;
    }
    .card {
      border-radius: 12px;
      overflow: hidden;
    }
    .shorts img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      border-radius: 10px;
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <nav class="navbar navbar-dark px-3">
    <a class="navbar-brand" href="#">MyTube</a>
    <div>
      <button class="btn btn-outline-light btn-sm">Search</button>
      <button class="btn btn-outline-light btn-sm">Profile</button>
    </div>
  </nav>

  <!-- Banner Section -->
  <div class="container my-3">
    <div class="card bg-dark text-white">
      <img src="https://via.placeholder.com/800x250.png?text=India+vs+Sri+Lanka+Banner" class="card-img" alt="Banner">
      <div class="card-img-overlay d-flex flex-column justify-content-end">
        <h5 class="card-title">Live Now - India vs Sri Lanka</h5>
        <a href="#" class="btn btn-danger btn-sm">Watch Live</a>
      </div>
    </div>
  </div>

  <!-- Shorts Section -->
  <div class="container">
    <h4 class="mb-3">Shorts</h4>
    <div class="row g-3 shorts">
      <div class="col-6 col-md-3">
        <img src="https://via.placeholder.com/200x300.png?text=Short+1" alt="Short 1">
      </div>
      <div class="col-6 col-md-3">
        <img src="https://via.placeholder.com/200x300.png?text=Short+2" alt="Short 2">
      </div>
      <div class="col-6 col-md-3">
        <img src="https://via.placeholder.com/200x300.png?text=Short+3" alt="Short 3">
      </div>
      <div class="col-6 col-md-3">
        <img src="https://via.placeholder.com/200x300.png?text=Short+4" alt="Short 4">
      </div>
    </div>
  </div>

  <!-- Bottom Navigation -->
  <nav class="navbar fixed-bottom navbar-dark bg-dark d-flex justify-content-around">
    <a class="nav-link text-white" href="#">Home</a>
    <a class="nav-link text-white" href="#">Shorts</a>
    <a class="nav-link text-white" href="#">+</a>
    <a class="nav-link text-white" href="#">Subscriptions</a>
    <a class="nav-link text-white" href="#">You</a>
  </nav>

  <!-- Bootstrap JS -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
