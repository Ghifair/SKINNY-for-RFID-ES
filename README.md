# SKINNY-for-RFID-ES
This is an analysis of Arduino performance against the SKINNY encryption algorithm, the analysis is carried out using Kruskal Wallis analysis, the data analyzed is the performance of Arduino which includes, Flash, Memory Usage / RAM, Voltage, Current, and Power. data is taken from each byte that will increase and the relationship is sought between the increase in bytes with the performance of the Arduino itself. The Arduino used is Arduino Uno R3 in the RFID system. The SKINNY algortima used is the entire family of SKINNY 64, which includes SKINNY 64-64, 64-128, 64-192 and SKINNY 128, which includes SKINNY 128-128, 128-256, 128-384. 
## Analysis of the Significance of Arduino Uno Performance on RFID-based ES against SKINNY encryption
The following is an analysis of the significance of Arduino Uno performance on RFID-based ES against RFID systems without encryption. The analysis is done by taking 5 performance data for each byte increment, then the significance change will be compared using Kruskal-Wallis analysis.
### Without Encryption
The following is an analysis of the significance of Arduino Uno performance on RFID-based ES against RFID systems without encryption.
| Result         | Flash Usage | RAM Usage | Power |
|---------------|-------------|-----------|-------|
| H-statistic   | 113,9       | 113,9     | -     |
| p-value       | 2,12×10⁻¹⁴  | 2,12×10⁻¹⁴| -     |
### SKINNY 128-128
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 93,99       | 93,99     | 93,95        | 93,90        | 36,89         | 32,78         |
| p-value       | 2,75×10⁻¹²  | 2,75×10⁻¹²| 2,80×10⁻¹²   | 2,86×10⁻¹²   | 0,005         | 0,001         |
### SKINNY 128-256
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 84,00       | 84,00     | 83,93        | 83,92        | 8,84          | 15,46         |
| p-value       | 3,14×10⁻¹¹  | 3,14×10⁻¹¹| 3,23×10⁻¹¹   | 3,24×10⁻¹¹   | 0,920         | 0,492         |
### SKINNY 128-384
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 74,00       | 74,00     | 73,90        | 73,86        | -             | -             |
| p-value       | 3,61×10⁻¹⁰  | 3,61×10⁻¹⁰| 3,76×10⁻¹⁰   | 3,82×10⁻¹⁰   | -             | -             |

this table shows that Flash Usage and RAM Usage have a p-value of 3.61×10-10 which is far below 0.05. This indicates that changes in data size significantly affect Flash and RAM memory usage. Encrypt Time and Decrypt Time are also significant with p-values of 3.76×10-10 and 3.82×10-10 respectively. This indicates that the execution time increases significantly with the increase in byte size. As for power, the results are valuable because the power during encryption and decryption does not change at all.
### SKINNY 64-64
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 124,00      | 124,00    | 123,97       | 123,97       | 32,00         | 18,94         |
| p-value       | 1,87×10⁻¹⁵  | 1,87×10⁻¹⁵| 1,90×10⁻¹⁵   | 1,89×10⁻¹⁵   | 0,127         | 0,755         |
### SKINNY 64-128
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 124,00      | 124,00    | 123,93       | 123,93       | 124,00        | 124,00        |
| p-value       | 1,87×10⁻¹⁵  | 1,87×10⁻¹⁵| 1,92×10⁻¹⁵   | 1,92×10⁻¹⁵   | 1,87×10⁻¹⁵    | 1,87×10⁻¹⁵    |
### SKINNY 64-192
| Result         | Flash Usage | RAM Usage | Encrypt Time | Decrypt Time | Encrypt Power | Decrypt Power |
|---------------|-------------|-----------|--------------|--------------|---------------|---------------|
| H-statistic   | 119,00      | 119,00    | 118,99       | 118,99       | 119,00        | 119,00        |
| p-value       | 6,29×10⁻¹⁵  | 6,29×10⁻¹⁵| 6,30×10⁻¹⁵   | 6,33×10⁻¹⁵   | 6,29×10⁻¹⁵    | 6,29×10⁻¹⁵    |
### Conclusion
The results of the Kruskal-Wallis statistical test above show that the performance of the Arduino Uno in the RFID-based Embedded System with SKINNY encryption generally has no significant difference based on data size variations, except for some anomalies in RAM usage. In the SKINNY 128-128 configuration, the H-statistic value for Flash and RAM is 93.99 with a p-value of 2.75×10-¹², which means that an increase in data size significantly affects memory usage, while encryption and decryption times also show a significant increase with a p-value below 0.05. In contrast, the power consumption for encryption and decryption, although significant with p-values of 0.005 and 0.001, has a lower level of influence than memory usage. In the 64-128 and 64-192 SKINNY configurations, anomalies occurred in RAM usage, with large spikes at bytes 368 and 360, indicating potential hardware or memory allocation limitations that need to be further analyzed. Despite this, power consumption remained stable in the range of 0.026-0.03 W, indicating high energy efficiency. The linearly increasing execution time without large fluctuations confirms that the SKINNY algorithm has good scalability although it requires optimization on memory management.
## Efficiency and stability analysis of Arduino Uno performance on ES against SKINNY algorithm with large bytes
### Without Encryption
![Image](https://github.com/user-attachments/assets/d6f5be1c-ebf1-4da2-a515-f728f17b5375)
### SKINNY 128-128
![Image](https://github.com/user-attachments/assets/9fc8b163-4a9b-4003-a4f8-b2d307e97e3e)
### SKINNY 128-192
![Image](https://github.com/user-attachments/assets/35f18795-1a9c-4f2d-b897-40fb9a7dda36)
### SKINNY 128-384
![Image](https://github.com/user-attachments/assets/29233f73-83e8-45b8-8bac-40f9f954e06c)
### SKINNY 64-64
![Image](https://github.com/user-attachments/assets/7669bfa6-13a5-47ce-b864-e3c328a4c225)
### SKINNY 64-128
![Image](https://github.com/user-attachments/assets/ec776ba4-c545-4055-b368-e316ed2a7c02)
### SKINNY 64-192
![Image](https://github.com/user-attachments/assets/aaac5ba7-b109-4d82-a8c7-1cc0871801e6)
### Conclusion
From the graphs given, it can be concluded that, the microcontroller is able to maintain efficiency and performance stability when handling large data sizes. Memory usage and power consumption remain stable over most data sizes, and execution time increases linearly without significant fluctuations. This stability makes the SKINNY algorithm ideal for IoT applications that require large data processing with limited hardware resources. Anomalies found on some data sizes did not generally affect the overall efficiency and stability of the algorithm.

