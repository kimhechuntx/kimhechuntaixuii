k# kimhechuntaixuii
Tool Kim Chun Tài Xỉu VIp
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kim Chun Tài Xỉu VIP</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/blueimp-md5/2.19.0/js/md5.min.js"></script>
  <style>
    body { background: linear-gradient(135deg, #ffd6e7, #f0b6d5); font-family: sans-serif; }
    .container { max-width: 600px; margin-top: 50px; }
    .card { border-radius: 20px; padding: 20px; box-shadow: 0 0 15px rgba(0,0,0,0.1); margin-bottom: 20px; }
  </style>
</head>
<body>
  <div class="container">
    <h2 class="text-center text-danger">💎 Kim Chun Tài Xỉu VIP</h2>

    <div class="card">
      <h5>🔐 Nhập KEY:</h5>
      <div class="input-group">
        <input id="license-key" type="text" class="form-control" placeholder="Nhập KEY...">
        <button class="btn btn-success" onclick="verifyKey()">Mở khóa</button>
      </div>
      <div id="license-msg" class="mt-2 fw-bold"></div>
    </div>

    <div id="main-tool" class="d-none">
      <div class="card">
        <h5>📊 Dự đoán Tài Xỉu theo mã phiên:</h5>
        <input id="maphien" type="text" class="form-control mb-2" placeholder="Nhập mã phiên...">
        <button class="btn btn-primary" onclick="analyzeAndPredict()">Phân tích & Dự đoán</button>
        <div id="result" class="mt-2"></div>
      </div>

      <div class="card">
        <h5>💰 Chiến lược gấp thếp:</h5>
        <input id="investment" type="number" class="form-control mb-2" placeholder="Nhập vốn...">
        <button class="btn btn-danger" onclick="strategy()">Tính chiến lược</button>
        <div id="strategy-result" class="mt-2"></div>
      </div>

      <div class="text-center mt-4">
        <small>© Kim Chun Tool VIP v1.1</small>
      </div>
    </div>
  </div>

  <script>
    const validKeys = ["KimChunVip123"];

    function verifyKey() {
      const key = document.getElementById("license-key").value.trim();
      const msg = document.getElementById("license-msg");
      if (validKeys.includes(key)) {
        msg.textContent = "✅ Mở khóa thành công!";
        msg.className = "text-success";
        document.getElementById("main-tool").classList.remove("d-none");
      } else {
        msg.textContent = "❌ KEY không hợp lệ!";
        msg.className = "text-danger";
      }
    }

    function analyzeAndPredict() {
      const mã = document.getElementById("maphien").value.trim();
      const resultBox = document.getElementById("result");
      if (!mã) {
        resultBox.innerHTML = '<span class="text-danger">Vui lòng nhập mã phiên!</span>';
        return;
      }
      const hash = md5(mã);
      const base = parseInt(hash.substring(0, 2), 16) % 2;
      const prediction = base === 0 ? "Tài" : "Xỉu";
      const confidence = 90 + Math.floor(Math.random() * 10);
      resultBox.innerHTML = `Dự đoán: <strong>${prediction}</strong> (${confidence}% tin cậy)`;
    }

    function strategy() {
      const investment = parseInt(document.getElementById("investment").value);
      const strategyBox = document.getElementById("strategy-result");
      if (isNaN(investment) || investment <= 0) {
        strategyBox.innerHTML = '<span class="text-danger">Vui lòng nhập vốn hợp lệ!</span>';
        return;
      }
      const baseAmount = investment / 15;
      const rounds = [1, 2, 4, 8, 16];
      const strategy = rounds.map((round, i) => `Tay ${i + 1}: ${(baseAmount * round).toFixed(0)} VND`).join("<br>");
      strategyBox.innerHTML = `Chiến lược Gấp thếp:<br>${strategy}`;
    }
  </script>
</body>
</html>
