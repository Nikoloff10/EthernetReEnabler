# Auto Ethernet Re-Enabler

A Windows utility that automatically disables and re-enables network adapters to refresh network connections.

## Features

- Configurable network adapter name
- Multiple configuration methods
- Error handling and validation
- Windows startup integration
- Scheduled task creation
- Windows Defender exclusion

## Configuration

The adapter name can be configured in multiple ways (in order of priority):

### 1. Command Line Arguments
```powershell
AutoEthernetReEnabler.exe --adapter "Wi-Fi"
# or
AutoEthernetReEnabler.exe -a "Ethernet 2"
```

### 2. Environment Variable
```powershell
# Set environment variable
$env:ETHERNET_ADAPTER_NAME = "Wi-Fi"
AutoEthernetReEnabler.exe

# Or create a .env file (copy from config.example.env)
```

### 3. Default Value
If no configuration is provided, it defaults to "Ethernet"

## Usage

### List Available Adapters
```powershell
AutoEthernetReEnabler.exe --list-adapters
# or
AutoEthernetReEnabler.exe -l
```

### Run with Specific Adapter
```powershell
AutoEthernetReEnabler.exe --adapter "Your Adapter Name"
```

### Run with Default Settings
```powershell
AutoEthernetReEnabler.exe
```

## Building

If you have the source code and want to build the executable:

```powershell
# Install PyInstaller
pip install pyinstaller

# Build executable
pyinstaller AutoEthernetReEnabler.spec
```

## Requirements

- Windows OS
- Administrator privileges (script will request elevation)
- Network adapter management permissions

## Common Adapter Names

- `Ethernet` (default)
- `Wi-Fi`
- `Local Area Connection`
- `Ethernet 2`
- `Wireless Network Connection`

Use `--list-adapters` to see the exact names on your system.
