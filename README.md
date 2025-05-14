```
$url = "https://jagoanpedia.com/api/whatsapp-text?key=ba8c306f-dace-416a-a5a7-e980debca2b1&to=6287748842242&text=Hello";
$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
$httpcode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);

if ($httpcode == 200) {
    echo "Pesan terkirim!";
} else {
    echo "Gagal mengirim pesan. Kode HTTP: $httpcode";
}
```