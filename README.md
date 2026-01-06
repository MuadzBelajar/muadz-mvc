<h4>1. PENGERTIAN MVC</h4>
<p>
MVC (Model View Controller) adalah pola arsitektur dalam pengembangan aplikasi yang
memisahkan kode program menjadi tiga bagian utama: Model, View, dan Controller.
Tujuannya agar kode lebih rapi, terstruktur, mudah dikembangkan, dan mudah dirawat.
</p>

<h4>2. MODEL</h4>
<p>
Model adalah bagian yang bertugas mengelola data dan berinteraksi langsung dengan
database. Model tidak mengatur tampilan, melainkan fokus pada pengambilan,
penyimpanan, pengubahan, dan penghapusan data.
</p>
<p><b>Contoh tugas Model:</b></p>
<ul>
    <li>Mengambil data siswa dari database</li>
    <li>Menyimpan data siswa baru</li>
    <li>Mengupdate dan menghapus data siswa</li>
</ul>

<pre><code>
&lt;?php
function getSiswa() {
    global $conn;
    return mysqli_query($conn, "SELECT * FROM siswa");
}
?&gt;
</code></pre>

<h4>3. VIEW</h4>
<p>
View adalah bagian yang bertugas menampilkan data kepada pengguna dalam bentuk
tampilan (GUI). View biasanya berisi HTML, CSS, dan sedikit PHP, tanpa logika database.
</p>
<p><b>Contoh tugas View:</b></p>
<ul>
    <li>Menampilkan tabel data siswa</li>
    <li>Menampilkan form tambah atau edit data</li>
    <li>Menampilkan hasil dari Model</li>
</ul>

<pre><code>
&lt;table&gt;
&lt;?php foreach($siswa as $row): ?&gt;
&lt;tr&gt;
    &lt;td&gt;&lt;?= $row['nama']; ?&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;?php endforeach; ?&gt;
&lt;/table&gt;
</code></pre>

<h4>4. CONTROLLER</h4>
<p>
Controller adalah penghubung antara Model dan View. Controller menerima input dari
pengguna, memanggil Model untuk memproses data, lalu mengirim hasilnya ke View.
</p>
<p><b>Contoh tugas Controller:</b></p>
<ul>
    <li>Menerima data dari form</li>
    <li>Memanggil fungsi pada Model</li>
    <li>Menentukan tampilan (View) yang ditampilkan</li>
</ul>

<pre><code>
&lt;?php
$siswa = getSiswa();
include 'view/siswa.php';
?&gt;
</code></pre>

<h4>5. ALUR KERJA MVC</h4>
<p>
Alur kerja MVC dimulai saat pengguna meminta data melalui tampilan (View).
Permintaan tersebut diterima oleh Controller, lalu Controller meminta data ke Model.
Setelah data diproses oleh Model, hasilnya dikirim kembali ke Controller untuk
ditampilkan oleh View.
</p> 
<img width="592" height="366" alt="image" src="https://github.com/user-attachments/assets/f2104682-87a3-4398-8aef-d7fd3dc2adbb" />


<h4>6. MANFAAT MVC</h4>
<ul>
    <li>Pengembangan aplikasi lebih cepat dan efisien</li>
    <li>Kode lebih rapi dan terstruktur</li>
    <li>Mudah dilakukan testing</li>
    <li>Bug atau error lebih cepat diperbaiki</li>
    <li>Mudah dalam pemeliharaan aplikasi</li>
</ul>

<h4>7. KESIMPULAN</h4>
<p>
MVC adalah metode pengembangan aplikasi dengan memisahkan kode menjadi Model,
View, dan Controller. Dengan pemisahan ini, aplikasi menjadi lebih terstruktur,
mudah dikembangkan, dan mudah dirawat.
</p>
