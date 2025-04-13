<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>QR Code Scanner</title>
  <script src="https://unpkg.com/html5-qrcode" type="text/javascript"></script>
  <style>
    #reader {
      width: 300px;
      margin: auto;
      padding-top: 50px;
    }
    #result {
      text-align: center;
      margin-top: 20px;
      font-size: 1.2rem;
      color: green;
    }
  </style>
</head>
<body>
  <h2 style="text-align:center;">QR Code Scanner</h2>
  <div id="reader"></div>
  <div id="result">Scan a QR code</div>

  <script>
    function onScanSuccess(decodedText, decodedResult) {
      document.getElementById('result').innerText = `Scanned: ${decodedText}`;
      // Optional: Stop scanning after first scan
      html5QrcodeScanner.clear();
    }

    const html5QrcodeScanner = new Html5QrcodeScanner(
      "reader", 
      { fps: 10, qrbox: 250 }, 
      false
    );
    html5QrcodeScanner.render(onScanSuccess);
  </script>
</body>
</html>
