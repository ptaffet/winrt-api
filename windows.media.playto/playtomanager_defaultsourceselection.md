---
-api-id: P:Windows.Media.PlayTo.PlayToManager.DefaultSourceSelection
-api-type: winrt property
---

<!-- Property syntax
public bool DefaultSourceSelection { get;  set; }
-->

# Windows.Media.PlayTo.PlayToManager.DefaultSourceSelection

## -description
Enables or disables the default source selection for Play To.

## -property-value
True to enable default source selection; otherwise false. The default is true.

## -remarks

An app that contains media elements has Play To enabled by default. If a user invokes the **Devices** charm while running the app and selects a target device to stream media to, Play To will stream the media from the first audio, video, or image element on the current page. You can disable this default behavior by setting the **DefaultSourceSelection** property to **false**.
```javascript
var ptm = Windows.Media.PlayTo.PlayToManager.getForCurrentView();
ptm.defaultSourceSelection = false;

```



You can exclude individual HTML elements from the default Play To behavior by adding the **-ms-playToDisabled** attribute in your HTML markup.
```javascript
<video src="http://www.example.com/videos/video.mp4" x-ms-playToDisabled/>
```




<!--What about XAML exclusion attribute?-->

## -examples

## -see-also
[Play To sample](http://go.microsoft.com/fwlink/p/?linkid=245166), [PlayToReceiver sample](http://go.microsoft.com/fwlink/p/?linkid=245167), [Media Server sample](http://go.microsoft.com/fwlink/p/?linkid=245168)