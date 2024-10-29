# Buku-Tamu
Tugas Sekolah
<?php
$host = 'localhost';
$db = 'tamu'; // Ganti dengan nama database Anda
$user = 'root'; // Ganti dengan username database Anda
$pass = ''; // Ganti dengan password database Anda

try {
    // Mencoba untuk membuat koneksi ke database 
    $pdo = new PDO("mysql:host=$host;dbname=$db", $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    // Menangani kesalahan koneksi
    die("Connection failed: " . $e->getMessage());
}
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
  // Mengambil data dari form
  $nama = $_POST['nama'];
  $statuss = $_POST['statuss'];
  $instansi = isset($_POST['instansi']) ? $_POST['instansi'] : null; // Nullable jika 'Pribadi'
  $jumlah_tamu = $_POST['jml'];
  $maksud = $_POST['maksud'];

  try {
      // Menyiapkan query untuk menyimpan data
      $stmt = $pdo->prepare("INSERT INTO buku_tamu (nama, statuss, instansi, jumlah_tamu, maksud_kedatangan) VALUES (?, ?, ?, ?, ?)");
      $stmt->execute([$nama, $statuss, $instansi, $jumlah_tamu, $maksud]);
      echo "Data berhasil disimpan!";
  } catch (PDOException $e) {
      // Menangani kesalahan saat menyimpan data
      echo "Error: " . $e->getMessage();
  }
}

?>

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
  <title>Buku Tamu </title>
  <link rel="stylesheet" type="text/css" href="css/bootstrap.css" />
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/jquery-nice-select/1.1.0/css/nice-select.min.css" />
  <link href="css/font-awesome.min.css" rel="stylesheet" />
  <link href="css/style.css" rel="stylesheet" />
  <link href="css/responsive.css" rel="stylesheet" />
  <style>
    html {
      scroll-behavior: smooth;
    }
  </style>
</head>
<body>
  <div class="hero_area">
    <header class="header_section">
      <div class="header_top">
        <div class="container-fluid header_top_container">
          <a class="navbar-brand" href="#home"> Buku<span>Tamu</span> </a>
          <div class="contact_nav">
            <a href=""><i class="fa fa-map-marker" aria-hidden="true"></i><span> Jl.Suliki no 1.Jati baru,padang Timur </span></a>
            <a href=""><i class="fa fa-phone" aria-hidden="true"></i><span> Call : + 0751 21907 </span></a>
            <a href=""><i class="fa fa-envelope" aria-hidden="true"></i><span> smksixpdg@gmail.com </span></a>
          </div>
          <div class="social_box">
            <a href=""><i class="fa fa-facebook" aria-hidden="true"></i></a>
            <a href=""><i class="fa fa-twitter" aria-hidden="true"></i></a>
            <a href=""><i class="fa fa-linkedin" aria-hidden="true"></i></a>
            <a href=""><i class="fa fa-instagram" aria-hidden="true"></i></a>
          </div>
        </div>
      </div>
      <div class="header_bottom">
        <div class="container-fluid">
          <nav class="navbar navbar-expand-lg custom_nav-container">
            <a class="navbar-brand navbar_brand_mobile" href="#home"> Buku<span>Tamu</span> </a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
              <span class=""></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
              <ul class="navbar-nav">
                <li class="nav-item active"><a class="nav-link" href="#home">Home</a></li>
                <li class="nav-item"><a class="nav-link" href="#buku">Buku Tamu</a></li>
                <li class="nav-item"><a class="nav-link" href="#kontak">Kontak</a></li>
              </ul>
            </div>
          </nav>
        </div>
      </div>
    </header>

    <section class="slider_section">
      <div id="customCarousel1" class="carousel slide" data-ride="carousel">
        <div class="carousel-inner">
          <div class="carousel-item active">
            <div class="container">
              <div class="detail-box">
                <h1>BUKU TAMU <br />SMK NEGERI 6 PADANG <br /></h1>
              </div>
              <div class="image-box" style="margin-top: -100px;">
                <img src="images/sekolah.jpeg" alt="Description of Image" class="d-block w-100" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>


  <!DOCTYPE html>
  <html lang="en">
  
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    <title>Troweld</title>
    <link rel="stylesheet" type="text/css" href="css/bootstrap.css" />
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/OwlCarousel2/2.3.4/assets/owl.carousel.min.css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/jquery-nice-select/1.1.0/css/nice-select.min.css" />
    <link href="css/font-awesome.min.css" rel="stylesheet" />
    <link href="css/style.css" rel="stylesheet" />
    <link href="css/responsive.css" rel="stylesheet" />
    <style>
      html {
        scroll-behavior: smooth;
      }
      .map_container {
        height: 100%; /* Ensure the map takes full height */
      }
    </style>
  </head>
  
  
  
  <html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Buku Tamu</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
    <style>
        body {
            background-color: #e0f7fa; /* Mengubah latar belakang menjadi biru muda */
        }
        .hidden { display: none; }
        .form_container { 
            background-color: #007bff; 
            padding: 20px; 
            border-radius: 8px; 
            color: white; 
            height: 100%; /* Memastikan tinggi penuh */
        }
        .form_container input, .form_container select { 
            background-color: #0056b3; 
            color: white; 
            border: none; 
        }
        .form_container input::placeholder, .form_container select::placeholder { 
            color: #cce5ff; 
        }
        .map_container { 
            height: 350px; 
            margin-top: 25px; 
        }
    </style>
