### **Wiring the D1 Mini to the Sboard III**  
You need to connect the D1 Mini's GPIO pins to the corresponding Sboard III terminals as follows:

| **D1 Mini (ESP8266)** | **Sboard III** | **Function** |
|------------------|----------------|-------------|
| `D5 (GPIO14)`   | `D_IN`          | Door Contact Status |
| `D6 (GPIO12)`   | `OPEN`          | Exit Button |
| `D7 (GPIO13)`   | `ALARM-`        | Alarm Activation |
| `D1 (GPIO5)`    | `BZ`            | Buzzer Control |
| `d0 (GPIO0)`    | `D1`            | Reader pin  D1 |
| `d1  (GPIO2)`   | `D0`            | Reader pin  D0  |

---

### **Detailed Wiring Guide**
1. **Door Contact Status (`D5` → `D_IN`)**
   - Connect `D5 (GPIO14)` on the D1 Mini to `D_IN` on the Sboard III.
   - Connect `GND` from the D1 Mini to the `GND` terminal near `D_IN` on the Sboard III.
   - This allows the D1 Mini to read the door contact sensor.

2. **Exit Button (`D6` → `OPEN`)**
   - Connect `D6 (GPIO12)` on the D1 Mini to `OPEN` on the Sboard III.
   - Connect `GND` from the D1 Mini to `GND` on the Sboard III.
   - This lets the D1 Mini simulate a button press to open the door.

3. **Alarm Activation (`D7` → `ALARM-`)**
   - Connect `D7 (GPIO13)` on the D1 Mini to `ALARM-` on the Sboard III.
   - Connect `GND` from the D1 Mini to `GND` on the Sboard III.
   - This allows the D1 Mini to log alarm events.

4. **Buzzer Control (`D1` → `BZ`)**
   - Connect `D1 (GPIO5)` on the D1 Mini to `BZ` on the Sboard III.
   - When the D1 Mini turns this pin HIGH, it will activate the buzzer.
   - If needed, use a small NPN transistor (e.g., 2N2222) and a pull-down resistor to ensure proper operation.

---

### **Important Notes**
- **Pull-up resistors**: If you experience floating values (random state changes), you might need to add pull-up resistors (4.7kΩ–10kΩ) on `D_IN`, `OPEN`, and `ALARM-`.
- **Voltage levels**: The Sboard III might operate at 12V for some connections; make sure all GPIOs are **not exposed to more than 3.3V**. If necessary, use a level shifter or optocoupler.
- **Testing**: Before finalizing, check with a multimeter to ensure voltage compatibility.

Let me know if you need further clarification! 🚀