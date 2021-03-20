#针对 RN 0.63 + 的 BUG 作者迟迟没更新

****索性亲自动手风衣足食

### 组件 `react-native-spring-scrollview` `这个组件 的BUG`
```
error: Error: Unable to resolve module 'react-native/lib/TextInputState' from 'node_modules/react-native-spring-scrollview/SpringScrollView.js': react-native/lib/TextInputState could not be found within the project'
```
#
```
解决方法：https://github.com/bolan9999/react-native-largelist/issues/369
在node文件夹中找到react-native-spring-scrollview中的SpringScrollView.js修改下面的TextInputState
-import * as TextInputState from "react-native/lib/TextInputState";
+import * as TextInputState from "react-native/Libraries/Components/TextInput/TextInputState";å
```

另外一个 BUG   是我在 RN 0.64+ iOS 调试中遇见的
修改了 STSpringScrollView.m  的 头文件引用
```
// #import "STSpringScrollView.h"
#import <React/RCTEventDispatcher.h>
#import <RNSpringScrollView/STSpringScrollView.h>
```
