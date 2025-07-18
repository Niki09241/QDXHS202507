<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>7月青岛小勇士活动</title>
  <style>
    body { 
      font-family: Arial, sans-serif; 
      padding: 30px; 
      background-color: #f5faff;
    }
    h2 {
      color: #2c3e50;
    }
    input, button { 
      font-size: 18px; 
      padding: 10px; 
      margin-top: 10px; 
      width: 300px;
    }
    button {
      cursor: pointer;
    }
    #result { 
      margin-top: 20px; 
      font-size: 18px; 
      color: #333; 
      background: #fff; 
      padding: 20px; 
      border-radius: 8px; 
      box-shadow: 0 0 10px rgba(0,0,0,0.05);
    }
  </style>
</head>
<body>
  <h2>7月青岛“追光小勇士”活动场次与编码查询</h2>
  <p>请输入您的姓名或身份证号后六位进行查询：</p>
  <input type="text" id="inputValue" placeholder="姓名或身份证后六位">
  <button onclick="search()">查询</button>
  <div id="result"></div>

  <script src="data.js"></script>
  <script>
    function search() {
      const input = document.getElementById("inputValue").value.trim();
      const matches = participants.filter(p => p.name === input || p.idLast6 === input);
      const resultDiv = document.getElementById("result");

      if (matches.length > 0) {
        resultDiv.innerHTML = matches.map(match => `
          查询成功！<br>
          姓名：<strong>${match.name}</strong><br>
          报名场次：<strong>${match.session}</strong><br>
          编码：<strong>${match.code}</strong>
        `).join('<hr>');
      } else {
        resultDiv.innerHTML = "未找到匹配的信息，请检查输入是否正确。";
      }
    }
  </script>
</body>
</html>
