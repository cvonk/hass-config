# Rainforest's Eagle 200 for the whole house

Configured using Integration that pulls PG&E Electricity usage data

# EmonESP for the apartment (https://github.com/CircuitSetup/Split-Single-Phase-Energy-Meter)

Configured for MQTT, instead of Emoncms account/apikey

CT1 should be on the same side of the split phase as the breaker for the plug
that the AC transformer is plugged into, and should point in the direction of
the current flowing into the house.
CT2 should point in the opposite direction as CT1.
see https://github.com/CircuitSetup/Split-Single-Phase-Energy-Meter

# Estimated Idle Power

Estimated Arlo Pro 3 power usage
based on
 - base runs on 12vdc/1.5a ~= 20 W
 - 3 cameras runs from 5v/1.8a to 9v/1.1a ~= 10 W each

Estimated always-on usage
  ~30 W smart plugs (10)
  ~20 W Pool equipment
  ~20 W Arlo cameras (3)
  ~10 W microwaves when idle (2)
  ~10 W Eagle 200
  ~10 W low voltage transformers and garage door opener
   ~5 W smoke detectors
   ~5 W stove when idle
   ~5 W HDHomeRun
   ~5 W outside awning
------------------------------------------------------ +
 ~120 W TOTAL ALWAYS ON

# Sonoff Tasmata

Sonoff S31 socket switches also measure power usage

No longer need to trigger a 'discovery annoucement' by going to each Sonoff device pageiot.vonk/)
  Console >  Command > SetOption19 0
while you're at it
  Console >  Command > Timezone -8
  Console >  Command > TelePeriod 30

Remember to calibrate (https://tasmota.github.io/docs/Power-Monitoring-Calibration/)
note that `CurrentSet` expects milliamps [mA]
