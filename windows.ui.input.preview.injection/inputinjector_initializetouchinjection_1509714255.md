---
-api-id: M:Windows.UI.Input.Preview.Injection.InputInjector.InitializeTouchInjection(Windows.UI.Input.Preview.Injection.InjectedInputVisualizationMode)
-api-type: winrt method
---

<!-- Method syntax
public void InitializeTouchInjection(Windows.UI.Input.Preview.Injection.InjectedInputVisualizationMode visualMode)
-->

# Windows.UI.Input.Preview.Injection.InputInjector.InitializeTouchInjection

## -description
Initializes a virtual touch device that can synthesize input events and provide corresponding input data to the system. 

## -parameters

### -param visualMode

The type of visual feedback displayed for touch input injection.

## -remarks

> [!Important]
> The APIs in this namespace require the inputInjectionBrokered [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities).

Using input injection requires the following be added to the Package.appxmanifest:

- To `<Package>`
    - `xmlns:rescap="http://schemas.microsoft.com/appx/manifest/foundation/windows10/restrictedcapabilities"`
    - `IgnorableNamespaces="rescap"`
- To `<Capabilities>`
    - `<rescap:Capability Name="inputInjectionBrokered" />`


## -examples

## -see-also

### Reference

[UninitializeTouchInjection](inputinjector_uninitializetouchinjection_1885359186.md)

### Conceptual

[Gaze interactions and eye tracking in UWP apps](https://docs.microsoft.com/windows/uwp/design/input/gaze-interactions)

### Samples

- [Simulate user input through input injection](https://review.docs.microsoft.com/windows/uwp/design/input/input-injection?branch=kbridge-inputinjection)
- [Input injection sample (mouse to touch)](https://github.com/MicrosoftDocs/windows-topic-specific-samples/archive/uwp-input-injection-mouse-to-touch.zip)
- [Touch injection sample](http://go.microsoft.com/fwlink/p/?LinkID=267906)
- [Input: XAML user input events sample](http://go.microsoft.com/fwlink/p/?linkid=226855)
