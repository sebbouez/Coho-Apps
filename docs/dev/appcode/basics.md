# The basics of AppCode

AppCode uses Javascript syntax with modules style of coding.  
This approach allows for better organization and maintainability of the codebase.  

## Example

```javascript
import { ui } from 'core';

export function UserFunction(){
    const bridge = new AppCodeBridgeBase();
    bridge.Log('Hello World');
}

```