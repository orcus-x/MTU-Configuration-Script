
# MTU Configuration Script

This repository contains a script to configure the Maximum Transmission Unit (MTU) size for network interfaces on a Windows operating system. The script uses the `netsh` command to set and display MTU settings for specific network interfaces.

## Purpose

The script is designed to:
1. Set the MTU size for a specified network interface.
2. Display current subinterface configurations.
3. Ensure persistence of the configuration across system reboots.

## Script Details

### Commands Used

1. **Set MTU Size**
   ```plaintext
   netsh interface ipv4 set subinterface "Ethernet" mtu=1350 store=persistent
   ```
   Sets the MTU for the "Ethernet" interface to `1350` bytes. The configuration is stored persistently to survive reboots.

2. **Display Subinterface Configurations**
   ```plaintext
   netsh int ip show subinterfaces
   ```
   Displays the current subinterface configurations, including their MTU values.

3. **Set MTU Size for a Specific Interface**
   ```plaintext
   netsh int ip set subinterface 6 mtu=1350 store=persistent
   ```
   Sets the MTU for a subinterface identified by its index (`6` in this example) to `1350` bytes.

### Notes

- Replace `"Ethernet"` with the name of your desired network interface.
- Replace `6` with the actual index of your subinterface as displayed by the `show subinterfaces` command.

## How to Use

1. Open a Command Prompt with administrative privileges.
2. Copy and paste the relevant commands from the script into the terminal.
3. Verify the changes using the `show subinterfaces` command.

## License

This script is provided under the MIT License. See `LICENSE` for details.

## Contributions

Feel free to submit issues or pull requests if you encounter any problems or have suggestions for improvements.
