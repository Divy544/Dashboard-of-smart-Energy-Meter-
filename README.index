<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Smart Energy Meter Dashboard</title>
  
  <!-- Alternative font source -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource/roboto@latest/index.css">
  
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: 'Roboto', Arial, sans-serif; /* Fallback font added */
      background: linear-gradient(135deg, #1e1e1e, #323232);
      color: #e0e0e0;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      padding: 20px;
    }
    h1 {
      margin-bottom: 20px;
      font-size: 2.5em;
      color: #ffa500;
    }
    .dashboard {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      width: 100%;
      max-width: 1000px;
    }
    .card {
      background-color: #2c2c2c;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.3);
      transition: transform 0.2s ease-in-out;
    }
    .card:hover {
      transform: translateY(-5px);
    }
    .card h2 {
      margin-bottom: 10px;
      font-size: 1.4em;
      color: #00ffcc;
    }
    .card p {
      font-size: 1.8em;
      font-weight: 500;
    }
    @media (max-width: 480px) {
      h1 {
        font-size: 2em;
      }
      .card p {
        font-size: 1.5em;
      }
    }
  </style>
</head>
<body>
  <h1>Smart Energy Meter Dashboard</h1>
  <div class="dashboard">
    <div class="card">
      <h2>Voltage (V)</h2>
      <p id="voltage">--</p>
    </div>
    <div class="card">
      <h2>Current (A)</h2>
      <p id="current">--</p>
    </div>
    <div class="card">
      <h2>Power (W)</h2>
      <p id="power">--</p>
    </div>
    <div class="card">
      <h2>Energy (kWh)</h2>
      <p id="energy">--</p>
    </div>
    <div class="card">
      <h2>Units Consumed</h2>
      <p id="units">--</p>
    </div>
    <div class="card">
      <h2>Total Cost (INR)</h2>
      <p id="cost">--</p>
    </div>
  </div>
  
  <script>
    async function fetchData() {
      try {
        const response = await fetch("/data");
        if (!response.ok) throw new Error("Failed to fetch data");
        const data = await response.json();
        
        document.getElementById("voltage").innerText = data.voltage || "--";
        document.getElementById("current").innerText = data.current || "--";
        document.getElementById("power").innerText = data.power || "--";
        document.getElementById("energy").innerText = data.energy || "--";
        document.getElementById("units").innerText = data.unitsConsumed || "--";
        document.getElementById("cost").innerText = data.totalCost || "--";
      } catch (err) {
        console.error("Error fetching data:", err);
      }
    }
    
    setInterval(fetchData, 1000);
    fetchData();
  </script>
</body>
</html>
