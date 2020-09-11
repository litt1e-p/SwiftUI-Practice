# SwiftUI Practice

## 1. Observerable

### 1.1  Data binding

> the role of a binding: A binding controls the storage for a value, so you can pass data around to different views that need to read or write it.


- `environmentObject(_:)`:  modifier that use as an observer and passes the data downward in the view hierarchy
- `@EnvironmentObject`: attribute in the view hierarchy  that use as a watcher to receive the data from views that are higher up

eg.

// Observable Object
```swift
import Foundation
import Combine

final class UserData: ObservableObject {
    @Published var showFavoritesOnly = false
    @Published var landmarks = landmarkData
}

```

// Data Binding
```swift
LandmarkDetail().environmentObject(UserData())
```

// Watcher
```swift
struct LandmarkDetail: View {
    @EnvironmentObject var userData: UserData
}
```




