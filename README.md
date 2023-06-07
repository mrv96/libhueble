# libhueble

Control Philips Hue light by bluetooth in python

## Requirements

- Bluetooth
- Python
   - bleak
   - rxby
   - struck

## Pairing

1. In the Hue BT app, go to **Settings** > **Voice Assistants** > **Amazon Alexa** and tap **Make visible**.¹
2. Open the bluetoothctl shell:
   ```
   sudo bluetoothctl
   ```
3. Start the discovery:
   ```
   scan on
   ```
4. Write down the MAC address of your light.
5. Pair to your light:
   ```
   pair [MAC address]
   trust [MAC address]
   ```
6. Done, you can now pair the light to your phone again.

## Usage

# Install the requirements

Install the required packages from requirements.txt

# Import the library

Import the library into your python code

# Connect to a lamp

```
lamp = lamp('BLUETOOTH_MAC_ADDRESS')
await lamp.connect()
```

# Get lamp proporties

```
try:
   await lamp.is_connected()
   await lamp.get_model()
   await lamp.get_power()
   await lamp.get_brightness()
   await lamp.get_temperature()
   await lamp.get_color_xy()
   await lamp.get_color_rgb()
```

# Change lamp proporties

```
try:
   await lamp.set_power(True)
   await lamp.set_brightness(1.0)
   await lamp.set_temperature(1.0)
   await lamp.set_color_rgb(1.0, 0.0, 0.0)
   await lamp.set_color_xy(1.0, 1.0)
```

# Disconnect lamp

```
lamp.disconnect()
```

## Compatibility

- [X] Linux
- [?] Windows - Strange behaviour, sometimes doesnt work
