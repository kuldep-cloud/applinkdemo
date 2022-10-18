import 'img.png';

# applinkdemo

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [UniLink ](https://pub.dev/packages/uni_links)
- [get: ](https://pub.dev/packages/get)
- [fluttertoast: ](https://pub.dev/packages/fluttertoast)
- img.png for overall overview.
- /Users/kuldeepsingh/StudioProjects/applinkdemo/img.png

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.


Android Config


1.App link

App Links: This link requires a specified host, a hosted file (assetlinks.json), and it only works with the https scheme (https://your_host).
Here’s the App Link intent filter that you need to add to your AndroidManifest.xml file. You can change the host to your liking:

<!-- App Links -->
      <intent-filter android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.BROWSABLE" />
        <!-- Accepts URIs that begin with https://YOUR_HOST -->
        <data
          android:scheme="https"
          android:host="your domain name" />
      </intent-filter>

2.Deep link

Deep Links: This link doesn’t require a host, a hoster file, or any custom scheme.
It provides a way to utilize your app using URL: your_scheme://any_host. Here’s the Deep Link intent filter that you need to add to your AndroidManifest.xml.
You can also change the scheme and host:

<!-- Deep Links --> 
          
          <intent-filter>
            <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
          <!-- Accepts URIs that begin with YOUR_SCHEME://YOUR_HOST --> 
        <data android:scheme="myapp" android:host="open.my.app" /> 
        </intent-filter>


IOS CONFIG

3.universel link

Universal Links: These only work with the https scheme and require a specified host, entitlements, and a hosted file.
Similar to App Links in Android. You need to add or create a com.apple.developer.associated-domains entitlement,
either through Xcode or by editing the ios/Runner/Runner.entitlements file:

            <?xml version="1.0" encoding="UTF-8"?>
             <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
               <plist version="1.0">
             <dict>
              <!-- ... other keys -->
            <key>com.apple.developer.associated-domains</key>
            <array>
             <string>applinks:[YOUR_HOST]</string>
          </array>
             <!-- ... other keys -->
          </dict>
         </plist>

4.custom url schemas

Custom URL: This URL doesn’t require a host, entitlements, a hosted file, or any custom scheme.
Similar to a Deep Link in Android, you need to add the host and scheme in the ios/Runner/Info.plist file as below:

    <key>CFBundleURLTypes</key>
     <array>
      <dict>
          <key>CFBundleTypeRole</key>
          <string>Editor</string>
          <key>CFBundleURLName</key>
          <string>unilinks.example.com</string>
          <key>CFBundleURLSchemes</key>
          <array>
              <string>logrckt</string>
          </array>
      </dict>
     </array>






