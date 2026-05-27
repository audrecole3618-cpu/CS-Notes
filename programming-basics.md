# 💻 Programming Foundations

!> **PRO TIP:** In programming, the `=` sign is an **action**. It takes the value on the right and "shoves" it into the variable on the left.

---

### 2. Pseudocode vs. Actual Code

**Actual Code (Python) Example:**

```python
if coffee_cup == "empty":
    refill()

# This is a comment - the computer ignores it
name = "Audi"
iced_coffee_count = 1

print("Welcome back to the Vault, " + name)
print("Today's energy level: " + str(iced_coffee_count) + " coffee(s)")
```

---

## 🏎️ The SNHU Translator: Python vs. Coral

In **CS-205**, you'll be switching between these two. Here is how the same logic looks in both:

| Feature | Python (Real World) | Coral (Classroom/Lab) |
| :--- | :--- | :--- |
| **Variables** | `count = 5` | `integer count` <br> `count = 5` |
| **Output** | `print("Hi")` | `Put "Hi" to output` |

### 🛠️ Practice Challenge: Iced Coffee Logic (Coral Version)

```coral
// 1. Declare the variables first (Strict Rule!)
integer iced_coffee_count
string name

// 2. Assign the values
name = "Audi"
iced_coffee_count = 1

// 3. Print to the screen
Put "Welcome back to the Vault, " to output
Put name to output
Put "Today's energy level: " to output
Put iced_coffee_count to output
```

---

### 🕹️ The "High/Low" Security Challenge

<iframe src="https://trinket.io/embed/python/f109c065f3?outputOnly=true&runOption=run" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
# 🎮 Audi's InfoSec Sandbox: Port Hacker

> "Testing system logic through simulation." 💻⚡

Welcome to the live coding sandbox. Below is an interactive terminal game built entirely using JavaScript and HTML embedded directly into our Markdown vault. Use this to practice state tracking, DOM manipulation, and logic loops!

---

### 🚨 Live Simulator: Firewall Bypass

Can you infiltrate the target mainframe before the defensive subroutines lock you out? Click the correct action based on the port status!

<div id="game-box" style="background: rgba(15, 10, 25, 0.9); border: 2px dashed #ff79c6; border-radius: 16px; padding: 25px; font-family: 'Courier New', Courier, monospace; color: #03dac6; max-width: 500px; margin: 20px auto; box-shadow: 0 10px 30px rgba(0,0,0,0.5); text-align: center;">

  <div style="font-weight: bold; font-size: 1.2rem; color: #ff79c6; margin-bottom: 15px;">
    ⚡ TERMINAL UPLINK ACTIVE ⚡
  </div>

  <div id="status-display" style="background: rgba(0,0,0,0.4); border-radius: 8px; padding: 15px; min-height: 80px; margin-bottom: 20px; font-size: 1.1rem; display: flex; flex-direction: column; justify-content: center; align-items: center; border: 1px solid rgba(255,255,255,0.05);">
    <span id="port-text" style="color: #ffffff; font-weight: bold;">Press START to begin infiltration...</span>
    <span id="hint-text" style="color: #bb86fc; font-size: 0.85rem; margin-top: 5px;"></span>
  </div>

  <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 20px; font-size: 0.9rem;">
    <div style="background: rgba(255,255,255,0.05); padding: 8px; border-radius: 6px;">
      SCORE: <span id="game-score" style="color: #fff; font-weight: bold;">0</span>
    </div>
    <div style="background: rgba(255,255,255,0.05); padding: 8px; border-radius: 6px;">
      TIME LEFT: <span id="game-timer" style="color: #ff5555; font-weight: bold;">--</span>
    </div>
  </div>

  <div id="controls" style="display: flex; justify-content: space-around; gap: 10px;">
    <button id="btn-start" onclick="startGame()" style="background: #bb86fc; color: #110022; border: none; padding: 12px 30px; font-weight: bold; border-radius: 8px; cursor: pointer; font-family: inherit; width: 100%; transition: transform 0.2s;">
      INITIALIZE EXPLOIT
    </button>
    <button id="btn-bypass" onclick="checkAction('bypass')" style="display: none; background: #03dac6; color: #110022; border: none; padding: 12px 20px; font-weight: bold; border-radius: 8px; cursor: pointer; font-family: inherit; flex: 1;">
      🔓 BYPASS
    </button>
    <button id="btn-filter" onclick="checkAction('filter')" style="display: none; background: #ff79c6; color: #110022; border: none; padding: 12px 20px; font-weight: bold; border-radius: 8px; cursor: pointer; font-family: inherit; flex: 1;">
      🛡️ FILTER
    </button>
  </div>
