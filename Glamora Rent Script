// Kode promo yang berlaku: huruf besar semua -> persentase diskon
var DAFTAR_PROMO = {
  "GLAMORA": 15
};

function formatRupiah(angka) {
  return "Rp" + Math.round(angka).toLocaleString("id-ID");
}

function hitungTotal() {
  var harga = Number(document.getElementById("paket").value);
  var hari = parseInt(document.getElementById("hari").value, 10);
  var kode = document.getElementById("promo").value.trim().toUpperCase();
  var hasil = document.getElementById("hasil");

  if (isNaN(hari) || hari < 1) {
    hasil.innerHTML = '<p class="pesan salah">Jumlah hari sewa minimal 1.</p>';
    return;
  }

  var subtotal = harga * hari;
  var persen = 0;
  var pesan = "";

  if (kode !== "") {
    if (DAFTAR_PROMO[kode]) {
      persen = DAFTAR_PROMO[kode];
      pesan = '<p class="pesan ok">Kode ' + kode + " berhasil dipakai, diskon " + persen + "%.</p>";
    } else {
      pesan = '<p class="pesan salah">Kode promo tidak dikenal, total dihitung tanpa diskon.</p>';
    }
  }

  var diskon = subtotal * persen / 100;
  var total = subtotal - diskon;

  hasil.innerHTML =
    "<table>" +
    "<tr><td>Harga paket &times; " + hari + " hari</td><td>" + formatRupiah(subtotal) + "</td></tr>" +
    '<tr class="diskon"><td>Diskon promo</td><td>-' + formatRupiah(diskon) + "</td></tr>" +
    '<tr class="total"><td>Total bayar</td><td>' + formatRupiah(total) + "</td></tr>" +
    "</table>" + pesan;
}

document.getElementById("tombol-hitung").addEventListener("click", hitungTotal);
