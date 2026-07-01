# Calibration

Calibration is planned for `v0.2.0`.

The project will not use a generic internet formula for pH conversion. Every pH probe and PH-4502C board pair behaves differently, so HydroMonitor will use two-point software calibration:

1. Put the probe in pH 7.00 buffer and record mV.
2. Put the probe in pH 4.00 or pH 10.00 buffer and record mV.
3. Calculate pH using linear interpolation.

For `v0.1.0`, only the filtered probe voltage is shown. This lets us confirm that the ADC input and wiring are stable before adding pH math.
