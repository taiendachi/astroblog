---
// Halaman Kalkulator Kebutuhan Guru
// Tidak perlu kode di frontmatter
---

<style>
  /* ===== CSS Tools Kebutuhan Guru ===== */
  .guru-calculator {
    max-width: 600px;
    margin: 20px auto;
    background: #f9fafc;
    border-radius: 20px;
    padding: 25px 30px;
    box-shadow: 0 10px 25px rgba(0,0,0,0.1);
    font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
    border: 1px solid #e9ecf0;
  }
  .guru-calculator h3 {
    margin-top: 0;
    margin-bottom: 10px;
    color: #0a2540;
    font-size: 1.6rem;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 3px solid #2b6f9b;
    padding-bottom: 10px;
  }
  .guru-calculator h3 span {
    background: #2b6f9b;
    color: white;
    font-size: 1.2rem;
    padding: 2px 12px;
    border-radius: 40px;
  }
  .guru-calculator p {
    color: #2d3a4b;
    line-height: 1.5;
    margin-bottom: 20px;
  }
  .guru-calculator label {
    font-weight: 500;
    color: #1f3a5f;
    display: block;
    margin-bottom: 6px;
    font-size: 0.95rem;
  }
  .guru-calculator input {
    width: 100%;
    padding: 12px 15px;
    border: 2px solid #dde3ea;
    border-radius: 14px;
    font-size: 1rem;
    transition: 0.2s;
    box-sizing: border-box;
    background: white;
  }
  .guru-calculator input:focus {
    border-color: #2b6f9b;
    outline: none;
    box-shadow: 0 0 0 3px rgba(43,111,155,0.2);
  }
  .guru-calculator .input-group {
    margin-bottom: 20px;
  }
  .guru-calculator .row {
    display: flex;
    gap: 15px;
    flex-wrap: wrap;
  }
  .guru-calculator .row .input-group {
    flex: 1 1 200px;
  }
  .guru-calculator button {
    background: #2b6f9b;
    color: white;
    border: none;
    padding: 14px 20px;
    font-size: 1.1rem;
    font-weight: 600;
    border-radius: 40px;
    width: 100%;
    cursor: pointer;
    transition: 0.2s;
    letter-spacing: 0.3px;
    border-bottom: 4px solid #1d4b6b;
  }
  .guru-calculator button:hover {
    background: #1f5a82;
    transform: translateY(-2px);
    border-bottom-width: 6px;
  }
  .guru-calculator .result-box {
    background: #ffffff;
    border-radius: 18px;
    padding: 20px;
    margin-top: 25px;
    border: 2px dashed #cbd5e1;
  }
  .guru-calculator .result-item {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    padding: 10px 0;
    border-bottom: 1px solid #ecf1f6;
  }
  .guru-calculator .result-item:last-child {
    border-bottom: none;
  }
  .guru-calculator .badge {
    background: #ecf7ff;
    color: #1f5a82;
    padding: 6px 12px;
    border-radius: 30px;
    font-weight: 600;
    font-size: 0.9rem;
  }
  .guru-calculator .status {
    font-weight: 600;
    padding: 8px 12px;
    border-radius: 40px;
    background: #f0f4f9;
  }
  .guru-calculator .status.kurang { background: #ffe0d9; color: #b13e2d; }
  .guru-calculator .status.lebih { background: #ffefc9; color: #8e6100; }
  .guru-calculator .status.cocok { background: #dff0d8; color: #2b6e3f; }
  .guru-calculator hr {
    border: 1px solid #eef2f6;
    margin: 15px 0;
  }
  .guru-calculator .footnote {
    font-size: 0.85rem;
    color: #6b7a8f;
    text-align: center;
    margin-top: 15px;
  }
  @media (max-width: 480px) {
    .guru-calculator { padding: 20px; }
    .guru-calculator h3 { font-size: 1.3rem; }
  }
</style>

<div class="guru-calculator">
  <h3>
    <span>🧑‍🏫</span> Kalkulator Kebutuhan Guru
  </h3>
  <p>Hitung jumlah ideal guru per mata pelajaran berdasarkan rombel dan jam mengajar (rumus: <strong>(Rombel × Jam Mapel) / 24</strong>).</p>

  <div class="input-group">
    <label>📚 Jumlah Rombongan Belajar (Rombel)</label>
    <input type="number" id="rombel" min="1" step="1" value="12" placeholder="Contoh: 12">
  </div>

  <div class="row">
    <div class="input-group">
      <label>⏰ Jam Mapel per Minggu</label>
      <input type="number" id="jamMapel" min="1" step="0.5" value="5" placeholder="Misal: 5 (Matematika)">
    </div>
    <div class="input-group">
      <label>👥 Guru Tersedia (opsional)</label>
      <input type="number" id="guruTersedia" min="0" step="1" value="3" placeholder="Kosongkan jika tidak ingin banding">
    </div>
  </div>

  <button id="hitungBtn">🔍 Hitung Kebutuhan Guru</button>

  <div class="result-box" id="hasilBox">
    <div class="result-item">
      <span>📐 Kebutuhan Ideal (pecahan)</span>
      <span class="badge" id="idealPecahan">0</span>
    </div>
    <div class="result-item">
      <span>🔢 Pembulatan ke Atas</span>
      <span class="badge" id="idealBulat">0 guru</span>
    </div>
    <hr>
    <div class="result-item" id="statusBaris" style="display: none;">
      <span>📊 Status dengan Guru Tersedia</span>
      <span class="status" id="statusText">-</span>
    </div>
    <div class="result-item" id="selisihBaris" style="display: none;">
      <span>📈 Selisih</span>
      <span class="badge" id="selisihValue">0</span>
    </div>
  </div>

  <div class="footnote">
    * Rumus berdasarkan Permendikbud: 24 jam tatap muka minimal per minggu.
  </div>
</div>

<script>
  (function() {
    const rombelInput = document.getElementById('rombel');
    const jamMapelInput = document.getElementById('jamMapel');
    const guruTersediaInput = document.getElementById('guruTersedia');
    const hitungBtn = document.getElementById('hitungBtn');
    
    const idealPecahanSpan = document.getElementById('idealPecahan');
    const idealBulatSpan = document.getElementById('idealBulat');
    const statusBaris = document.getElementById('statusBaris');
    const selisihBaris = document.getElementById('selisihBaris');
    const statusText = document.getElementById('statusText');
    const selisihValue = document.getElementById('selisihValue');

    function hitungKebutuhan() {
      let rombel = parseFloat(rombelInput.value);
      let jamMapel = parseFloat(jamMapelInput.value);
      let guruTersedia = guruTersediaInput.value.trim() === '' ? null : parseFloat(guruTersediaInput.value);

      if (isNaN(rombel) || rombel < 1) rombel = 12;
      if (isNaN(jamMapel) || jamMapel < 0.5) jamMapel = 5;
      
      const totalJam = rombel * jamMapel;
      const kebutuhanPecahan = totalJam / 24;
      const kebutuhanBulat = Math.ceil(kebutuhanPecahan);

      idealPecahanSpan.textContent = kebutuhanPecahan.toFixed(2);
      idealBulatSpan.textContent = kebutuhanBulat + ' guru';

      if (guruTersedia !== null && !isNaN(guruTersedia) && guruTersedia >= 0) {
        const tersedia = Math.floor(guruTersedia);
        const selisih = tersedia - kebutuhanBulat;
        
        let statusClass = '';
        let statusMessage = '';
        if (selisih > 0) {
          statusClass = 'lebih';
          statusMessage = `Kelebihan ${selisih} guru`;
        } else if (selisih < 0) {
          statusClass = 'kurang';
          statusMessage = `Kekurangan ${Math.abs(selisih)} guru`;
        } else {
          statusClass = 'cocok';
          statusMessage = `Ideal (sesuai)`;
        }

        statusText.className = 'status ' + statusClass;
        statusText.textContent = statusMessage;
        selisihValue.textContent = (selisih > 0 ? '+' : '') + selisih;

        statusBaris.style.display = 'flex';
        selisihBaris.style.display = 'flex';
      } else {
        statusBaris.style.display = 'none';
        selisihBaris.style.display = 'none';
      }
    }

    hitungBtn.addEventListener('click', hitungKebutuhan);
    hitungKebutuhan();

    [rombelInput, jamMapelInput, guruTersediaInput].forEach(input => {
      input.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') hitungKebutuhan();
      });
    });
  })();
</script>
