ReadabilityActivity
===================

ReadabilityActivity is a UIActivity class for launching and adding articles to the Readability iOS app.

iOS 6 introduced the "share sheet"—a simple native interface to launch actions. We've created a custom UIActivity that you can integrate into your app. Simply import the ReadabilityActivity class and icons to your project and wire it up:

```objective-c
// init Readability activity
ReadabilityActivity *rdb = [[ReadabilityActivity alloc] init];

NSURL *url = [NSURL URLWithSting:@"http://example.com"];

// set up activity item / action
NSArray *activityItems = @[url];

// init share sheet with app-specific activity
UIActivityViewController *shareSheet = [[UIActivityViewController alloc] initWithActivityItems:activityItems applicationActivities:@[rdb]];

// present the view controller, animated.
[self presentViewController:shareSheet
animated:YES
completion:^{
}];
```

The ReadabilityActivity class also includes an easy way to check that Readability is installed on a device. This method returns YES if the user is running Readability 1.2.2 or newer:

```objective-c
[ReadabilityActivity canPerformActivity]
```
