<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>YouTube Dashboard - Static</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #ffffff;
      color: #000;
    }
    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 10px 20px;
      background: #f1f1f1;
      position: sticky;
      top: 0;
      z-index: 1000;
      border-bottom: 1px solid #ddd;
    }
    .navbar .logo {
      font-size: 20px;
      color: red;
      font-weight: bold;
    }
    .content {
      padding: 20px;
    }
    h2 {
      margin-bottom: 10px;
      border-left: 4px solid red;
      padding-left: 8px;
    }

    /* Shorts Section */
    .shorts-container {
      display: flex;
      gap: 10px;
      overflow-x: auto;
      padding: 10px 0;
    }
    .shorts-container iframe {
      width: 200px;
      height: 350px;
      border-radius: 10px;
      border: none;
    }

    /* Recommended Section */
    .videos {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      gap: 20px;
    }
    .video-card {
      background: #fafafa;
      border-radius: 10px;
      overflow: hidden;
      border: 1px solid #ddd;
      cursor: pointer;
      transition: transform 0.3s;
    }
    .video-card:hover {
      transform: scale(1.03);
    }
    .thumbnail {
      width: 100%;
      height: 180px;
      background-size: cover;
      background-position: center;
    }
    .video-info {
      padding: 10px;
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: rgba(0,0,0,0.8);
      justify-content: center;
      align-items: center;
      z-index: 2000;
    }
    .modal iframe {
      width: 80%;
      height: 70%;
      border: none;
    }
    .modal .close {
      position: absolute;
      top: 20px; right: 40px;
      font-size: 30px;
      color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <div class="navbar">
    <div class="logo">YouTube</div>
    <div class="icons">Static Mode</div>
  </div>

  <!-- Content -->
  <div class="content">
    <h2>Shorts</h2>
    <div class="shorts-container">
      <iframe src="https://www.youtube.com/embed/YJG0nR81UO0" allowfullscreen></iframe>
      <iframe src="https://www.youtube.com/embed/VF4IQo0M-QE" allowfullscreen></iframe>
      <iframe src="https://www.youtube.com/embed/eMLJyNEectg" allowfullscreen></iframe>
      <iframe src="https://www.youtube.com/embed/8yOEc7tnFmQ" allowfullscreen></iframe>
    </div>

    <h2>Recommended</h2>
    <div class="videos">
      <div class="video-card" onclick="openModal('YJG0nR81UO0')">
        <div class="thumbnail" style="background-image:url('https://img.youtube.com/vi/YJG0nR81UO0/hqdefault.jpg')"></div>
        <div class="video-info"><h4>Video 1</h4><p>Shorts Content</p></div>
      </div>

      <div class="video-card" onclick="openModal('VF4IQo0M-QE')">
        <div class="thumbnail" style="background-image:url('https://img.youtube.com/vi/VF4IQo0M-QE/hqdefault.jpg')"></div>
        <div class="video-info"><h4>Video 2</h4><p>Shorts Content</p></div>
      </div>

      <div class="video-card" onclick="openModal('eMLJyNEectg')">
        <div class="thumbnail" style="background-image:url('https://img.youtube.com/vi/eMLJyNEectg/hqdefault.jpg')"></div>
        <div class="video-info"><h4>Video 3</h4><p>Shorts Content</p></div>
      </div>

      <div class="video-card" onclick="openModal('8yOEc7tnFmQ')">
        <div class="thumbnail" style="background-image:url('https://img.youtube.com/vi/8yOEc7tnFmQ/hqdefault.jpg')"></div>
        <div class="video-info"><h4>Video 4</h4><p>Shorts Content</p></div>
      </div>
    </div>
  </div>

  <!-- Modal -->
  <div class="modal" id="videoModal">
    <span class="close" onclick="closeModal()">&times;</span>
    <iframe id="modalVideo" allowfullscreen></iframe>
  </div>

  <script>
    const modal = document.getElementById("videoModal");
    const modalVideo = document.getElementById("modalVideo");

    function openModal(videoId) {
      modal.style.display = "flex";
      modalVideo.src = `https://www.youtube.com/embed/${videoId}`;
    }
    function closeModal() {
      modal.style.display = "none";
      modalVideo.src = "";
    }
  </script>

</body>
</html>
