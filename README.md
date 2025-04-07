
<html>
<head>
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
    /* Tambahkan kode CSS berikut untuk membuat layout responsif */
    @media only screen and (max-width: 768px) {
      #stok-table {
        width: 100%;
        margin: 20px auto;
      }
      .container {
        display: block;
      }
      .container div {
        margin-bottom: 20px;
      }
    }
  </style>
</head>
<body>
  <table id="stok-table">
    <thead>
      <tr>
        <th>Nama</th>
        <th>Stok</th>
        <th>Harga</th>
        <th>Status</th>
      </tr>
    </thead>
    <tbody id="stok-body">
    </tbody>
  </table>
  <div class="container">
    </div>
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
          const hargaCell = document.createElement('td');
          const statusCell = document.createElement('td');
          namaCell.innerHTML = item.nama.replace(/\n/g, '<br>');
          stokCell.textContent = item.stok;
          hargaCell.textContent = item.harga;
          statusCell.textContent = item.status;
          row.appendChild(namaCell);
          row.appendChild(stokCell);
          row.appendChild(hargaCell);
          row.appendChild(statusCell);
          stokBody.appendChild(row);
        });
      })
      .catch(error => {
        console.error(error);
      });
  </script>
</body>
</html
<style>
    .whatsapp-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        z-index: 999;
    }
    .whatsapp-button:hover {
        transform: scale(1.2);
        transition: all 0.3s ease-in-out;
    }
</style>

<a href="https://wa.me/6287748842242" target="_blank" class="whatsapp-button">
    <img src="https://i.ibb.co.com/8Lz5rRsD/images-58.jpg" alt="WhatsApp" width="50" height="50">
</a>
