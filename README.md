# KOPinCodeView
[![Version](https://img.shields.io/cocoapods/v/KOPinCodeView.svg?style=flat)](http://cocoapods.org/pods/KOPinCodeView)
[![License](https://img.shields.io/cocoapods/l/KOPinCodeView.svg?style=flat)](http://cocoapods.org/pods/KOPinCodeView)
[![Platform](https://img.shields.io/cocoapods/p/KOPinCodeView.svg?style=flat)](http://cocoapods.org/pods/KOPinCodeView)
## Installation
KOPinCodeView is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "KOPinCodeView"
```
### Objective-C
```objc 
#import <KOPinCodeView/KOPinCodeView.h> //in your controller's header file
``` 
### Swift
If you are using `use_frameworks!` in your Podfile, use this import:
```swift
import KOPinCodeView
```
## Usage
### In Objective-C
##### Init methods
#
```objc
//init PinCodeView with cout symbol
-(void)initPinWithCountView:(int)count;

//init PinCodeView with confirm or custom view
-(void)initPinViewWithConfirmPIN:(BOOL)confirm
                     countSymbol:(int)count
                      sizeSimbol:(CGSize)size
                        formView:(FormView)form;
```
##### Delegate methods KOPinCodeViewDelegate
#
```objc
// delegate method. Called when entered all simbols.
// it returned symbols array and string with all symbols.
- (void)pinDidEnterAllSymbol:(NSArray *)symbolArray string:(NSString*)pin;
```
##### Creating a Pin Code View 
###### Example code:
#
```objc
//1. init with frame
KOPinCodeView *pinCodeView = [[KOPinCodeView alloc]initWithFrame:CGRectMake(0, 0, self.view.frame.size.width, 65)];
//2. Add to you view
[self.view addSubview:pinCodeView];
//3. setting the delegate:
pinCodeView.delegate = self;
//or just add view in storyboard  
```
```objc
//and init PinCodeView with cout symbol example
[pinCodeView initPinWithCountView:4];
```
###### init PinCodeView with confirm example:
#
```objc
[self.pinCodeConfirmView initPinViewWithConfirmPIN:YES countSymbol:6 sizeSimbol:CGSizeMake(45, 45) formView:kCircle];
```

###### Pin Code View with confirm custom settings example:
#
```objc
//thickness view line
self.pinCodeConfirmView.lineDeep = 2.f;
//Color view line
self.pinCodeConfirmView.lineColor = kColor;
//Background color view in select state
self.pinCodeConfirmView.selectColor = [kColor colorWithAlphaComponent:0.5f];

//Text color UITextField
self.pinCodeConfirmView.symbolColor = kColor;
//Font UITextField
self.pinCodeConfirmView.symbolFont = [UIFont systemFontOfSize:14];

//UILabel show only initPinViewWithConfirmPIN:
//Text color Label
self.pinCodeConfirmView.titleColor = kColor;
//Font Label
self.pinCodeConfirmView.titleFont = [UIFont systemFontOfSize:14];
//Text Label - Default: "enter Pin code"
self.pinCodeConfirmView.enterPinString = @"Any text 1";
//Text Label - Default: "Confirm Pin code"
self.pinCodeConfirmView.confirmPinString = @"Any text 2";

//Create Confirm Pin Code
self.pinCodeConfirmView.confirm = NO;
//Secure Text - Default: YES
self.pinCodeConfirmView.secure = NO;
//Keyboard Type
self.pinCodeConfirmView.typeKeyboard = UIKeyboardTypeNumberPad;
```
## Author
Oleksandr Khymych, seth@khymych.com

## License
KOPinCodeView is available under the MIT license. See the LICENSE file for more info.
