# Test Your Integration

Make sure that you've complete the previous steps on SDK integration prior to testing.

## Step 1: Debug Mode

Test ads with iOS Simulator at this stage.

If everything's done correctly you should be able to display ads with Test mode label, for example:

<p align="center">
<img src="https://github.com/nextmillenniummedia/inapp-ios-example/blob/main/docs/images/test_ads_banner.png" height="480">
</p>

For the next step you'll be required to enable a flag when initialize SDK which would signal SDK to serve test ads while in **Release** build.

Enabling a flag is required, since if we don't get a signal we won't be able to serve test ads on each request made.

```swift
InApp.shared.start(onTestMode: true)
```

**Important:** For iOS 14+ you need also give access to IDFA so we can generate device ID based on it. Learn about IDFA and how to obtain in from [Apple documentation](https://developer.apple.com/documentation/apptrackingtransparency).

## Step 2: TestFlight

### App-ads.txt

By the time testing, `app-ads.txt` **must** be added into your developer website, for example: `example.com/app-ads.txt`

Please, contact your account manager (*support@nextmillennium.io*) so you'll be provided with a proper file to add.

This step is a **must** to start displaying ads.

### Test Integrated Ad Units

Just as in **Debug Mode** you should be able to see 100% of the implemented ads in your application with a **Test mode** label, however now you'll be able to test ads on physical devices.

If something's not working for you at this stage, don't hesitate and contact our support team.

Once you're sure that everything works as intended make sure to disable the test flag before the app release on SDK initialization:

```swift
InApp.shared.start(onTestMode: false)
```

or just

```swift
InApp.shared.start()
```

## Step 3: App Store

Once your ad is released keep researching for better spots for your ads.

For any questions, contact *support@nextmillennium.io*
