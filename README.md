<?php
$url = "https://jagoanpedia.com/api/whatsapp-text";
$data = [
    "key" => "ba8c306f-dace-416a-a5a7-e980debca2b1",
    "to" => "6287748842242",
    "text" => "order"
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    "Content-Type: application/json"
]);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
$response = curl_exec($ch);
curl_close($ch);

echo "Response: " . $response;
?>