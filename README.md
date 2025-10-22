# Disable Command+Tab Shortcuts

This Karabiner-Elements configuration disables the Command+Tab (and Command+Shift+Tab) application switching shortcuts on macOS.

## What it does

- **Disables Command+Tab**: Prevents the standard macOS application switcher from opening
- **Disables Command+Shift+Tab**: Prevents reverse application switching
- **Complete blocking**: The shortcuts are completely disabled and won't trigger any action

## Why disable Command+Tab?

Some users prefer to disable these shortcuts for various reasons:

- Prevent accidental application switching
- Use alternative application switching methods
- Customize their workflow with different key combinations
- Avoid conflicts with other applications

## Installation

### Prerequisites

1. **Install Karabiner-Elements**: Download and install [Karabiner-Elements](https://karabiner-elements.pqp.io/) from the official website
2. **Grant permissions**: Make sure Karabiner-Elements has the necessary accessibility permissions in System Preferences > Security & Privacy > Privacy > Accessibility

### Method 1: Import Configuration File

1. Open Karabiner-Elements
2. Go to the **Complex Modifications** tab
3. Click **Add rule** button
4. Click **Import more rules from the Internet** (at the bottom)
5. Click **Import** next to this configuration
6. Enable the rule in the **Complex Modifications** tab

### Method 2: Manual Import

1. Open Karabiner-Elements
2. Go to the **Complex Modifications** tab
3. Click **Add rule** button
4. Click **Import more rules from the Internet** (at the bottom)
5. Click **Import** next to this configuration
6. Enable the rule in the **Complex Modifications** tab

### Method 3: Direct File Import

1. Download the `karabiner.json` file
2. Open Karabiner-Elements
3. Go to the **Complex Modifications** tab
4. Click **Add rule** button
5. Click **Import more rules from the Internet** (at the bottom)
6. Click **Import** next to this configuration
7. Enable the rule in the **Complex Modifications** tab

## Configuration Details

The configuration uses a simple rule that:

- Listens for the `tab` key with the `command` modifier
- Accepts any additional optional modifiers (like `shift`)
- Maps the key combination to an empty action (effectively disabling it)

```json
{
  "from": {
    "key_code": "tab",
    "modifiers": {
      "mandatory": ["command"],
      "optional": ["any"]
    }
  },
  "to": [],
  "type": "basic"
}
```

## Re-enabling Command+Tab

To re-enable the Command+Tab functionality:

1. Open Karabiner-Elements
2. Go to the **Complex Modifications** tab
3. Find the "Disable Command+Tab" rule
4. Click the **Remove** button or disable the rule

## Troubleshooting

- **Rule not working**: Make sure Karabiner-Elements is running and has accessibility permissions
- **Permission denied**: Go to System Preferences > Security & Privacy > Privacy > Accessibility and enable Karabiner-Elements
- **Rule not appearing**: Try restarting Karabiner-Elements after importing the configuration

## License

This configuration is provided as-is for educational and personal use.
