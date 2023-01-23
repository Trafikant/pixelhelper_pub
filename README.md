# trafikant-pixel-helper-message

## Format of message
- The message must comply to JSON format.
- Attributes:
    - ```message``` (optional) - ```string```:  The content to be displayed to users in extension. If this field doesn't exist, or has an 
  empty value, the extension will interpret it as "No message"
    - ```expiredAt``` (optional) - ```string```:
       - The date until 23:59 AM of which the message is valid.   
       - Must be in this format ```YYYY-MM-DD```.
    - ```color``` (optional) - ```string```:
       - If no value is provided, the default value is "green".
       - Otherwise, the value provided should be in the lists of standard CSS colors listed here: https://www.w3.org/wiki/CSS/Properties/color/keywords
