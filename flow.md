## 📂 Source Code Structure with Component Descriptions

```plaintext
src/
├── assets/                          
│   ├── images/                      # Static images (AC units, status indicators)
│   ├── icons/                       # Icons (power, fan, temperature, etc.)
│   └── styles/                      # Global styles and variables
│       ├── variables.scss           # Color schemes, spacing, fonts
│       └── global.scss              # Global CSS resets and base styles
├── components/                      
│   ├── common/                      # Reusable common components
│   │   ├── Button.jsx               # Reusable button with custom props
│   │   ├── Input.jsx                # Input field component
│   │   ├── Select.jsx               # Dropdown selector
│   │   ├── Slider.jsx               # Temperature slider component
│   │   ├── ToggleSwitch.jsx         # On/Off toggle component
│   │   └── Icon.jsx                 # Displays status icons
│   ├── layout/                      # Layout components
│   │   ├── Header.jsx               # Top navigation bar
│   │   ├── Sidebar.jsx              # Sidebar with equipment list
│   │   └── Footer.jsx               # Footer section
│   └── airConditionerControl/       # Air Conditioner specific components
│       ├── AirConditionerCard.jsx   # Card for individual AC unit
│       ├── TemperatureControl.jsx   # Temperature adjustment control
│       ├── ModeSelector.jsx         # Select AC mode (cool, heat, etc.)
│       ├── FanSpeedControl.jsx      # Control fan speed levels
│       ├── TimerControl.jsx         # Manage timer settings
│       └── StatusDisplay.jsx        # Display status information
├── pages/                           
│   ├── Dashboard.jsx                # Main dashboard page
│   ├── Equipment.jsx                # Equipment configuration page
│   ├── StateSetup.jsx               # Manage operational states
│   ├── TimeSetup.jsx                # Scheduling page
│   ├── Config.jsx                   # System configuration settings
│   └── Logs.jsx                     # View logs and error reports
├── services/                        
│   ├── api.js                       # Axios instance setup
│   ├── AirConditionerService.js     # API calls for AC control
│   ├── NotificationService.js       # Notification handling service
│   └── ConfigService.js             # API calls for app configuration
├── constants/                       
│   ├── routes.js                    # Route paths
│   ├── apiEndpoints.js              # API endpoint URLs
│   ├── messages.js                  # Success and error messages
│   └── appConfig.js                 # General application configuration
├── hooks/                           
│   ├── useAirConditioner.js         # Hook for managing AC data
│   ├── useNotification.js           # Hook for notification system
│   └── useFetch.js                  # Data fetching utility hook
├── utils/                           
│   ├── helpers.js                   # Utility functions
│   ├── formatters.js                # Format data for UI display
│   └── validators.js                # Input validation functions
├── context/                         
│   ├── AirConditionerContext.js     # AC data global state context
│   └── NotificationContext.js       # Notification state context
├── router/                          
│   └── AppRouter.jsx                # Main routing configuration
├── i18n/                            
│   ├── index.js                     # Internationalization setup
│   ├── en.json                      # English translations
│   └── vi.json                      # Vietnamese translations
├── App.jsx                          # Root component
├── main.jsx                         # Main app entry point
└── index.css                        # Global styles
```

---

## 🛠️ Component Structure (Pseudocode)

### 1. **Dashboard Page Component**
```jsx
Dashboard {
    Header                          // Top navigation
    Sidebar                         // Equipment list navigation
    AirConditionerCard (multiple)   // Display multiple AC units
    Footer                          // Footer with system info
}
```

### 2. **AirConditionerCard Component**
> Displays an individual air conditioner's controls and status.

```jsx
AirConditionerCard {
    StatusDisplay                   // Current status (on/off, temperature)
    TemperatureControl              // Component to adjust temperature
    ModeSelector                    // Select operation mode (cool, heat, etc.)
    FanSpeedControl                 // Adjust fan speed
    TimerControl                    // Set timer for operations
    ToggleSwitch                    // Toggle AC on or off
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

### 4. **ModeSelector Component**
> Dropdown for selecting AC modes.

```jsx
ModeSelector {
    Select (options: ["Cool", "Heat", "Fan", "Auto"])   // Mode selection
}
```

### 5. **FanSpeedControl Component**
> Allows users to select different fan speed levels.

```jsx
FanSpeedControl {
    Button (Low)                                        // Set fan to low
    Button (Medium)                                     // Set fan to medium
    Button (High)                                       // Set fan to high
}
```

### 6. **TimerControl Component**
> Setup and manage timers for AC operations.

```jsx
TimerControl {
    Input (startTime)                                   // Set start time
    Input (endTime)                                     // Set end time
    Button (Save Timer)                                 // Save timer settings
}
```

### 7. **StatusDisplay Component**
> Display real-time status of the air conditioner.

```jsx
StatusDisplay {
    Icon (status)                                       // Display on/off status icon
    Text (temperature)                                  // Show current temperature
}
```

---

This structure and pseudocode ensure clarity in how each component interacts while maintaining a clean and scalable architecture. If you need more details for any specific component logic, let me know! 🚀

