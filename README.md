<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Skor SNBT</title>
    <script>
        function hitungSkor() {
            const maxSoal = {
                penalaranUmum: 30,
                pengetahuanUmum: 20,
                pemahamanBacaan: 20,
                pengetahuanKuantitatif: 15,
                literasiIndonesia: 30,
                literasiInggris: 20,
                penalaranMatematika: 20
            };

            let jawabanBenar = [];

            function validasiInput(value, max) {
                if (value >= 0 && value <= max) {
                    return true;
                } else {
                    alert(`Jumlah jawaban benar tidak boleh lebih dari ${max} atau kurang dari 0.`);
                    return false;
                }
            }

            const penalaranUmum = parseInt(prompt("Masukkan perkiraan jawaban benar pada Penalaran Umum (30 Soal):"));
            if (validasiInput(penalaranUmum, maxSoal.penalaranUmum)) jawabanBenar.push(penalaranUmum);

            const pengetahuanUmum = parseInt(prompt("Masukkan perkiraan jawaban benar pada Pengetahuan dan Pemahaman Umum (20 Soal):"));
            if (validasiInput(pengetahuanUmum, maxSoal.pengetahuanUmum)) jawabanBenar.push(pengetahuanUmum);

            const pemahamanBacaan = parseInt(prompt("Masukkan perkiraan jawaban benar pada Pemahaman Bacaan dan Menulis (20 Soal):"));
            if (validasiInput(pemahamanBacaan, maxSoal.pemahamanBacaan)) jawabanBenar.push(pemahamanBacaan);

            const pengetahuanKuantitatif = parseInt(prompt("Masukkan perkiraan jawaban benar pada Pengetahuan Kuantitatif (15 Soal):"));
            if (validasiInput(pengetahuanKuantitatif, maxSoal.pengetahuanKuantitatif)) jawabanBenar.push(pengetahuanKuantitatif);

            const literasiIndonesia = parseInt(prompt("Masukkan perkiraan jawaban benar pada Literasi Bahasa Indonesia (30 Soal):"));
            if (validasiInput(literasiIndonesia, maxSoal.literasiIndonesia)) jawabanBenar.push(literasiIndonesia);

            const literasiInggris = parseInt(prompt("Masukkan perkiraan jawaban benar pada Literasi Bahasa Inggris (20 Soal):"));
            if (validasiInput(literasiInggris, maxSoal.literasiInggris)) jawabanBenar.push(literasiInggris);

            const penalaranMatematika = parseInt(prompt("Masukkan perkiraan jawaban benar pada Penalaran Matematika (20 Soal):"));
            if (validasiInput(penalaranMatematika, maxSoal.penalaranMatematika)) jawabanBenar.push(penalaranMatematika);

            if (jawabanBenar.length === 7) {
                const jumlahBenar = jawabanBenar.reduce((a, b) => a + b, 0);
                const jumlahSalah = 155 - jumlahBenar;
                const nilaiTotal = jumlahBenar * 6.58;

                let hasil = `Jawaban Benar: ${jumlahBenar}\n`;
                hasil += `Jawaban Salah: ${jumlahSalah}\n`;
                hasil += `Perkiraan Nilai Anda: ${nilaiTotal.toFixed(2)}\n`;

                if (nilaiTotal >= 670) {
                    hasil += "Anda memiliki peluang untuk lulus PTN Top 3";
                } else {
                    hasil += "Lebih banyak belajar lagi";
                }

                alert(hasil);
            } else {
                alert("Proses dihentikan karena ada input yang tidak valid.");
            }
        }
    </script>
</head>
<body>
    <h1>Program Perkiraan Skor Tes Masuk Universitas</h1>
    <button onclick="hitungSkor()">Mulai Program</button>
</body>
</html>

