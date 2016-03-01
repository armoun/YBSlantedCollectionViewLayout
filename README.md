# YBSlantedCollectionViewLayout

[![Version](https://img.shields.io/cocoapods/v/YBSlantedCollectionViewLayout.svg?style=flat)](http://cocoapods.org/pods/YBSlantedCollectionViewLayout)
[![License](https://img.shields.io/cocoapods/l/YBSlantedCollectionViewLayout.svg?style=flat)](http://cocoapods.org/pods/YBSlantedCollectionViewLayout)
[![Platform](https://img.shields.io/cocoapods/p/YBSlantedCollectionViewLayout.svg?style=flat)](http://cocoapods.org/pods/YBSlantedCollectionViewLayout)

## Overview
YBSlantedCollectionViewLayout is a subclass of UICollectionViewLayout allowing the display of slanted content on UICollectionView.

<p align="center" >
  
	<img src="./Screenshots/YBSlantedCollectionViewLayout.gif" alt="YBSlantedCollectionViewLayout" title="YBSlantedCollectionViewLayout">

</p>

## Usage

YBSlantedCollectionViewLayout contains six properties to customize the interface.

```swift
var slantingDelta: UInt
var reverseSlantingAngle: Bool
var firstCellSlantingEnabled: Bool
var lastCellSlantingEnabled: Bool
var lineSpacing: CGFloat
var scrollDirection: UICollectionViewScrollDirection
```

- _slantingDelta_ is the slanting delta.  Defaults to 50
- _reverseSlantingAngle_ allows to reverse the slanting angle if the value is `true`. By default, this property is set to `false`
- _firstCellSlantingEnabled_ allows to enable the slanting for the first cell. By default, this property is set to `true`
- _lastCellSlantingEnabled_ allows to enable the slanting for the last cell. By default, this property is set to `true`
- _lineSpacing_ is the spacing to use between two items. Defaults to 10.0
- _scrollDirection_ is the scroll direction. Defaults to `UICollectionViewScrollDirectionVertical`

### Apply the slanting mask 

To apply the slanting mask on the cellView, call the `applyMaskToCellView` method like the following example:                         

```swift
func collectionView(collectionView: UICollectionView,
  	 cellForItemAtIndexPath indexPath: NSIndexPath) -> UICollectionViewCell {

	let cell = collectionView.dequeueReusableCellWithReuseIdentifier(reuseIdentifier, forIndexPath: indexPath) as! CustomCollectionCell

	// do something 

	// Apply the mask
	let layout = collectionView.collectionViewLayout as! YBSlantedCollectionViewLayout
	layout.applyMaskToCellView(cell, forIndexPath: indexPath)

	return cell
}
```


## Installation

YBSlantedCollectionViewLayout is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "YBSlantedCollectionViewLayout", '~> 1.0'
```

## Todo
- [] Carthage support
- [] Improve the attribution of the clic
- [] Tests

## Author

[Yassir Barchi](https://linkedin.com/in/yassir-barchi-318a7949)

## Acknowledgement

This framework is inspired by [this prototype](https://dribbble.com/shots/1727594-Slanted-Table-Cells-With-Parallax?_=1456679145403) released by [Matt Bridges](https://dribbble.com/rrridges).


## License

YBSlantedCollectionViewLayout is available under the MIT license. See the LICENSE file for more info.
