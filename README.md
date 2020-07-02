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

## Image size in pixel
```swift
To get size in pixels of UIImageView:

let widthInPixels = imageView.frame.width * UIScreen.mainScreen().scale
let heightInPixels = imageView.frame.height * UIScreen.mainScreen().scale
To get size in pixels of UIImage:

let widthInPixels = image.size.width * image.scale
let heightInPixels = image.size.height * image.scale
```

## UICollectionView left align
```swift
self.flowLayout.estimatedItemSize = UICollectionViewFlowLayout.automaticSize

class LeftAlignedCollectionViewFlowLayout: UICollectionViewFlowLayout {

    override func layoutAttributesForElements(in rect: CGRect) -> [UICollectionViewLayoutAttributes]? {
        let attributes = super.layoutAttributesForElements(in: rect)

        var leftMargin = sectionInset.left
        var maxY: CGFloat = -1.0
        attributes?.forEach { layoutAttribute in
            if layoutAttribute.frame.origin.y >= maxY {
                leftMargin = sectionInset.left
            }

            layoutAttribute.frame.origin.x = leftMargin

            leftMargin += layoutAttribute.frame.width + minimumInteritemSpacing
            maxY = max(layoutAttribute.frame.maxY , maxY)
        }

        return attributes
    }
}
```
