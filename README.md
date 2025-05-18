# Diskusi5
**Jihan Puspita**
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulir Identitas Diri - Lilac</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            margin: 0;
            padding: 0;
            background-color: #f9f5ff;
        }
        
        .container {
            display: grid;
            grid-template-areas:
                "header header"
                "sidebar main"
                "footer footer";
            grid-template-columns: 220px 1fr;
            grid-template-rows: 90px 1fr 80px;
            min-height: 100vh;
        }
        
        header {
            grid-area: header;
            background-color: #8a6bb8;
            color: white;
            display: flex;
            align-items: center;
            padding: 0 30px;
            box-shadow: 0 2px 15px rgba(138, 107, 184, 0.3);
        }
        
        .sidebar {
            grid-area: sidebar;
            background-color: #f3edfc;
            padding: 25px 15px;
            box-shadow: 2px 0 10px rgba(138, 107, 184, 0.1);
        }
        
        .nav-menu {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        
        .nav-item {
            margin-bottom: 12px;
            transition: all 0.3s ease;
        }
        
        .nav-item a {
            display: flex;
            align-items: center;
            text-decoration: none;
            color: #5d4a7a;
            padding: 12px 15px;
            border-radius: 8px;
            transition: all 0.3s ease;
        }
        
        .nav-item a:hover {
            background-color: #e2d5f7;
            color: #6a4b8c;
            transform: translateX(5px);
        }
        
        .nav-item i {
            margin-right: 12px;
            font-size: 20px;
            width: 24px;
            text-align: center;
            color: #8a6bb8;
        }
        
        .nav-item.active a {
            background-color: #d9c6f5;
            color: #6a4b8c;
            font-weight: 600;
            box-shadow: 3px 3px 8px rgba(138, 107, 184, 0.1);
        }
        
        main {
            grid-area: main;
            padding: 35px;
            background-color: #f9f5ff;
        }
        
        .form-container {
            background-color: white;
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 4px 20px rgba(138, 107, 184, 0.1);
            border: 1px solid #e8ddf7;
        }
        
        h2 {
            color: #6a4b8c;
            margin-top: 0;
            margin-bottom: 25px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f0e5ff;
            display: flex;
            align-items: center;
        }
        
        h2 i {
            margin-right: 12px;
            color: #8a6bb8;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #5d4a7a;
            font-size: 15px;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #d8c7f0;
            border-radius: 8px;
            font-size: 15px;
            background-color: #fcfaff;
            transition: all 0.3s ease;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #b399d6;
            box-shadow: 0 0 0 3px rgba(138, 107, 184, 0.2);
            background-color: white;
        }
        
        .form-row {
            display: flex;
            gap: 25px;
            margin-bottom: 20px;
        }
        
        .form-row .form-group {
            flex: 1;
        }
        
        footer {
            grid-area: footer;
            background-color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 35px;
            box-shadow: 0 -2px 10px rgba(138, 107, 184, 0.1);
            border-top: 1px solid #e8ddf7;
        }
        
        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 15px;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            transition: all 0.3s ease;
        }
        
        .btn i {
            margin-right: 8px;
        }
        
        .btn-primary {
            background-color: #8a6bb8;
            color: white;
            box-shadow: 0 3px 10px rgba(138, 107, 184, 0.3);
        }
        
        .btn-primary:hover {
            background-color: #7a5ba8;
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background-color: #f3edfc;
            color: #6a4b8c;
            border: 1px solid #d8c7f0;
        }
        
        .btn-secondary:hover {
            background-color: #e2d5f7;
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .tab-content.active {
            display: block;
        }
        
        .progress-bar {
            display: flex;
            align-items: center;
        }
        
        .progress-steps {
            display: flex;
            margin-right: 20px;
        }
        
        .step {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: #d8c7f0;
            margin-right: 8px;
            transition: all 0.3s ease;
        }
        
        .step.active {
            background-color: #8a6bb8;
            transform: scale(1.2);
        }
        
        @media (max-width: 768px) {
            .container {
                grid-template-areas:
                    "header"
                    "main"
                    "footer";
                grid-template-columns: 1fr;
                grid-template-rows: 80px 1fr 80px;
            }
            
            .sidebar {
                display: none;
            }
            
            main {
                padding: 20px;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
            
            footer {
                flex-direction: column-reverse;
                padding: 15px;
                gap: 10px;
            }
            
            .progress-bar {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-id-card"></i> Formulir Identitas Diri</h1>
        </header>
        
        <aside class="sidebar">
            <ul class="nav-menu">
                <li class="nav-item active" data-tab="personal">
                    <a href="#">
                        <i class="fas fa-user"></i>
                        <span>Data Pribadi</span>
                    </a>
                </li>
                <li class="nav-item" data-tab="address">
                    <a href="#">
                        <i class="fas fa-home"></i>
                        <span>Alamat</span>
                    </a>
                </li>
                <li class="nav-item" data-tab="education">
                    <a href="#">
                        <i class="fas fa-graduation-cap"></i>
                        <span>Pendidikan</span>
                    </a>
                </li>
                <li class="nav-item" data-tab="family">
                    <a href="#">
                        <i class="fas fa-users"></i>
                        <span>Data Keluarga</span>
                    </a>
                </li>
            </ul>
        </aside>
        
        <main>
            <div class="form-container">
                <!-- Tab Data Pribadi -->
                <div id="personal" class="tab-content active">
                    <h2><i class="fas fa-user"></i> Data Pribadi</h2>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="nama_lengkap">Nama Lengkap</label>
                            <input type="text" id="nama_lengkap" placeholder="Masukkan nama lengkap">
                        </div>
                        <div class="form-group">
                            <label for="nama_panggilan">Nama Panggilan</label>
                            <input type="text" id="nama_panggilan" placeholder="Masukkan nama panggilan">
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="tempat_lahir">Tempat Lahir</label>
                            <input type="text" id="tempat_lahir" placeholder="Masukkan tempat lahir">
                        </div>
                        <div class="form-group">
                            <label for="tanggal_lahir">Tanggal Lahir</label>
                            <input type="date" id="tanggal_lahir">
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="jenis_kelamin">Jenis Kelamin</label>
                            <select id="jenis_kelamin">
                                <option value="">Pilih Jenis Kelamin</option>
                                <option value="L">Laki-laki</option>
                                <option value="P">Perempuan</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="golongan_darah">Golongan Darah</label>
                            <select id="golongan_darah">
                                <option value="">Pilih Golongan Darah</option>
                                <option value="A">A</option>
                                <option value="B">B</option>
                                <option value="AB">AB</option>
                                <option value="O">O</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <!-- Tab Alamat -->
                <div id="address" class="tab-content">
                    <h2><i class="fas fa-home"></i> Alamat</h2>
                    
                    <div class="form-group">
                        <label for="alamat">Alamat Lengkap</label>
                        <textarea id="alamat" rows="3" placeholder="Masukkan alamat lengkap"></textarea>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="provinsi">Provinsi</label>
                            <select id="provinsi">
                                <option value="">Pilih Provinsi</option>
                                <option value="Jabar">Jawa Barat</option>
                                <option value="Jateng">Jawa Tengah</option>
                                <option value="Jatim">Jawa Timur</option>
                                <option value="Jakarta">DKI Jakarta</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="kota">Kota/Kabupaten</label>
                            <select id="kota">
                                <option value="">Pilih Kota/Kabupaten</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="kecamatan">Kecamatan</label>
                            <select id="kecamatan">
                                <option value="">Pilih Kecamatan</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="kode_pos">Kode Pos</label>
                            <input type="text" id="kode_pos" placeholder="Masukkan kode pos">
                        </div>
                    </div>
                </div>
                
                <!-- Tab Pendidikan -->
                <div id="education" class="tab-content">
                    <h2><i class="fas fa-graduation-cap"></i> Pendidikan</h2>
                    
                    <div class="form-group">
                        <label for="pendidikan_terakhir">Pendidikan Terakhir</label>
                        <select id="pendidikan_terakhir">
                            <option value="">Pilih Pendidikan Terakhir</option>
                            <option value="SD">SD/Sederajat</option>
                            <option value="SMP">SMP/Sederajat</option>
                            <option value="SMA">SMA/Sederajat</option>
                            <option value="D3">Diploma (D3)</option>
                            <option value="S1">Sarjana (S1)</option>
                            <option value="S2">Magister (S2)</option>
                            <option value="S3">Doktor (S3)</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="nama_sekolah">Nama Sekolah/Universitas</label>
                        <input type="text" id="nama_sekolah" placeholder="Masukkan nama sekolah/universitas">
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="tahun_masuk">Tahun Masuk</label>
                            <input type="number" id="tahun_masuk" placeholder="Tahun masuk">
                        </div>
                        <div class="form-group">
                            <label for="tahun_lulus">Tahun Lulus</label>
                            <input type="number" id="tahun_lulus" placeholder="Tahun lulus">
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="jurusan">Jurusan</label>
                        <input type="text" id="jurusan" placeholder="Masukkan jurusan (jika ada)">
                    </div>
                </div>
                
                <!-- Tab Data Keluarga -->
                <div id="family" class="tab-content">
                    <h2><i class="fas fa-users"></i> Data Keluarga</h2>
                    
                    <div class="form-group">
                        <label for="status_perkawinan">Status Perkawinan</label>
                        <select id="status_perkawinan">
                            <option value="">Pilih Status Perkawinan</option>
                            <option value="belum_kawin">Belum Kawin</option>
                            <option value="kawin">Kawin</option>
                            <option value="cerai_hidup">Cerai Hidup</option>
                            <option value="cerai_mati">Cerai Mati</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="nama_pasangan">Nama Pasangan</label>
                        <input type="text" id="nama_pasangan" placeholder="Masukkan nama pasangan (jika ada)">
                    </div>
                    
                    <div class="form-group">
                        <label for="jumlah_anak">Jumlah Anak</label>
                        <input type="number" id="jumlah_anak" placeholder="Masukkan jumlah anak" min="0">
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="nama_ayah">Nama Ayah</label>
                            <input type="text" id="nama_ayah" placeholder="Masukkan nama ayah">
                        </div>
                        <div class="form-group">
                            <label for="nama_ibu">Nama Ibu</label>
                            <input type="text" id="nama_ibu" placeholder="Masukkan nama ibu">
                        </div>
                    </div>
                </div>
            </div>
        </main>
        
        <footer>
            <div class="progress-bar">
                <div class="progress-steps">
                    <div class="step active" data-step="1"></div>
                    <div class="step" data-step="2"></div>
                    <div class="step" data-step="3"></div>
                    <div class="step" data-step="4"></div>
                </div>
                <span id="step-indicator">Langkah 1 dari 4</span>
            </div>
            
            <div class="button-group">
                <button class="btn btn-secondary" id="btn-prev">
                    <i class="fas fa-arrow-left"></i> Sebelumnya
                </button>
                <button class="btn btn-secondary" id="btn-next">
                    Selanjutnya <i class="fas fa-arrow-right"></i>
                </button>
                <button class="btn btn-primary" id="btn-save">
                    <i class="fas fa-save"></i> Simpan Data
                </button>
            </div>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const navItems = document.querySelectorAll('.nav-item');
            const tabContents = document.querySelectorAll('.tab-content');
            const steps = document.querySelectorAll('.step');
            const stepIndicator = document.getElementById('step-indicator');
            
            // Urutan tab
            const tabs = ['personal', 'address', 'education', 'family'];
            let currentTabIndex = 0;
            
            // Fungsi untuk mengupdate tampilan tab
            function updateTab(index) {
                // Update menu navigasi
                navItems.forEach((item, i) => {
                    if (i === index) {
                        item.classList.add('active');
                    } else {
                        item.classList.remove('active');
                    }
                });
                
                // Update konten tab
                tabContents.forEach((content, i) => {
                    if (i === index) {
                        content.classList.add('active');
                    } else {
                        content.classList.remove('active');
                    }
                });
                
                // Update progress steps
                steps.forEach((step, i) => {
                    if (i <= index) {
                        step.classList.add('active');
                    } else {
                        step.classList.remove('active');
                    }
                });
                
                // Update step indicator
                stepIndicator.textContent = `Langkah ${index + 1} dari ${tabs.length}`;
                
                // Update tombol navigasi
                updateButtonVisibility();
            }
            
            // Fungsi untuk update visibilitas tombol navigasi
            function updateButtonVisibility() {
                const btnPrev = document.getElementById('btn-prev');
                const btnNext = document.getElementById('btn-next');
                
                btnPrev.style.display = currentTabIndex === 0 ? 'none' : 'inline-flex';
                btnNext.style.display = currentTabIndex === tabs.length - 1 ? 'none' : 'inline-flex';
            }
            
            // Event listener untuk menu navigasi
            navItems.forEach((item, index) => {
                item.addEventListener('click', function() {
                    currentTabIndex = index;
                    updateTab(currentTabIndex);
                });
            });
            
            // Event listener untuk tombol navigasi
            document.getElementById('btn-next').addEventListener('click', function() {
                if (currentTabIndex < tabs.length - 1) {
                    currentTabIndex++;
                    updateTab(currentTabIndex);
                }
            });
            
            document.getElementById('btn-prev').addEventListener('click', function() {
                if (currentTabIndex > 0) {
                    currentTabIndex--;
                    updateTab(currentTabIndex);
                }
            });
            
            // Event listener untuk tombol simpan
            document.getElementById('btn-save').addEventListener('click', function() {
                if (validateForm()) {
                    // Kumpulkan semua data form
                    const formData = {
                        personal: {
                            namaLengkap: document.getElementById('nama_lengkap').value,
                            namaPanggilan: document.getElementById('nama_panggilan').value,
                            tempatLahir: document.getElementById('tempat_lahir').value,
                            tanggalLahir: document.getElementById('tanggal_lahir').value,
                            jenisKelamin: document.getElementById('jenis_kelamin').value,
                            golonganDarah: document.getElementById('golongan_darah').value
                        },
                        address: {
                            alamat: document.getElementById('alamat').value,
                            provinsi: document.getElementById('provinsi').value,
                            kota: document.getElementById('kota').value,
                            kecamatan: document.getElementById('kecamatan').value,
                            kodePos: document.getElementById('kode_pos').value
                        },
                        education: {
                            pendidikanTerakhir: document.getElementById('pendidikan_terakhir').value,
                            namaSekolah: document.getElementById('nama_sekolah').value,
                            tahunMasuk: document.getElementById('tahun_masuk').value,
                            tahunLulus: document.getElementById('tahun_lulus').value,
                            jurusan: document.getElementById('jurusan').value
                        },
                        family: {
                            statusPerkawinan: document.getElementById('status_perkawinan').value,
                            namaPasangan: document.getElementById('nama_pasangan').value,
                            jumlahAnak: document.getElementById('jumlah_anak').value,
                            namaAyah: document.getElementById('nama_ayah').value,
                            namaIbu: document.getElementById('nama_ibu').value
                        }
                    };
                    
                    console.log('Data yang akan disimpan:', formData);
                    alert('Data berhasil disimpan!');
                    
                    // Di sini bisa ditambahkan kode untuk mengirim data ke server
                    // Contoh: fetch('/api/save', { method: 'POST', body: JSON.stringify(formData) })
                }
            });
            
            // Fungsi validasi form sederhana
            function validateForm() {
                let isValid = true;
                const currentTab = tabs[currentTabIndex];
                
                if (currentTab === 'personal') {
                    if (!document.getElementById('nama_lengkap').value) {
                        alert('Nama lengkap harus diisi');
                        isValid = false;
                    }
                }
                
                if (currentTab === 'address') {
                    if (!document.getElementById('alamat').value) {
                        alert('Alamat lengkap harus diisi');
                        isValid = false;
                    }
                }
                
                if (currentTab === 'education') {
                    if (!document.getElementById('pendidikan_terakhir').value) {
                        alert('Pendidikan terakhir harus dipilih');
                        isValid = false;
                    }
                }
                
                if (currentTab === 'family') {
                    const status = document.getElementById('status_perkawinan').value;
                    if (status === 'kawin' && !document.getElementById('nama_pasangan').value) {
                        alert('Nama pasangan harus diisi untuk status kawin');
                        isValid = false;
                    }
                }
                
                return isValid;
            }
            
            // Inisialisasi data kota berdasarkan provinsi
            document.getElementById('provinsi').addEventListener('change', function() {
                const kotaSelect = document.getElementById('kota');
                kotaSelect.innerHTML = '<option value="">Pilih Kota/Kabupaten</option>';
                
                // Data dummy kota (bisa diganti dengan data sebenarnya)
                const kotaData = {
                    'Jabar': ['Bandung', 'Bogor', 'Bekasi', 'Depok', 'Cimahi'],
                    'Jateng': ['Semarang', 'Solo', 'Magelang', 'Pekalongan', 'Tegal'],
                    'Jatim': ['Surabaya', 'Malang', 'Madiun', 'Kediri', 'Blitar'],
                    'Jakarta': ['Jakarta Pusat', 'Jakarta Selatan', 'Jakarta Barat', 'Jakarta Timur', 'Jakarta Utara']
                };
                
                const selectedProvinsi = this.value;
                if (selectedProvinsi && kotaData[selectedProvinsi]) {
                    kotaData[selectedProvinsi].forEach(kota => {
                        const option = document.createElement('option');
                        option.value = kota;
                        option.textContent = kota;
                        kotaSelect.appendChild(option);
                    });
                }
            });
            
            // Inisialisasi data kecamatan berdasarkan kota
            document.getElementById('kota').addEventListener('change', function() {
                const kecamatanSelect = document.getElementById('kecamatan');
                kecamatanSelect.innerHTML = '<option value="">Pilih Kecamatan</option>';
                
                // Data dummy kecamatan (bisa diganti dengan data sebenarnya)
                const kecamatanData = {
                    'Bandung': ['Bandung Kulon', 'Bandung Wetan', 'Buahbatu', 'Cibeunying'],
                    'Jakarta Pusat': ['Gambir', 'Sawah Besar', 'Menteng', 'Tanah Abang']
                };
                
                const selectedKota = this.value;
                if (selectedKota && kecamatanData[selectedKota]) {
                    kecamatanData[selectedKota].forEach(kec => {
                        const option = document.createElement('option');
                        option.value = kec;
                        option.textContent = kec;
                        kecamatanSelect.appendChild(option);
                    });
                }
            });
            
            // Inisialisasi tampilan awal
            updateTab(0);
        });
    </script>
</body>
</html>