</div>

<script>
  let score = 0;
  let timer;
  let timeLeft = 0;
  let currentTarget = ""; 
  let gameActive = false;

  const portsPool = [
    { name: "Port 80 (HTTP)", action: "bypass", hint: "Unencrypted web traffic - safe to bypass" },
    { name: "Port 22 (SSH Brute Force)", action: "filter", hint: "Attacker detecting! Filter the connection" },
    { name: "Port 443 (HTTPS)", action: "bypass", hint: "Secure layer uplink - bypass safely" },
    { name: "Port 3389 (RDP Exploit)", action: "filter", hint: "Unauthorized remote access protocol - Filter!" },
    { name: "Port 21 (FTP Plaintext)", action: "bypass", hint: "Legacy file port exposed - bypass and extract" }
  ];

  function startGame() {
    score = 0;
    gameActive = true;
    document.getElementById("game-score").innerText = score;
    document.getElementById("btn-start").style.display = "none";
    document.getElementById("btn-bypass").style.display = "inline-block";
    document.getElementById("btn-filter").style.display = "inline-block";
    nextTurn();
  }

  function nextTurn() {
    if (!gameActive) return;
    
    // Pick a random port event
    let target = portsPool[Math.floor(Math.random() * portsPool.length)];
    currentTarget = target.action;
    
    document.getElementById("port-text").innerText = target.name;
    document.getElementById("hint-text").innerText = target.hint;
    
    // Reset clock per turn
    clearInterval(timer);
    timeLeft = 4; // 4 seconds to decide!
    document.getElementById("game-timer").innerText = timeLeft + "s";
    
    timer = setInterval(() => {
      timeLeft--;
      document.getElementById("game-timer").innerText = timeLeft + "s";
      if (timeLeft <= 0) {
        endGame(false);
      }
    }, 1000);
  }

  function checkAction(playerChoice) {
    if (!gameActive) return;
    
    if (playerChoice === currentTarget) {
      score += 10;
      document.getElementById("game-score").innerText = score;
      nextTurn();
    } else {
      endGame(true); // Wrong action triggers alert
    }
  }

  function endGame(triggeredAlarm) {
    gameActive = false;
    clearInterval(timer);
    document.getElementById("game-timer").innerText = "--";
    
    let msg = triggeredAlarm ? "🚨 ALARM TRIGGERED! FIREWALL LOCKED YOU OUT." : "⏰ TIMER EXPIRED! LINK LOST.";
    document.getElementById("port-text").innerText = msg;
    document.getElementById("hint-text").innerText = "Final Core Score: " + score;
    
    document.getElementById("btn-start").innerText = "RETRY SYSTEM INFILTRATION";
    document.getElementById("btn-start").style.display = "block";
    document.getElementById("btn-bypass").style.display = "none";
    document.getElementById("btn-filter").style.display = "none";
  }
</script>
---

### 💻 Code Insights for Class Practice
This playground targets key computer science logic mechanisms:
1. **Arrays of Objects:** The application draws dynamic hazards out of a custom structural pool `portsPool`.
2. **State Machines:** The game flips between states (`gameActive` toggling true/false) to protect functions from running out of sequence.
3. **Asynchronous Handlers:** `setInterval` acts as a clock subroutine ticking asynchronously in the background.