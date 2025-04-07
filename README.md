
<html>
<head>
  <title>Cek Stok</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
    }

    #stok-table {
      border-collapse: collapse;
      width: 50%;
      margin: 40px auto;
      background-color: #c6efce;
      border: 1px solid #3e8e41;
    }

    #stok-table th, #stok-table td {
      border: 1px solid #3e8e41;
      padding: 10px;
      text-align: left;
    }

    #stok-table th {
      background-color: #3e8e41;
      color: #ffffff;
    }

    #stok-table td {
      background-color: #c6efce;
    }

    #stok-table tr:nth-child(even) {
      background-color: #b3dfb5;
    }

    #stok-table tr:hover {
      background-color: #a1d9a3;
    }
  </style>
</head>
<body>
  <table id="stok-table">
    <thead>
      <tr>
        <th>Nama</th>
        <th>Stok</th>
      </tr>
    </thead>
    <tbody id="stok-body">
    </tbody>
  </table>

  <script>
    const apiUrl = 'https://sheetdb.io/api/v1/ugr3n28l5w7p9';
    const stokTable = document.getElementById('stok-table');
    const stokBody = document.getElementById('stok-body');

    fetch(apiUrl)
      .then(response => response.json())
      .then(data => {
        data.forEach(item => {
          const row = document.createElement('tr');
          const namaCell = document.createElement('td');
          const stokCell = document.createElement('td');

          namaCell.textContent = item.nama;
          stokCell.textContent = item.stok;

          row.appendChild(namaCell);
          row.appendChild(stokCell);

          stokBody.appendChild(row);
        });
      })
      .catch(error => {
        console.error(error);
      });
  </script>
</body>
</html>

<html>
<head>
  <title>Catatan</title>
  <style>
    .container {
      display: flex;
      justify-content: space-between;
    }
  </style>
</head>
<body>
  <div class="container">
    <div style="text-align: left;">
      <h2>Akrab Jumbo</h2>
      <p>Area 1: 45 GB</p>
      <p>Area 2: 50 GB</p>
      <p>Area 3: 63 GB</p>
      <p>Area 4: 103 GB</p>
      <p>Rp 65,000</p>
    </div>
    <div style="text-align: center;">
      <h2>Akrab Super</h2>
      <p>Area 1: 65 GB</p>
      <p>Area 2: 70 GB</p>
      <p>Area 3: 83 GB</p>
      <p>Area 4: 123 GB</p>
      <p>Rp 69,000</p>
    </div>
    <div style="text-align: right;">
      <h2>Paket Lain</h2>
      <p>Area 1: 85 GB</p>
      <p>Area 2: 90 GB</p>
      <p>Area 3: 103 GB</p>
      <p>Area 4: 143 GB</p>
      <p>Rp 85,000</p>
    </div>
  </div>
</body>
</html>

