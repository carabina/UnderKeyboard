## Move scroll view content from under the keyboard on iOS/Swift

[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)][carthage]
[![CocoaPods Version](https://img.shields.io/cocoapods/v/UnderKeyboard.svg?style=flat)][cocoadocs]
[![License](https://img.shields.io/cocoapods/l/UnderKeyboard.svg?style=flat)][cocoadocs]
[![Platform](https://img.shields.io/cocoapods/p/UnderKeyboard.svg?style=flat)][cocoadocs]
[cocoadocs]: http://cocoadocs.org/docsets/UnderKeyboard
[carthage]: https://github.com/Carthage/Carthage

This is a helper function that moves scroll view content from under the keyboard on iOS.

## What's the problem?

Suppose we have a scroll view or a text view, or a table view on iOS screen. That scroll view stretches all the way down to the bottom of the screen. If virtual keyboard appears it is shown over the scroll view content. The problem is there is no way for users to see the bottom of the scroll view content because is it obscured by the keyboard.

## Solution

When virtual keyboard is shown we can adjust the bottom inset of the scroll view by the height of the keyboard.

<img src="https://raw.githubusercontent.com/exchangegroup/UnderKeyboard/master/Graphics/under_the_keyboard_ios.png" alt="Move scroll view content from under the keyboard in iOS/Swift" width="640" />

## Setup

There are three ways you can add UnderKeyboard to your project.

**Add source (iOS 7+)**

Simply add [UnderKeyboard.swift](https://github.com/exchangegroup/UnderKeyboard/blob/master/UnderKeyboard/UnderKeyboard.swift) into your project.

**Setup with Carthage (iOS 8+)**

Alternatively, add `github "exchangegroup/UnderKeyboard" ~> 1.0` to your Cartfile and run `carthage update`.

**Setup with CocoaPods (iOS 8+)**

If you are using CocoaPods add this text to your Podfile and run `pod install`.

    use_frameworks!
    pod 'UnderKeyboard', '~> 1.0'


## Usage

Call `UnderKeyboard.scrollView` function before keyboard is shown. It can be done in `viewDidLoad`.


```Swift
UnderKeyboard.scrollView(scrollView)
```

**Note**: One can also use `UITextView` and `UITableView` objects or other subclasses of `UIScrollView`.

### Account for bottom layout guide

If your view controller has a tab bar you can supply its bottom layout guide. Its height will be taken into account during inset calculation.

```Swift
UnderKeyboard.scrollView(scrollView, bottomLayoutGuide: bottomLayoutGuide)
```


## Reference

[Managing Keyboard](https://developer.apple.com/library/ios/documentation/StringsTextFonts/Conceptual/TextAndWebiPhoneOS/KeyboardManagement/KeyboardManagement.html)

## License

UnderKeyboard is released under the [MIT License](LICENSE).
