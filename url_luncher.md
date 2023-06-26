# flutter url luncher:

- [ ]  First you should add the url lucher in 'pubspec.yaml' File. Under the ``` dependencies: ``` section:

```
url_launcher: ^6.0.0
```

- [ ] The edit the 'main.dart' file.

```import 'package:flutter/material.dart';
import 'package:url_launcher/url_launcher.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Open Website',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  final String websiteUrl = 'https://gamesbazarbd.com';

  @override
  void initState() {
    super.initState();
    _openWebsite();
  }

  Future<void> _openWebsite() async {
    if (await canLaunch(websiteUrl)) {
      await launch(websiteUrl);
    } else {
      throw 'Could not launch $websiteUrl';
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Text('Loading ...'),
      ),
    );
  }
}

```
