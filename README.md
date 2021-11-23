# Trainstation system factorio

## Signals

### Green:
- Clock?
- Management signals
    - 0 - 100 ... Open Stations => `O`
    - 100 - 10000 ... All Stations => `S`
    - 10000 - 1000000 ... Avalible Station Places => `A`

### Red
- 0 ... 100 Demand in Trains
- (100 ... 10000 Avalible Ressources)


## Inbound Station
- Station Number => `S` => Send to `A`
- Opens when `S - 1 = O` and `Demand` and `min. 1 Train of Ressources`
- Inbound train keeps Station open. => `C`, with some logic
- If Station open, send `1 O` to `green`
- If all Stations are full, set Trainlimit to `Train Ressources avalible`
- Send `Trainlimit` - `Traincount` 


## Outbound Station
- Demand = (4 * `Chestcount` * `Stacksize` - `Items in Chest`) / 4 * 40 * `Stacksize`
- Open on Demand. 
- Send Train not to Stack:
    - Avalible Inbound Station