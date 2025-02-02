# LabVIEW Resettable Counter System (0 to 15)

## **Objective**
Implement a **resettable counter system** in **LabVIEW** that:
- Counts **from 0 to 15** (binary **0000 to 1111**).
- Uses **three buttons** for control:
  - **Count Up by 1**: Increments counter by **1**.
  - **Count Up by 2**: Increments counter by **2**.
  - **Reset Button**: Resets counter to **0**.
- Displays output using **four LEDs** representing the **binary value**.
- Shows a **warning message** if the counter reaches **1111** and an increment is attempted.

---

## **System Requirements**
### **Inputs**
1. **Count Up by 1 Button**  
   - Increments counter by **1**.
2. **Count Up by 2 Button**  
   - Increments counter by **2**.
3. **Reset Button**  
   - Resets counter to **0**.

### **Outputs**
1. **Four LEDs (LED0, LED1, LED2, LED3)**  
   - Represent the binary value of the counter.
   - **LED0** → Least Significant Bit (LSB).  
   - **LED3** → Most Significant Bit (MSB).
2. **Warning Message**
   - Displays **"You reached the max value!"** if an increment is attempted at **1111 (15)**.

---

## **Implementation Steps**
### **1. Initialize Variables**
- Create an **integer counter** initialized to `0`.
- Link **Boolean LEDs** to display the **binary representation**.

### **2. Implement Button Functionality**
- **Count Up by 1 Button:**
  - If `counter < 15`, increment by `1`.
  - If `counter == 15`, show warning message.
- **Count Up by 2 Button:**
  - If `counter < 14`, increment by `2`.
  - If `counter == 15` or `counter == 14`, show warning message.
- **Reset Button:**
  - Set counter to `0`.

### **3. Update LED Outputs**
- Convert **counter value** to **binary**.
- Assign **each bit** to the respective **LED**.

### **4. Display Warning Message**
- Use a **case structure** to check if `counter == 15` and a button press is attempted.
- Show a **warning message** when necessary.

---

## **Expected Behavior**
| Counter Value | Binary (LEDs) | Count Up by 1 | Count Up by 2 | Reset |
|--------------|--------------|---------------|---------------|--------|
| 0 (0000)    | 🔴🔴🔴🔴 | ✅ 1 → 0001 | ✅ 2 → 0010 | ✅ Reset to 0 |
| 14 (1110)   | 🟢🟢🟢🔴 | ✅ 1 → 1111 | ⚠️ Warning | ✅ Reset to 0 |
| 15 (1111)   | 🟢🟢🟢🟢 | ⚠️ Warning | ⚠️ Warning | ✅ Reset to 0 |

---

## **Conclusion**
This **LabVIEW system** successfully:
✅ Implements a **0 to 15** counter with **increment and reset** buttons.  
✅ Uses **four LEDs** to display **binary output**.  
✅ Prevents overflow with a **warning message** at **1111 (15)**.  

This ensures a **robust and interactive** counting mechanism. 🚀
