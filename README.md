# Flutter's Animated Icons Package

A Simple flutter example to use Animated Icons pack.

## Code

1. Create Stateful Widget with SingleTickerProviderStateMixin
```dart
import 'package:flutter/cupertino.dart';
import 'package:flutter/src/foundation/key.dart';
import 'package:flutter/src/widgets/framework.dart';

class HomePage extends StatefulWidget {
  const HomePage({Key? key}) : super(key: key);

  @override
  State<HomePage> createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> with SingleTickerProviderStateMixin{
  @override
  Widget build(BuildContext context) {
    return <Widget>;
  }
}
```
2. Create 3 Methods
```dart
  // create animation controller
  late AnimationController _animationController;
```

```dart
 // initialise the controller
  @override
  void initState() {
    super.initState();
    _animationController =
        AnimationController(vsync: this, duration: const Duration(seconds: 1));
  }
```

```dart
// method for on-tap
  bool videoPlaying = false;
  void _iconTapped() {
    if (videoPlaying == false) {
      _animationController.forward();
      videoPlaying = true;
    } else {
      _animationController.reverse();
      videoPlaying = false;
    }
  }
```
## Scaffold Widget
```dart
Scaffold(
      backgroundColor: Colors.deepPurple[300],
      appBar: AppBar(
        backgroundColor: Colors.deepPurple[200],
        title: const Text(
          "A N I M A T E D   I C O N S",
          style: TextStyle(fontWeight: FontWeight.bold),
        ),
        centerTitle: true,
      ),
      body: Center(
        child: GestureDetector(
          onTap: _iconTapped,
          child: AnimatedIcon(
            size: 150,
            icon: AnimatedIcons.play_pause,
            progress: _animationController,
          ),
        ),
      ),
    );
```

## Results
<p>
<img src="https://github.com/Vishwa-Karthik/AnimatedIcons-Flutter/blob/master/play_gif.gif" width=200 height=400 />
<img src="https://github.com/Vishwa-Karthik/AnimatedIcons-Flutter/blob/master/search_gif.gif" width=200 height=400 />
</p>
