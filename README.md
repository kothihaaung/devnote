# Developer Note
## Auto Layout
```swift
let guide = view.safeAreaLayoutGuide
closeButton.translatesAutoresizingMaskIntoConstraints = false
closeButton.widthAnchor.constraint(equalToConstant: 40).isActive = true
closeButton.heightAnchor.constraint(equalToConstant: 40).isActive = true
closeButton.topAnchor.constraint(equalTo: guide.topAnchor, constant: 20).isActive = true
closeButton.trailingAnchor.constraint(equalTo: guide.trailingAnchor, constant: -20).isActive = true
```
