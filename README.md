# Temperature-Monitoring-and-Alert-System
This project simulates an embedded temperature monitoring system-like the ones used in refrigerators, greenhouses, or microcontrollers.
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h> // for sleep() function

int main() {
    float temperature;
    const float THRESHOLD = 40.0; // temperature limit in °C

    printf("---- EMBEDDED TEMPERATURE MONITORING SYSTEM ----\n");
    printf("System Initializing...\n");
    sleep(1);

    while (1) {
        printf("\nEnter current temperature (°C): ");
        scanf("%f", &temperature);

        if (temperature > THRESHOLD) {
            printf("⚠️ ALERT! High Temperature: %.2f°C\n", temperature);
            printf("Activating Cooling Fan...\n");
        } else if (temperature < 10) {
            printf("⚠️ ALERT! Low Temperature: %.2f°C\n", temperature);
            printf("Activating Heater...\n");
        } else {
            printf("✅ Temperature Normal: %.2f°C\n", temperature);
            printf("System Stable.\n");
        }

        printf("Reading next value in 3 seconds...\n");
        sleep(3); // delay for 3 seconds like a real sensor interval
    }

    return 0;
}
