
# 🛠 PLC Timer and Counter Logic for Automated Stamping Device

This project demonstrates the implementation of timer and counter logic in Siemens TIA Portal for automating a **stamping process** commonly used in manufacturing industries. It simulates a system where a **cylinder extends** to perform a **stamping action**, waits for a preset amount of time, and **counts the number of successful stampings** using a CTU (count-up) counter and TON (on-delay) timers.

## ✅ Real-world Use Case
In automated production lines (e.g., metal forming, packaging, PCB drilling), devices must apply force or heat in precise intervals and count the number of actions for quality control or batch tracking. This logic is used to:

- Control timing of the cylinder extension using TON.
- Ensure accuracy in each stamping cycle.
- Count the number of stamps for production batch monitoring.

## 📂 Project Structure

```
/StampingDeviceProject
├── README.md
├── Project_Screenshot.png
└── Timers_and_Counters.ap15_1
```

## 🔄 Logic Breakdown

### Main Logic Flow (OB1)

1. **Start Condition:**
   - The stamping process starts when:
     - The `start` button (`%I0.0`)
     - The sensor input (`%I0.1`)
     - And the counter not yet reaching preset value
     - All are active.

2. **Cylinder Activation:**
   - Output coil `%Q0.0` (cylinder1) turns ON.
   - Triggers a TON timer (`DB1`) called `stamptime`.

3. **Stamp Time Delay:**
   - The timer ensures the stamping head remains active for the set time (`PT`).
   - Once the time elapses, timer output `Q` becomes TRUE.

4. **Counter Logic:**
   - After the stamping time elapses:
     - The timer’s `Q` output triggers the CTU counter (`DB2`).
     - Increments the stamp count (`CV`) by 1.
     - The counter has a preset value (`PV`) like 10 cycles.
     - When count reaches PV, output `Q` becomes TRUE to stop further stamping.

5. **Wait Time Before Restarting:**
   - A second TON timer (`DB3`) called `waittime` is used to delay the next cycle.
   - Controlled by the counter `Q` output.

## 🧠 Key Components

| Element            | Description                                |
|--------------------|--------------------------------------------|
| `%I0.0`            | Start Push Button                          |
| `%I0.1`            | Sensor Input (object detected)             |
| `%Q0.0`            | Cylinder Activation (Output)               |
| `IEC_Timer_0_DB`   | TON Timer for stamping hold time           |
| `IEC_Counter_0_DB` | CTU Counter for stamp count                |
| `IEC_Timer_0_DB_1` | TON Timer for post-stamp wait              |
| `CV`               | Current Value of counter                   |
| `PV`               | Preset Value for stamping limit (e.g. 10)  |

## ⚙️ How to Simulate

### Requirements:
- Siemens TIA Portal v15.1 or later
- S7-1200 (e.g., CPU 1215C DC/DC/DC)

### Steps:
1. Open the `.ap15_1` file in TIA Portal.
2. Download to a simulator or physical PLC.
3. Monitor tags: `start`, `sensorb1`, `stamptime`, `waittime`.
4. Toggle inputs to simulate stamping process.
5. Observe counter increment and cylinder ON/OFF.

## 📸 Screenshot

![Screenshot](./Project_Screenshot.png)

## 🧪 Future Improvements

- Add **HMI** visualization of count value.
- Implement **reset** or **manual override** function.
- Add **fault detection** if sensor does not respond in time.

## 🏁 Conclusion

This project is ideal for showcasing automation logic using basic PLC instructions like TON timers and CTU counters. It reflects real-world automation scenarios in stamping or repetitive tasks requiring timing precision and event counting.

## 📘 License

This project is open-source and licensed under the [MIT License](LICENSE).