</head>
<body>
<section id="buku" class="contact section bg-light py-5">
<div class="container mt-5">
    <div class="row gy-4 justify-content-center">
        <div class="col-lg-8">
            <form action="" method="post" class="shadow-lg p-4 rounded bg-white">
                <h2 class="text-center mb-4">Buku Tamu</h2>
                <div class="row gy-4">
                    <div class="col-md-6">
                        <label for="nama" class="pb-2">Nama</label>
                        <input type="text" name="nama" id="nama" class="form-control" placeholder="Tuliskan Nama Tamu" required>
                    </div>
                    <div class="col-md-6">
                        <label for="statuss" class="pb-2">Asal</label>
                        <select class="form-control" name="statuss" id="statuss" required onchange="tampilkanNamaInstansi(this)">
                            <option value="">Pilih Instansi / Pribadi</option>
                            <option value="Pribadi">Pribadi</option>
                            <option value="Instansi">Instansi</option>
                        </select>
                    </div>
                    <div class="col-md-8" id="input_instansi" style="display: none;">
                        <label for="instansi" class="pb-2">Nama Instansi</label>
                        <input type="text" class="form-control" name="instansi" placeholder="Tuliskan Nama Instansi" id="instansi">
                    </div>
                    <div class="col-md-4">
                        <label for="jml" class="pb-2">Jumlah Tamu</label>
                        <input type="number" class="form-control" name="jml" id="jml" placeholder="Tuliskan Jumlah Tamu" required>
                    </div>
                    <div class="col-md-12">
                        <label for="maksud" class="pb-2">Maksud Kedatangan</label>
                        <textarea class="form-control" name="maksud" rows="4" id="maksud" placeholder="Tuliskan Maksud kedatangan" required></textarea>
                    </div>
                    <div class="col text-center">
                        <button type="submit" class="btn btn-gradient btn-lg mt-3">Simpan</button>
                    </div>
                </div>
            </form>
        </div>
    </div>
</div>

<script>
    function tampilkanNamaInstansi(select) {
        const instansiInput = document.getElementById("input_instansi");
        instansiInput.style.display = select.value === "Instansi" ? "block" : "none";
    }
</script>

