#   High Level Requirements 

1. __Multi-node sensing + identification:__  The system must reliably receive and associate moisture readings from ≥ 3 sensor nodes with the correct plant IDs at least once every T seconds (choose T for your design, e.g., 30–120 s), while the watering can is in use.
2. __Correct watering decision__: For each plant profile, the main unit must determine “needs water / doesn’t need water” and compute a dispense target based on (target moisture − current moisture) (or your chosen mapping), using stored plant parameters and recent sensor data.

3. __Accurate dispensing__: When the user selects a plant and presses dispense, the pump must dispense the commanded amount of water with ≤ ±10% volume error, and the electronics must remain operational during/after watering.