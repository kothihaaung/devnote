# Developer Note

## Markdown help
[Basic format](https://help.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax)  
[Code block](https://help.github.com/en/github/writing-on-github/creating-and-highlighting-code-blocks)  
[Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

## Auto Layout
```swift
let guide = view.safeAreaLayoutGuide
closeButton.translatesAutoresizingMaskIntoConstraints = false
closeButton.widthAnchor.constraint(equalToConstant: 40).isActive = true
closeButton.heightAnchor.constraint(equalToConstant: 40).isActive = true
closeButton.topAnchor.constraint(equalTo: guide.topAnchor, constant: 20).isActive = true
closeButton.trailingAnchor.constraint(equalTo: guide.trailingAnchor, constant: -20).isActive = true
```
