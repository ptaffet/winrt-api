---
-api-id: T:Windows.Storage.ApplicationDataCompositeValue
-api-type: winrt class
---

<!-- Class syntax.
public class ApplicationDataCompositeValue : Windows.Foundation.Collections.IIterable<Windows.Foundation.Collections.IKeyValuePair<System.String, System.Object>>, Windows.Foundation.Collections.IMap<System.String, System.Object>, Windows.Foundation.Collections.IObservableMap<System.String, System.Object>, Windows.Foundation.Collections.IPropertySet
-->

# Windows.Storage.ApplicationDataCompositeValue

## -description
Represents related app settings that must be serialized and deserialized atomically.

## -remarks
A composite setting is serialized by inserting it into a settings map and deserialized by looking it up from the map.

### Collection member lists

For JavaScript, [ApplicationDataCompositeValue](applicationdatacompositevalue.md) supports using an index to access items.

## -examples
This example creates and reads a composite setting named `exampleCompositeSetting`.

Call the [Remove | remove](applicationdatacompositevalue_remove_1498489487.md) method to delete the `exampleCompositeSetting` setting when you have finished with it.

```csharp
Windows.Storage.ApplicationDataContainer localSettings = Windows.Storage.ApplicationData.Current.LocalSettings;

// Create a composite setting

Windows.Storage.ApplicationDataCompositeValue composite = new Windows.Storage.ApplicationDataCompositeValue();
composite["intVal"] = 1;
composite["strVal"] = "string";

localSettings.Values["exampleCompositeSetting"] = composite;

// Read data from a composite setting

Windows.Storage.ApplicationDataCompositeValue composite = 
   (Windows.Storage.ApplicationDataCompositeValue)localSettings.Values["exampleCompositeSetting"];

if (composite == null)
{
   // No data
}
else
{
   // Access data in composite["intVal"] and composite["strVal"]
}

// Delete a composite setting

localSettings.Values.Remove("exampleCompositeSetting");
```

```cppwinrt
Windows::Storage::ApplicationDataContainer localSettings{
    Windows::Storage::ApplicationData::Current().LocalSettings() };
auto values{ localSettings.Values() };

{
    // Create a composite setting.
    Windows::Storage::ApplicationDataCompositeValue composite;
    composite.Insert(L"intVal", Windows::Foundation::PropertyValue::CreateInt32(1));
    composite.Insert(L"strVal", Windows::Foundation::PropertyValue::CreateString(L"string"));
    values.Insert(L"exampleCompositeSetting", composite);
}

{
    // Read data from a composite setting.
    Windows::Storage::ApplicationDataCompositeValue composite{ values.Lookup(L"exampleCompositeSetting").as<Windows::Storage::ApplicationDataCompositeValue>() };
    if (composite == nullptr)
    {
        // No data
    }
    else
    {
        int32_t one{ winrt::unbox_value<int32_t>(composite.Lookup(L"intVal")) };
        winrt::hstring hello{ winrt::unbox_value<winrt::hstring>(composite.Lookup(L"strVal")) };
    }
}

// Delete a composite setting.
values.Remove(L"exampleCompositeSetting");
```

```cpp
ApplicationDataContainer^ localSettings = ApplicationData::Current->LocalSettings;

// Create a composite setting

ApplicationDataCompositeValue^ composite = ref new ApplicationDataCompositeValue();
composite->Insert("intVal", dynamic_cast<PropertyValue^>(PropertyValue::CreateInt32(1)));
composite->Insert("strVal", dynamic_cast<PropertyValue^>(PropertyValue::CreateString("string")));

auto values = localSettings->Values;
values->Insert("exampleCompositeSetting", composite);

// Read data from a composite setting

composite = safe_cast<ApplicationDataCompositeValue^>(localSettings->Values->Lookup("exampleCompositeSetting"));

if (composite == nullptr)
{
   // No data
}
else
{
   int one = safe_cast<IPropertyValue^>(composite->Lookup("intVal"))->GetInt32();
   String^ hello = safe_cast<String^>(composite->Lookup("strVal"));
}

// Delete a composite setting

values->Remove("exampleCompositeSetting");
```

```javascript
var applicationData = Windows.Storage.ApplicationData.current;

var localSettings = applicationData.localSettings;

// Create a composite setting

var composite = new Windows.Storage.ApplicationDataCompositeValue();
composite["intVal"] = 1;
composite["strVal"] = "string";

localSettings.values["exampleCompositeSetting"] = composite;

// Read data from a composite setting

var composite = localSettings.values["exampleCompositeSetting"];

if (!composite)
{
    // No data
}
else
{
    // Access data in composite["intVal"] and composite["strVal"]
}

// Delete a composite setting

localSettings.values.remove("exampleCompositeSetting");
```

```vb
Dim localSettings As Windows.Storage.ApplicationDataContainer = Windows.Storage.ApplicationData.Current.LocalSettings

' Create a composite setting

Dim composite As New Windows.Storage.ApplicationDataCompositeValue
composite("intVal") = 1
composite("strVal") = "string";

localSettings.Values("exampleCompositeSetting") = composite

' Read data from a composite setting

Dim composite As Windows.Storage.ApplicationDataCompositeValue = 
   CType(localSettings.Values("exampleCompositeSetting"), Windows.Storage.ApplicationDataCompositeValue)

If composite Is Nothing Then
   ' No data
Else
   ' Access data in composite("intVal") and composite("strVal")
End If

' Delete a composite setting

localSettings.Values.Remove("exampleCompositeSetting")
```

## -see-also
[Quickstart: Local application data (JavaScript)](http://msdn.microsoft.com/library/87dfe8e5-2d01-45cf-bcb1-25f54219a439), [Store and retrieve settings and other app data](http://msdn.microsoft.com/library/41676a02-325a-455e-8565-c9ec0bc3a8fe), [Quickstart: Roaming application data (JavaScript)](http://msdn.microsoft.com/library/60f40214-c201-4afe-a2f5-0ef3a7de0076), [Store and retrieve settings and other app data](http://msdn.microsoft.com/library/41676a02-325a-455e-8565-c9ec0bc3a8fe), [Store and retrieve settings and other app data](http://msdn.microsoft.com/library/41676a02-325a-455e-8565-c9ec0bc3a8fe), [ApplicationData](applicationdata.md), [ApplicationDataContainer](applicationdatacontainer.md), [ApplicationDataContainerSettings](applicationdatacontainersettings.md), [Application data sample](http://go.microsoft.com/fwlink/p/?linkid=231478), [Application data sample (Windows 10)](http://go.microsoft.com/fwlink/p/?LinkId=620486)