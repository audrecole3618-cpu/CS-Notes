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