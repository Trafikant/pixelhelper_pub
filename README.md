# trafikant-pixel-helper-message

## Format of message
- The message must comply to JSON format.
- There should be **NO** redundant comma character (,) after attributes' value. Otherwise the extension's fetch will consider it invalid and thus can't properply parse it.
    - For exampe: {"x": "y",} is invalid
- Schema
```
export interface CloudMessage {
    message: string,
    // if expiredAt is undefined, that mean a forever message
    expiredAt?: number,
    color?: string
}

export interface CloudData {
    messages: {
        // Msg at the top Right
        topRightMessage?: CloudMessage,
        // Bottom message
        bottomMessage?: CloudMessage,
    }
}```

- Attributes explanation:
    - ```messages``` (optional) - ```string```:  The content to be displayed to users in extension. If this field doesn't exist, or has an empty value, the extension will interpret it as "No message"
    - ```expiredAt``` (optional) - ```string```:
       - The date until 23:59 AM of which the message is valid.   
       - if undefined, that mean a forever message
       - Must be in this format ```YYYY-MM-DD```.
    - ```color``` (optional) - ```string```:
       - If no value is provided, the default value is "green".
       - Otherwise, the value provided should be in the lists of standard CSS colors listed here: https://www.w3.org/wiki/CSS/Properties/color/keywords

- Sample values
```
   "messages": {
      "topRightMessage": {
          "message": "Message:<a target='blank' href='https://trafikant.pro'>link</a> - test edit at github",
          "expiredAt": "2025-01-30"
      },
      "bottomMessage": {
          "message": "Message:<a target='blank' href='https://trafikant.pro'>link</a> - test edit at github",
          "expiredAt": "2025-01-30"
      }
   }
```
