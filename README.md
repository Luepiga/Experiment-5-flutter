# Experiment-5-flutter
EXPERIMENT 5 – IMPLEMENTATION OF NAVIGATION AND ROUTING
Aim: To implement navigation between multiple screens in a Flutter application using named routes.
Step 1 – Create Flutter project
1. Open VS Code.
2. Click Terminal → New Terminal.
3. Type the following commands one by one:
flutter create navigation_app
cd navigation_app
code .


Step 2 – Open main.dart
1. Open the lib folder.
2. Click main.dart.
3. Delete all existing code.
4. Paste the following code.
Step 3 – Write the Flutter program
File: lib/main.dart

import 'package:flutter/material.dart';

void main() => runApp(const MaterialApp(
  home: HomePage(),
  routes: {
    '/profile': (c) => const ProfilePage(),
    '/details': (c) => const DetailsPage(),
  },
));

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) => Scaffold(
    appBar: AppBar(title: const Text('Home')),
    body: Center(child: ElevatedButton(
      onPressed: () => Navigator.pushNamed(context, '/profile'),
      child: const Text('Go to Profile'),
    )),
  );
}

class ProfilePage extends StatelessWidget {
  const ProfilePage({super.key});

  @override
  Widget build(BuildContext context) => Scaffold(
    appBar: AppBar(title: const Text('Profile')),
    body: Center(child: ElevatedButton(
      onPressed: () => Navigator.pushNamed(context, '/details'),
      child: const Text('View Details'),
    )),
  );
}

class DetailsPage extends StatelessWidget {
  const DetailsPage({super.key});

  @override
  Widget build(BuildContext context) => Scaffold(
    appBar: AppBar(title: const Text('Details')),
    body: Center(child: ElevatedButton(
      onPressed: () => Navigator.pop(context),
      child: const Text('Back'),
    )),
  );
}



Step 4 – Save the program
Press:
Ctrl + S


Step 5 – Get packages
In the VS Code terminal, type:
flutter pub get


Step 6 – Check available devices
flutter devices


Select Chrome or an Android emulator.
Step 7 – Run the application
flutter run
