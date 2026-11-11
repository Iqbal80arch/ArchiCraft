<!DOCTYPE html>
<html lang="id">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>ArchiCraft — Concept Visualizer</title>
    <meta
      name="description"
      content="Prototipe visualisasi konsep arsitektur untuk arsitek, desain rumah, dan presentasi proyek."
    />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header class="topbar">
      <div class="container nav">
        <div class="brand">
          <div class="brand-mark">A</div>
          <span>ArchiCraft</span>
        </div>
        <nav class="nav-links">
          <a href="#features">Fitur</a>
          <a href="#workflow">Alur</a>
          <a href="#pricing">RAB</a>
        </nav>
        <button class="nav-btn">Coba Demo</button>
      </div>
    </header>

    <main>
      <section class="hero">
        <div class="container hero-grid">
          <div class="hero-copy">
            <div class="eyebrow">AI VISUALISASI KONSEP ARSITEKTUR</div>
            <h1>Transformasi sketsa, foto, dan denah menjadi konsep arsitektur yang hidup.</h1>
            <p>
              ArchiCraft membantu arsitek dan desainer mengeksplorasi variasi ruang,
              material, pencahayaan, dan suasana dalam hitungan menit.
            </p>

            <div class="hero-actions">
              <button class="primary">Mulai Eksplorasi</button>
              <button class="secondary">Lihat Demo</button>
            </div>

            <div class="mini-stats">
              <div>
                <strong>24x</strong>
                <span>Lebih cepat</span>
              </div>
              <div>
                <strong>3 varian</strong>
                <span>Konsep per projek</span>
              </div>
              <div>
                <strong>1 klik</strong>
                <span>Bagikan presentasi</span>
              </div>
            </div>
          </div>

          <div class="hero-panel">
            <div class="panel-window">
              <div class="panel-header">
                <span class="dot red"></span>
                <span class="dot yellow"></span>
                <span class="dot green"></span>
              </div>

              <div class="render-preview">
                <div class="render-image" id="renderImage">
                  <div class="glass">
                    <span>Concept Preview</span>
                    <strong id="sceneName">Modern Tropical Villa</strong>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="controls-section" id="features">
        <div class="container">
          <div class="section-heading">
            <div class="eyebrow">PILIH KONSEP</div>
            <h2>Kelola gaya, pencahayaan, dan suasana proyek Anda</h2>
          </div>

          <div class="workspace">
            <aside class="control-panel">
              <div class="panel-block">
                <label for="projectType">Jenis proyek</label>
                <select id="projectType">
                  <option value="villa">Villa</option>
                  <option value="interior">Interior Rumah</option>
                  <option value="cafe">Cafe & Resto</option>
                  <option value="office">Office</option>
                </select>
              </div>

              <div class="panel-block">
                <label>Style</label>
                <div class="option-grid">
                  <button class="option active" data-style="modern">Modern</button>
                  <button class="option" data-style="minimalis">Minimalis</button>
                  <button class="option" data-style="tropis">Tropis</button>
                  <button class="option" data-style="industrial">Industrial</button>
                  <button class="option" data-style="classic">Classic</button>
                  <button class="option" data-style="japandi">Japandi</button>
                </div>
              </div>

              <div class="panel-block">
                <label>Pencahayaan</label>
                <div class="option-grid">
                  <button class="option active" data-light="pagi">Pagi</button>
                  <button class="option" data-light="siang">Siang</button>
                  <button class="option" data-light="senja">Senja</button>
                  <button class="option" data-light="malam">Malam</button>
                </div>
              </div>

              <div class="panel-block">
                <label>Level visual</label>
                <div class="option-grid">
                  <button class="option active" data-visual="sketsa">Sketsa</button>
                  <button class="option" data-visual="ilustrasi">Ilustrasi</button>
                  <button class="option" data-visual="realistis">Realistis</button>
                </div>
              </div>

              <div class="panel-block">
                <label for="upload">Unggah referensi</label>
                <input id="upload" type="file" accept="image/*" />
              </div>

              <button id="generateBtn" class="primary full">Generate Concept</button>
            </aside>

            <div class="result-panel">
              <div class="result-header">
                <div>
                  <span class="eyebrow small">PREVIEW</span>
                  <h3 id="captionTitle">Concept Visual</h3>
                </div>
                <div class="tag" id="tagLabel">Style: Modern</div>
              </div>

              <div class="result-art">
                <div id="uploadedPreview" class="uploaded-layer"></div>
                <div class="scene-scroller">
                  <div class="scene-card active">
                    <div class="scene-thumb scene-1"></div>
                    <div class="scene-info">
                      <strong>Alternatif A</strong>
                      <span>Modern Tropical</span>
                    </div>
                  </div>
                  <div class="scene-card">
                    <div class="scene-thumb scene-2"></div>
                    <div class="scene-info">
                      <strong>Alternatif B</strong>
                      <span>Warm Minimalist</span>
                    </div>
                  </div>
                  <div class="scene-card">
                    <div class="scene-thumb scene-3"></div>
                    <div class="scene-info">
                      <strong>Alternatif C</strong>
                      <span>Sunset Lounge</span>
                    </div>
                  </div>
                </div>
              </div>

              <div class="metrics">
                <div class="metric">
                  <span>Material</span>
                  <strong id="materialText">Wood + Concrete</strong>
                </div>
                <div class="metric">
                  <span>Suasana</span>
                  <strong id="moodText">Hangat & Kuat</strong>
                </div>
                <div class="metric">
                  <span>Estimasi</span>
                  <strong id="budgetText">Rp 320 jt</strong>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="feature-strip" id="workflow">
        <div class="container">
          <div class="section-heading">
            <div class="eyebrow">ALUR KERJA</div>
            <h2>Dari ide ke presentasi konsep yang lebih cepat</h2>
          </div>

          <div class="feature-grid">
            <div class="feature-box">
              <div class="icon">01</div>
              <h3>Unggah referensi</h3>
              <p>Foto, sketsa, denah, atau gambar kerja yang Anda miliki.</p>
            </div>
            <div class="feature-box">
              <div class="icon">02</div>
              <h3>Atur konsep</h3>
              <p>Style, material, pencahayaan, dan tingkat visual sesuai kebutuhan.</p>
            </div>
            <div class="feature-box">
              <div class="icon">03</div>
              <h3>Bandingkan varian</h3>
              <p>Tinjau beberapa opsi desain dan pilih arah yang paling cocok.</p>
            </div>
            <div class="feature-box">
              <div class="icon">04</div>
              <h3>Presentasi</h3>
              <p>Bagikan hasil untuk klien dan tim dalam format siap dipakai.</p>
            </div>
          </div>
        </div>
      </section>

      <section class="budget-section" id="pricing">
        <div class="container budget-wrap">
          <div class="budget-copy">
            <div class="eyebrow">RAB AWAL</div>
            <h2>Estimasi biaya dapat dibuat otomatis dari konsep yang dipilih.</h2>
            <p>
              Fitur tambahan ini membantu arsitek membuat gambaran anggaran awal
              berdasarkan luas ruangan, material, dan kebutuhan proyek.
            </p>
          </div>

          <div class="budget-card">
            <div class="budget-head">
              <span>Project Estimate</span>
              <strong>Concept House</strong>
            </div>
            <ul>
              <li><span>Struktur</span><strong>Rp 150 jt</strong></li>
              <li><span>Finishing</span><strong>Rp 90 jt</strong></li>
              <li><span>Furniture</span><strong>Rp 55 jt</strong></li>
              <li><span>Lighting</span><strong>Rp 25 jt</strong></li>
            </ul>
            <div class="total">
              <span>Total estimasi</span>
              <strong id="totalBudget">Rp 320 jt</strong>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="footer">
      <div class="container footer-inner">
        <div>© 2026 ArchiCraft</div>
        <div>Concept-first architectural visualizer</div>
      </div>
    </footer>

    <script src="script.js"></script>
  </body>
</html>