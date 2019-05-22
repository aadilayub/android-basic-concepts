#### Concepts to Revise:

- Activity Lifecycle
- ~~ViewGroups~~
- ~~RelativeLayout~~
- ~~LinearLayout~~
- Styles
- Fragments
- MediaPlayers and AudioFocus
- Activities
- Contexts
- ArrayAdapter
- Intents

# Android UI Overview

The user interface (UI) that appears on the screen of an Android device consists of a hierarchy of objects called *views* - every element of the screen is a `View` . The `View` class represents the basic building block for all UI components, and the base class for classes that provide interactive UI components such as buttons, checkboxes, and text entry fields. Commonly used `View` subclasses include: 

- `TextView` for displaying text.
- `EditText` to enable the user to enter and edit text.
- `Button` and other clickable elements (such as `RadioButton`, `Checkbox`, and `Spinner`) to provide interactive behavior.
- `ScrollView` and `RecyclerView` to display scrollable items.
- `ImageView` for displaying images.
- `ConstraintLayout` and `LinearLayout` for containing other `View` elements and positioning them.



The Java code that displays and drives the UI is contained in a class that extends `Activity`. An `Activity` is usually associated with a layout of UI views defined as an XML (eXtended Markup Language) file. This XML file is usually named after its `Activity` and defines the layout of `View` elements on the screen.

For example, the `MainActivity` code in the [Hello World](https://codelabs.developers.google.com/codelabs/android-training-hello-world/index.html?index=..%2F..%2Fandroid-training#0) app displays a layout defined in the `activity_main.xml` layout file, which includes a `TextView` with the text "Hello World".

 In more complex apps, an activity might implement actions to respond to user taps, draw graphical content, or request data from a database or the Internet.



# Views and Layouts

A layout defines a single UI in your app. In Android, all UIs are built using a heirarchy of `View` and `ViewGroup` objects. 

A `View` usually draws something the user can see and interact with like a `TextView`, `ImageView` , or `Button`, whereas a `ViewGroup` is an invisible container that defines a layout structure for other `View` and `ViewGroup` objects. 

Examples of `ViewGroup`s are `LinearLayout`, `RelativeLayout`, and `ConstraintLayout`.

## LinearLayout

In a `LinearLayout`, like the name suggests, all the elements are displayed in a single direction either vertically or horizontally, and this behavior is specified in the `android:orientation` attribute.

#### Positioning

`LinearLayout` is required to have these attributes set:

- `android:layout_width`
- `android:layout_height`
- `android:orientation`



Other layout-related attributes include:

- `android:layout_gravity`: This attribute is used with a  UI element to control where the element is arranged within its parent.  For example, the following attribute centers the UI element horizontally  within the parent `ViewGroup`:

```java
android:layout_gravity="center_horizontal"
```

#### 

- `android:layout_weight`: This is useful for equally (or proportionally) spacing out views in a layout. To space out views equally set their height or width to 0dp, and assign each view a layout weight of 1. A related value is `android:weightsum`. Let's say you want to proportionally space out two views. You could set weightsum to 4, and set the layout weight of the views to 3 and 1 respectively. This will make on view take up 75% of the space, and the other one 25%.

## RelativeLayout

Another useful `ViewGroup` for layout is `RelativeLayout`, which you can use to position child `View` elements relative to each other or to the parent. The attributes you can use with `RelativeLayout` include the following:

- [`android:layout_toLeftOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_toLeftOf): Positions the right edge of this `View` to the left of another `View` (identified by its `ID`). 
- [`android:layout_toRightOf`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_toRightOf): Positions the left edge of this `View` to the right of another `View` (identified by its `ID`).
- [`android:layout_centerHorizontal`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_centerHorizontal): Centers this `View` horizontally within its parent. 
- [`android:layout_centerVertical`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_centerVertical): Centers this `View` vertically within its parent.
- [`android:layout_alignParentTo`p](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_alignParentTop): Positions the top edge of this `View` to match the top edge of the parent.
- [`android:layout_alignParentBottom`](https://developer.android.com/reference/android/widget/RelativeLayout.LayoutParams.html#attr_android:layout_alignParentBottom): Positions the bottom edge of this `View` to match the bottom edge of the parent.

## ConstraintLayout

## Style-related attributes

You specify style attributes to customize the appearance of a `View`. A `View` that *doesn't* have style attributes, such as `android:textColor`, `android:textSize`, and `android:background`, takes on the styles defined in the app's theme.

The following are common style-related attributes:

- `android:background`: Specifies a color or drawable resource to use as the background.
- `android:text`: Specifies the text to display in the view.
- `android:textColor`: Specifies the text color.
- `android:textSize`: Specifies the text size.
- `android:textStyle`: Specifies the text style, such as `bold`.