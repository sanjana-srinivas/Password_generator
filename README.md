# Password Generator Application

## Overview

A professional, feature-rich **Password Generator** application built with Python and Tkinter. This desktop utility provides secure, customizable password generation with an intuitive graphical user interface. The application includes advanced features such as password visibility toggling, strength evaluation, history management, and theme customization.

## Key Features

### Core Functionality
- **Secure Password Generation**: Generates random passwords with customizable length (minimum 4 characters)
- **Custom Character Sets**: Users can selectively enable/disable character types:
  - Lowercase letters (a-z)
  - Uppercase letters (A-Z)
  - Digits (0-9)
  - Special characters (#@_.$)
- **Guaranteed Diversity**: Ensures at least one character from each selected category
- **Smart Formatting**: Prevents passwords from ending with special characters for improved compatibility

### User Experience Features
- **Password Visibility Toggle**: Click the eye icon (👁️/⊘) to show/hide generated passwords
- **Password Strength Indicator**: Real-time strength assessment (Weak, Medium, Strong, Very Strong)
- **Recommended Length Label**: Displays optimal password length suggestion (12-16 characters)
- **Password History**: Maintains a list of recently generated passwords for quick access
- **History Selection**: Click any password in history to display and copy it

### Interface & Customization
- **Dark/Light Theme Toggle**: Switch between light and dark modes for comfortable viewing
- **Clipboard Integration**: One-click password copy to system clipboard with confirmation
- **Clear Functionality**: Quick clear of input field, generated password, and history selection
- **Clear History with Confirmation**: Secure history clearing with yes/no verification dialog

### Keyboard Shortcuts
| Shortcut | Action |
|----------|--------|
| `Enter` | Generate password (from input field) |
| `Ctrl+C` | Copy password to clipboard |
| `Ctrl+L` | Clear all fields and selection |
| `Ctrl+H` | Clear entire password history |
| `Ctrl+T` | Toggle dark/light theme |

## Technical Stack

- **Language**: Python 3.x
- **GUI Framework**: Tkinter (built-in with Python)
- **Image Processing**: Pillow (PIL)
- **Additional Modules**: 
  - `random` - Cryptographically randomized character selection
  - `messagebox` - User notifications and confirmations

## Requirements

### System Requirements
- Python 3.6 or higher
- Windows, macOS, or Linux

### Dependencies
```
Pillow>=9.0.0
```

## Installation

### Step 1: Clone or Download
```bash
# Navigate to the project directory
cd "password generator"
```

### Step 2: Install Dependencies
```bash
pip install Pillow
```

### Step 3: Run the Application
```bash
python pass_gen.py
```

## Usage Guide

### Basic Password Generation
1. Enter desired password length in the input field
2. Check/uncheck character type options as needed
3. Click **GENERATE PASSWORD** or press `Enter`
4. Generated password appears in the display box with strength indicator

### Viewing Password
- Click the eye icon (👁️) in the password display to reveal the password
- Click again to hide (⊘)

### Managing Passwords
- **Copy**: Select from history or use displayed password, then click **COPY**
- **Clear**: Click **CLEAR** to reset input and display
- **History**: Click any password in the history list to select and display it
- **Clear History**: Click **Clear History** button to remove all saved passwords (with confirmation)

### Theme Switching
- Click the moon/sun icon (🌓) in the bottom-right corner to toggle dark mode

## Project Structure

```
password generator/
├── pass_gen.py              # Main application file
├── pass_gen.png             # Header image (optional)
└── README.md                # This file
```

## Code Architecture

### Main Class: `password_generator`

#### Methods
- **`__init__(root)`**: Initializes UI components, layout, and keyboard bindings
- **`generate_password()`**: Core logic for password generation with validation and strength calculation
- **`copy_to_clipboard()`**: Manages clipboard operations with error handling
- **`clear_fields()`**: Resets input, display, and history selection
- **`clear_history()`**: Clears password history with confirmation dialog
- **`toggle_theme()`**: Switches application theme and updates all widget colors
- **`toggle_visibility()`**: Toggles password masking in the display entry
- **`on_history_select(event)`**: Handles history list selection events

### Password Generation Algorithm
1. Validates user input (non-empty, valid integer, minimum length)
2. Builds character pools based on selected character types
3. Ensures at least one character from each enabled category
4. Fills remaining length with random characters from combined pool
5. Shuffles character array to randomize positions
6. Validates that password does not end with special character (reshuffles if needed)
7. Calculates strength score based on length and character diversity
8. Adds password to history and updates strength indicator

## Strength Calculation

Strength is calculated on a 0-7 scale:
- **Length Bonus**: +1 (≥6), +2 (≥8), +3 (≥12)
- **Character Diversity**: +1 per category present (max +4)

**Strength Levels**:
- < 40%: Weak
- 40-70%: Medium
- 70-90%: Strong
- ≥ 90%: Very Strong

## Features Implemented

Secure password generation with custom character sets  
Password visibility toggle with fixed emoji placement  
Real-time password strength indicator  
Password history with selection support  
Dark/light theme toggle  
Keyboard shortcuts for all major actions  
Copy-to-clipboard with confirmation  
Clear history with safety confirmation  
Input validation and error messages  
Professional UI/UX design  

## Error Handling

The application includes comprehensive error handling:
- Input validation with user-friendly error messages
- Image file not found handling (graceful degradation)
- Clipboard operation error catching
- Safe theme toggle with exception handling

## Notes

- Passwords are generated locally without external network calls
- No data is stored beyond the session (unless user manually exports)
- Recommended password length: 12-16 characters for optimal security
- Special characters are limited to (#@_.$) for maximum compatibility with common systems



