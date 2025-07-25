<h1>Auto Rice Dispenser PLC Project</h1>

### [YouTube Demonstration](https://youtu.be/br58FgKLC3g)

<h2>Description</h2>
This PLC automation project simulates a real-world batch process commonly found in food and beverage industries, specifically modeling the sequential cooking of Jollof Rice. Developed in Siemens TIA Portal v15.1, the logic architecture leverages ladder logic programming techniques including:

-TP (Pulse Timer) to control short-duration activations like oil and water dispensing.

-TON (On-Delay Timer) to manage timed heating, ingredient mixing, and vending delays.

-CTU (Up Counter) to implement a cycle-based control system, limiting the process to 5 complete automated cooking sequences.

-Memory Bit (M) Tags are used for internal logic control and HMI interconnection without tying up physical I/O.

-Cycle Done condition controls logical flow for restarting or ending the batch after a complete cycle.

Each network is modularly designed to represent a phase of the cooking process (water fill, oil dispense, ingredient addition, heat, vending), coordinated via interlocks and timing sequences. The process is triggered by a Start Button and can auto-loop for a pre-defined number of cycles, demonstrating the application of industrial automation standards like state-driven sequencing, timing interlocks, and event-based resets.



<br />

This model is ideal for instructional purposes and demonstrates how timers and counters can be applied to build autonomous, looped control systems in a real manufacturing context.

---

<h2> 🧰 Applications Used in This Project
</h2>

-TIA Portal

-PLC SIM

<h2> 🧰 Github Link
</h2>  (https://github.com/Chidinmaidonor/PLC-Project-Auto-Rice-Dispenser/edit/main/README.md)

<h2> 🧰 Screen recording tool</h2> - OBS Studio

<h3>Ladder Logic Network One to Eight<h3>
<p align="center">
<img src ="Documents/Auto Jollof Rice Cooker/Screenshots/1.png" alt="1">

<img src ="Documents/Auto Jollof Rice Cooker/Screenshots/2.png" alt="2">

<img src ="Documents/Auto Jollof Rice Cooker/Screenshots/3.png" alt="3">

<img src ="Documents/Auto Jollof Rice Cooker/Screenshots/4.png" alt="4">
</p>

</p>