<style>
    body {
        background-color: #f8f9fa; /* Latar belakang abu-abu terang */
    }
    .form-control {
        border-radius: 20px; /* Sudut membulat pada input */
    }
    .btn-gradient {
        background: linear-gradient(90deg, #ff7e5f, #feb47b); /* Gradasi warna untuk tombol */
        border-radius: 20px; /* Sudut membulat pada tombol */
        color: white; /* Warna teks putih */
        border: none; /* Menghilangkan border */
        transition: background 0.3s;
    }
    .btn-gradient:hover {
        background: linear-gradient(90deg, #feb47b, #ff7e5f); /* Warna lebih terang saat hover */
    }
</style>

                </div>
            </form>
        </div>
    </div>
</div>

<script>
    function tampilkanNamaInstansi(select) {
        const instansiInput = document.getElementById("input_instansi");
        instansiInput.style.display = select.value === "Instansi" ? "block" : "none";
    }
</script>

<style>
    body {
        background-color: #f8f9fa; /* Latar belakang abu-abu terang */
    }
    .form-control {
        border-radius: 20px; /* Sudut membulat pada input */
    }
    .btn-warning {
        border-radius: 20px; /* Sudut membulat pada tombol */
        transition: background-color 0.3s;
    }
    .btn-warning:hover {
        background-color: #ffbb33; /* Warna lebih terang saat hover */
    }
</style>

                    </form>
                </div>
               <!-- Contact Section -->
        <section id="kontak" class="contact section bg-light py-5">
            <div class="container text-center section-title">
                <h2 class="display-4">Kontak </h2>
            </div>
            <div class="container">
            <div class="row gy-4 justify-content-center">
    <div class="col-lg-5">
        <div class="info-wrap shadow-lg p-4 rounded bg-white">
            <h3 class="text-center mb-4">Kontak Kami</h3>
            <div class="info-item d-flex align-items-center mb-4">
                <i class="bi bi-geo-alt flex-shrink-0 fs-3 text-primary"></i>
                <div class="ms-3">
                    <h4>Alamat</h4>
                    <p class="mb-0">Jl. Suliki No. 1, Jati Baru, Padang Timur</p>
                </div>
            </div>
            <div class="info-item d-flex align-items-center mb-4">
                <i class="bi bi-telephone flex-shrink-0 fs-3 text-primary"></i>
                <div class="ms-3">
                    <h4>Telepon</h4>
                    <p class="mb-0"><a href="tel:+6275121907" class="text-decoration-none text-success">0751 21907</a></p>
                </div>
            </div>
            <div class="info-item d-flex align-items-center mb-4">
                <i class="bi bi-envelope flex-shrink-0 fs-3 text-primary"></i>
                <div class="ms-3">
                    <h4>Email Kami</h4>
                    <p class="mb-0"><a href="mailto:smksixpdg@gmail.com" class="text-decoration-none text-success">smksixpdg@gmail.com</a></p>
                </div>
            </div>
            <div class="text-center mt-4">
            </div>
        </div>
    </div>
    <div class="col-lg-6 offset-lg-1">
        <div class="map-wrap">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3989.2846024163714!2d100.36239161475362!3d-0.937177399316345!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2fd4b924c3105a9b%3A0x6b4ee16db9f728e!2sSMK+Negeri+6+Padang!5e0!3m2!1sen!2sid!4v1545725633651" 
                    frameborder="0" 
                    style="border:0; width: 100%; height:380px; border-radius: 10px;" 
                    allowfullscreen="" 
                    loading="lazy"></iframe>
        </div>
    </div>
</div>

<style>
    .info-wrap {
        transition: transform 0.3s, box-shadow 0.3s;
    }
    .info-wrap:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    }
    .info-item {
        border-bottom: 1px solid #e9ecef;
        padding-bottom: 10px;
    }
    .info-item:last-child {
        border-bottom: none;
    }
    .text-success {
        color: #28a745 !important;
    }
</style>
        </div>
    </div>

    <script>
        $(document).ready(function() {
            $('#origin').change(function() {
                if ($(this).val() === 'Instansi') {
                    $('#instansi-container').removeClass('hidden');
                } else {
                    $('#instansi-container').addClass('hidden');
                }
            });
        });
    </script>
</body>
</html>

