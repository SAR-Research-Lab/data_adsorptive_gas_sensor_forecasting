This dataset was used in the paper "Adsorptive Gas Sensor Response Forecasting to Enable Breath-by-Breath Analysis."

===================================

Each .csv file in the dataset includes data taken from one breath sample. 
After a short start-up period, a vacuum pump is activated for 90 seconds, which exposes the sensors to exhaled breath. 
After this, a cleaning period of 4 minutes is initiated, which pumps ambient air back into the sensing enclosure to purge the sensors for the next experiment. 
The data collected in these files covers the entire exposure and cleaning period. 
The sampling frequency is fixed at 20 Hz for all samples. 
Each file contains 4 columns of data.

===================================

1. Column 1 contains the raw ADC values (12-bit ADC @ 3.3V) read from the TGS 822 VOC sensor, in sequence.

2. Column 2 contains the raw ADC values (12-bit ADC @ 3.3V) read from the TGS 813 VOC sensor, in sequence.

3. Column 3 contains the raw ADC values (12-bit ADC @ 3.3V) read from the SGX-4OX oxygen sensor, in sequence.

4. Column 4 contains the airflow measurement in mL/min measured by the SFM3200 airflow sensor.

===================================

To convert the three gas sensor measurements to engineering units, the equations below can be used. 
The TGS 822 and TGS 813 sensors are the upper element of a simple voltage divider circuit. The lower element is a 14K resistor connected to GND. 
The SGX-4OX sensor outputs a current, which is measured across a 100-Ohm shunt by an amplifier circuit with a gain of 225.

===================================

1. [(3.3*14) / (x*3.3 / 4095)] - 14   : result in kOhm

2. [(3.3*14) / (x*3.3 / 4095)] - 14   : result in kOhm

3. 1e6 * [(x*3.3 / 4095) / (225*100)] : result in uAmp