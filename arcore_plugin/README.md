# arcore_plugin

A Flutter plugin for Android allowing to recongize images via ARCore 

## Features 
 # [x] Displaying live ARCamera Feed 
 # [x] Recognizing images via ARCore (for more information see: https://developers.google.com/ar/develop/c/augmented-images/)
 # [ ] Placing Objects



## Installation 

### Android 
* For Setup make sure you migrated your App to AndroidX 
* in app/build.gradle set minSdkVersion to 24 and compileSdkVersion 28 
```
 defaultConfig {
        ...     
        minSdkVersion 24    
        ...
    }
```
    and
```
android {
    compileSdkVersion 28
    ...
}

``` 


## Example 
```
import 'package:arcore_plugin/arcore_plugin.dart';
import 'package:flutter/material.dart';

void main() => runApp(MaterialApp(home: TextViewExample()));

class TextViewExample extends StatefulWidget {
  @override
  _TextViewExampleState createState() => _TextViewExampleState();
}

class _TextViewExampleState extends State<TextViewExample> {

  @override
  void initState() {
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    Size screenSize = MediaQuery.of(context).size;
    return Scaffold(
        backgroundColor: Colors.blue,
        appBar: AppBar(
          title: const Text('ArCoreViewExample'),
          backgroundColor: Colors.black,
          centerTitle: true,
        ),
        body: Center(
            child: Container(
                width: screenSize.width,
                height: screenSize.height,
                child: ArCoreView(
                  onArCoreViewCreated: _onTextViewCreated,
                ))));
  }

  void _onTextViewCreated(ArCoreViewController controller) {
    controller.getArCoreView();
  }
}

```



Note: This plugin is still under development, and some APIs might not be available yet. Feedback welcome and Pull Requests are most welcome!


