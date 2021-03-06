---
-api-id: M:Windows.UI.WebUI.ActivatedOperation.GetDeferral
-api-type: winrt method
---

<!-- Method syntax
public Windows.UI.WebUI.ActivatedDeferral GetDeferral()
-->

# Windows.UI.WebUI.ActivatedOperation.GetDeferral

## -description
Requests that the completion of app activation be delayed.

## -returns
The activation deferral object.

## -remarks
When an app starts, the system displays its splash screen until the app indicates that it is ready to display its UI by returning from its activation handler. The app has several seconds to set up its state and initial UI. The UI for the app is displayed to the user when the app returns from its activation handler. However, some apps need to start asynchronous operations to retrieve state information and set up their UI (like using fragment loading to display app pages). Apps that must complete activation asynchronously can get a deferral object from the activation event arguments. This object enables the app to complete activation outside its handler. When the app acquires the deferral object, its activation is not completed when the activation handler returns.

An app can complete activation after its required asynchronous operations complete and it is ready to display its UI. App activation is delayed until the app calls the [ActivatedDeferral.complete](activateddeferral_complete_1807836922.md) method.

Requesting a deferral enables an app to display its static splash screen for up to 15 seconds. If the app hasn't completed activation after 15 seconds, the system considers the app hung and will terminate it if the user navigates away from the splash screen.

Note that in normal circumstances and app should take no more than a few seconds to finish activation. If your app requires more than 3 or 4 seconds to restore state and prepare its UI, then you should finish activation and display an [extended splash screen](http://msdn.microsoft.com/library/fd10a9ff-4e09-471f-886e-8b8246dc12de) screen until your app is ready.

## -examples

## -see-also
[App lifecycle](http://msdn.microsoft.com/library/6c469e77-f1e3-4859-a27b-c326f9616d10), [How to extend the splash screen](http://msdn.microsoft.com/library/fd10a9ff-4e09-471f-886e-8b8246dc12de), [ActivatedDeferral](activateddeferral.md), [App activated, resume, and suspend using the WRL sample](http://go.microsoft.com/fwlink/p/?linkid=226722)