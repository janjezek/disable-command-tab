# Disable Command+Tab Shortcuts

This repository contains Karabiner-Elements configurations for customizing keyboard behavior on macOS, including disabling Command+Tab shortcuts and creating a Hyper key from Caps Lock.

## What it does

### 1. Disable Command+Tab Shortcuts (`disable-command-tab.json`)

- **Disables Command+Tab**: Prevents the standard macOS application switcher from opening
- **Disables Command+Shift+Tab**: Prevents reverse application switching
- **Complete blocking**: The shortcuts are completely disabled and won't trigger any action

### 2. Hyper Key Configuration (`hyper-key.json`)

- **Caps Lock as Hyper Key**: Transforms Caps Lock into a Hyper key (Ctrl+Alt+Cmd+Shift)
- **Hold behavior**: When held down, Caps Lock acts as a Hyper key modifier
- **Tap behavior**: When tapped quickly, Caps Lock functions as Escape
- **Powerful modifier**: Hyper key can be used for custom shortcuts in other applications

## Why use these configurations?

### Disable Command+Tab

Some users prefer to disable these shortcuts for various reasons:

- Prevent accidental application switching
- Use alternative application switching methods
- Customize their workflow with different key combinations
- Avoid conflicts with other applications

### Hyper Key

The Hyper key provides several benefits:

- **More modifier combinations**: Access to Ctrl+Alt+Cmd+Shift combinations
- **Efficient workflow**: Use Caps Lock for both Escape and as a powerful modifier
- **Application shortcuts**: Many apps support Hyper key combinations
- **Ergonomic**: Keeps your hands on the home row

## Installation

### Prerequisites

1. **Install Karabiner-Elements**: Download and install [Karabiner-Elements](https://karabiner-elements.pqp.io/) from the official website
2. **Grant permissions**: Make sure Karabiner-Elements has the necessary accessibility permissions in System Preferences > Security & Privacy > Privacy > Accessibility

### Method 1: Import Individual Rules

1. Open Karabiner-Elements
2. Go to the **Complex Modifications** tab
3. Click **Add rule** button
4. Click **Import more rules from the Internet** (at the bottom)
5. Click **Import** next to the configuration you want
6. Enable the rule in the **Complex Modifications** tab
7. Repeat for each configuration file

### Method 2: Direct File Import

1. Download the JSON files you want:
   - `disable-command-tab.json` - Disables Command+Tab shortcuts
   - `hyper-key.json` - Creates Hyper key from Caps Lock
2. Open Karabiner-Elements
3. Go to the **Complex Modifications** tab
4. Click **Add rule** button
5. Click **Import more rules from the Internet** (at the bottom)
6. Click **Import** next to the configuration you want
7. Enable the rule in the **Complex Modifications** tab

## Configuration Details

### Disable Command+Tab (`disable-command-tab.json`)

This configuration uses a simple rule that:

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

### Hyper Key (`hyper-key.json`)

This configuration transforms Caps Lock into a Hyper key:

- **Hold behavior**: Maps to Ctrl+Alt+Cmd+Shift (Hyper key)
- **Tap behavior**: Functions as Escape when tapped quickly
- **Modifier combination**: `left_shift` + `left_command` + `left_control` + `left_option`

```json
{
  "from": {
    "key_code": "caps_lock",
    "modifiers": { "optional": ["any"] }
  },
  "to": [
    {
      "key_code": "left_shift",
      "modifiers": ["left_command", "left_control", "left_option"]
    }
  ],
  "to_if_alone": [{ "key_code": "escape" }],
  "type": "basic"
}
```

## Disabling/Re-enabling Rules

### To disable or remove rules:

1. Open Karabiner-Elements
2. Go to the **Complex Modifications** tab
3. Find the rule you want to disable:
   - "Disable Command+Tab" for the Command+Tab disabling
   - "Make caps_lock a Hyper key" for the Hyper key configuration
4. Click the **Remove** button or disable the rule

### To re-enable default behavior:

- **Command+Tab**: Remove the "Disable Command+Tab" rule
- **Caps Lock**: Remove the "Make caps_lock a Hyper key" rule

## Troubleshooting

- **Rule not working**: Make sure Karabiner-Elements is running and has accessibility permissions
- **Permission denied**: Go to System Preferences > Security & Privacy > Privacy > Accessibility and enable Karabiner-Elements
- **Rule not appearing**: Try restarting Karabiner-Elements after importing the configuration
- **Hyper key not working**: Make sure no other applications are using Caps Lock for other purposes
- **Command+Tab still working**: Check that the rule is enabled in the Complex Modifications tab
- **Caps Lock not functioning as Escape**: Ensure the Hyper key rule is properly imported and enabled

## License

This configuration is provided as-is for educational and personal use.
