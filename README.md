## 📂 Source Code Structure with Component Descriptions

```plaintext
src/
├── assets/                  # Images, fonts, icons
│   ├── images/
│   ├── icons/
│   └── fonts/
│
├── components/              # Reusable UI components
│   ├── common/              # Generic components like buttons, icons, sliders
│   │   ├── Button.jsx
│   │   ├── ToggleSwitch.jsx
│   │   ├── Slider.jsx
│   │   ├── Icon.jsx
│   │   ├── Input.jsx
│   │   └── Modal.jsx
│   │
│   ├── layout/              # Layout components like headers and footers
│   │   ├── Header.jsx
│   │   └── Footer.jsx
│   │
│   ├── airConditioner/      # Components related to AC control
│   │   ├── AirConditionerCard.jsx
│   │   ├── TemperatureControl.jsx
│   │   ├── ModeSelector.jsx
│   │   ├── FanSpeedControl.jsx
│   │   ├── TimerControl.jsx
│   │   └── ToggleSwitch.jsx
│   │
│   ├── sidebar/             # Sidebar components for the equipment list
│   │   ├── EquipmentList.jsx
│   │   └── EquipmentItem.jsx
│   │
│   ├── functionSetup/       # Control panel components
│   │   ├── FunctionSetupOptions.jsx
│   │   ├── FunctionSetupDescription.jsx
│   │   └── FunctionSetupPanel.jsx
│   │
│   └── instruction/         # Instructional components
│       └── InstructionCard.jsx
│
├── pages/                   # Page components
│   ├── AirConditionerDashboard.jsx
│   ├── Equipment.jsx                # Equipment configuration page
│   ├── StateSetup.jsx               # Manage operational states
│   ├── TimeSetup.jsx                # Scheduling page
│   ├── Config.jsx                   # System configuration settings
│   └── Logs.jsx                     # View logs and error reports
│
├── services/                # API services and utilities
│   ├── api.js                       # Axios instance setup
│   ├── AirConditionerService.js     # API calls for AC control
│   ├── NotificationService.js       # Notification handling service
│   └── ConfigService.js             # API calls for app configuration
│
├── utils/                           
│   ├── helpers.js                   # Utility functions
│   ├── formatters.js                # Format data for UI display
│   └── validators.js                # Input validation functions
├── context/                         
│   ├── AirConditionerContext.js     # AC data global state context
│   └── NotificationContext.js       # Notification state context
├── i18n/                            
│   ├── index.js                     # Internationalization setup
│   ├── en.json                      # English translations
│   └── ko.json                      # Korean translations
│
├── constants/               # Static constants
│   └── airConditionerModes.js
│
└── App.jsx                  # Main React component
└── index.js                 # Entry point

```

---

## 🛠️ Component Structure (Pseudocode)

### 1. **Dashboard Page Component**
```jsx
AirConditionerDashboard {
    Header
    Sidebar (EquipmentList)
    FunctionSetupPanel
    AirConditionerCard (repeatable for multiple AC units)
    Footer
}
```

### 2. **AirConditionerCard Component**
> Displays an individual air conditioner's controls and status.

```jsx
AirConditionerCard {
    Icon (AC status)
    TemperatureControl
    ModeSelector
    FanSpeedControl
    TimerControl
    ToggleSwitch (on/off)
    Input
}
```

### 3. **TemperatureControl Component**
> Manages the air conditioner's temperature adjustment logic.

```jsx
TemperatureControl {
    Slider (minTemp, maxTemp, currentTemp, onChange)    // Adjust temperature
    Button (increaseTemp)                               // Increase temperature
    Button (decreaseTemp)                               // Decrease temperature
}
```

### 4. **FunctionSetupPanel Component**
> Main control panel for setting modes, temperatures, and timers.

```jsx
FunctionSetupPanel {
    FunctionSetupOptions(type, hasLabel) : repeatable for each option
    InstructionCard()
    FunctionSetupDescription(Icon, Text): repeatable twice
}
```

### 5. **InstructionCard Component**
> Container wrap FunctionSetupDescription

```jsx
InstructionCard {
    FunctionSetupDescription(Icon, Text): repeatable twice
}
```

### 6. **FunctionSetupOptions Component**
> Base on type , hasLabel props to coding exactly. Ex: Douple Button, Button + Dropdown

```jsx
FunctionSetupOptions {
    Button (ON)
    Button (OFF)
    Button (Timer ON)
    Button (Timer OFF)
    Dropdown (Temperature selector)
    Button (Timer)
    Button (Filter)
    Button (Reset)
}
```

### 7. **FunctionSetupDescription Component**
> Description about function setup below page

```jsx
FunctionSetupDescription {
    Icon
    Text (Title)
    Text (Subtitle)
    Image
}
```
