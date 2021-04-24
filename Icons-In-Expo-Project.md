# Icons as a part of great user experience
Icons are an essential part of many user interfaces, visually expressing objects, actions and ideas. When done correctly, they communicate the core idea and intent of a product or action, and they bring a lot of nice benefits to user interfaces, such as saving screen real estate and enhancing aesthetic appeal.

## @expo/vector-icons
This library is installed by default on the template project that get through expo init -- it is part of the expo package. It includes popular icon sets and you can browse all of the icons using icons.expo.fyi.

```
import * as React from 'react';
import { View, StyleSheet } from 'react-native';
import { Ionicons } from '@expo/vector-icons';

export default function App() {
return (
    <View style={styles.container}>
    <Ionicons name="md-checkmark-off-circle" color="green" />
    </View>
    );
}
```
This component loads the Ionicons font if it hasn't been loaded already, and returns a checkmark icon that I found through the vector-icons directory mentioned above. @expo/vector-icons is built on top of react-native-vector-icons and uses a similar API.

By Giving a name to an icon inside Ionicons tag and importing it to our Project file, we can be able to use Icons in our application.

Note: Cheatsheet for IonIcons you can go to this link. [Click](https://ionicons.com/v4/cheatsheet.html).