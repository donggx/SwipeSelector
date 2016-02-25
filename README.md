# SwipeSelector
A nicer-looking and more intuitive alternative for radio buttons and dropdowns for Android.

# Demo
<a href="https://play.google.com/store/apps/details?id=com.iroughapps.swipeselectordemo&utm_source=global_co&utm_medium=prtnr&utm_content=Mar2515&utm_campaign=PartBadge&pcampaignid=MKT-AC-global-none-all-co-pr-py-PartBadges-Oct1515-1"><img alt="Get it on Google Play" src="https://play.google.com/intl/en_us/badges/images/apps/en-play-badge-border.png" width="216" height="70"/></a>

<img src="https://raw.githubusercontent.com/roughike/SwipeSelector/master/swipeselector_demo.gif" width="278" height="492" />


## What and why?

Bored of dull looking radio buttons and dropdowns? Me too. I started looking for a more sophisticated way of offering user a choice, and came up with [this beautiful dribble](https://dribbble.com/shots/2343630-Create-Shipment).

Unfortunately, there were no ready-made solutions to achieve this, so I spent a good day working on this very thing I call SwipeSelector.

## Installation

**Gradle:**

```groovy
compile 'com.roughike:swipe-selector:1.0.1'
```

**Maven:**
```xml
<dependency>
  <groupId>com.roughike</groupId>
  <artifactId>swipe-selector</artifactId>
  <version>1.0.1</version>
  <type>pom</type>
</dependency>
```

## How do I use it?

The usage is really simple.

**First add SwipeSelector to your layout file:**

```xml
<com.roughike.swipeselector.SwipeSelector
    android:id="@+id/swipeSelector"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />
```

**Then get a hold of it and give it a set of SwipeItem objects with values, titles and descriptions:**

```java
SwipeSelector swipeSelector = (SwipeSelector) findViewById(R.id.swipeSelector);
swipeSelector.setItems(
  // The first argument is the value for that item, and should in most cases be unique for the
  // current SwipeSelector, just as you would assign values to radio buttons.
  // You can use the value later on to check what the selected item was.
  // The value can be any Object, here we're using ints.
  new SwipeItem(0, "Slide one", "Description for slide one."),
  new SwipeItem(1, "Slide two", "Description for slide two."),
  new SwipeItem(2, "Slide three", "Description for slide three.")
);
```

**Whenever you need to know what is the currently showing SwipeItem:**
```java
SwipeItem selectedItem = swipeSelector.getSelectedItem();

// The value is the first argument provided when creating the SwipeItem.
int value = selectedItem.value;

// for example
if (value == 0) {
  // The user selected slide number one.
}
```

For an example project using multiple SwipeSelectors, [refer to the sample app](https://github.com/roughike/SwipeSelector/tree/master/sample/src/main).

## Customization

```xml
<com.roughike.swipeselector.SwipeSelector
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/conditionSelector"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:swipe_indicatorSize="10dp"
    app:swipe_indicatorMargin="12dp"
    app:swipe_indicatorInActiveColor="#DDDDDD"
    app:swipe_indicatorActiveColor="#FF00FF" />
```

**Attribute explanations**

* **swipe_indicatorSize** the size for the circle indicators.
* **swipe_indicatorMargin** how far the indicators are from each other.
* **swipe_indicatorInActiveColor** the color for normal unselected indicators.
* **swipe_indicatorActiveColor** the color for selected indicator.


## Apps using SwipeSelector

Contact me at iiro.krankka@gmail.com to get a shoutout!

## minSDK Version

The lowest supported SDK version is currently 14.

## Contributions

Feel free to create issues / pull requests.

## Known issues

* Doesn't hold state on orientation change properly.

## License

```
SwipeSelector library for Android
Copyright (c) 2016 Iiro Krankka (http://github.com/roughike).

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
