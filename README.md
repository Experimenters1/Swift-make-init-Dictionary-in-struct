# Swift-make-init-Dictionary-in-struct
Swift make init Dictionary in struct
### 

```swift

import Foundation

struct ChatUser {
    var id: String
    let uid: String
    let email: String
    let profileImageUrl: String

    init(data: [String: Any]) {
        self.id = data["id"] as? String ?? ""
        self.uid = data["uid"] as? String ?? ""
        self.email = data["email"] as? String ?? ""
        self.profileImageUrl = data["profileImageUrl"] as? String ?? ""
    }
}
```
```swift
import UIKit

class YourViewController: UIViewController {
    // Sử dụng ChatUser ở đây
    var user: ChatUser?
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        // Khởi tạo một đối tượng ChatUser từ dữ liệu
        let userData: [String: Any] = [
            "id": "12345",
            "uid": "user123",
            "email": "user@example.com",
            "profileImageUrl": "https://example.com/user.png"
        ]
        
        user = ChatUser(data: userData)
        
        // Bây giờ bạn có thể sử dụng biến user.id, user.uid, user.email, user.profileImageUrl ở đây
    }
}
```

### 
```swift
import Foundation

class ChatUser {
    var id: String { uid }
    
    let uid, email, profileImageUrl: String
    
    init(data: [String: Any]) {
        self.uid = data["uid"] as? String ?? ""
        self.email = data["email"] as? String ?? ""
        self.profileImageUrl = data["profileImageUrl"] as? String ?? ""
    }
    
    static let shared = ChatUser(data: [:]) // Initialize with default values or customize as needed
}
```
```swift

let currentUser = ChatUser.shared
let userID = currentUser.id
let userEmail = currentUser.email
let profileImageURL = currentUser.profileImageUrl

// Sử dụng userID, userEmail và profileImageURL theo nhu cầu
```
