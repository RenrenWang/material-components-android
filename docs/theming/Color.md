<!--docs:
title: "Color Theming"
layout: detail
section: theming
excerpt: "Color Theming"
iconId: color
path: /theming/color/
-->

# Color Theming

The Material Design color theming system can be used to create a color scheme
that reflects your brand or style.

The Material Design color theming system uses an organized approach to applying
color to your UI. In this system, two theme colors are selected to express
different parts of a UI: a primary color and a secondary color. Material
components use these theme colors and their variations to style their individual
backgrounds, text, and more.

## Design & API Documentation

-   [Material Design guidelines:
    Color](https://material.io/go/design-color-theming/)
    <!--{: .icon-list-item.icon-list-item--spec }-->

## Using The Color Theming System

All Material Design components use a `Widget.MaterialComponents` style, and
these styles reference color attributes from the Material Design theme
(`Theme.MaterialComponents`). So, it is easy to re-color attributes across your
app by simply modifying the color attributes in your theme. These attributes
are:

Attribute Name         |Description                                                                                                 |Default Value
-----------------------|------------------------------------------------------------------------------------------------------------|-------------
`colorPrimary`         |The color displayed most frequently across your app’s screens and components.                               |#6200EE
`colorPrimaryVariant`  |A tonal variation of the primary color.                                                                     |#3700B3
`colorOnPrimary`       |A color that passes accessibility guidelines for text/iconography when drawn on top of the primary color.   |#FFFFFF
`colorSecondary`       |The secondary branding color for the app, usually an accented complement to the primary branding color.     |#03DAC6
`colorSecondaryVariant`|A tonal variation of the secondary color.                                                                   |#018786
`colorOnSecondary`     |A color that passes accessibility guidelines for text/iconography when drawn on top of the secondary color. |#000000

By changing these six color attributes, you can easily change the style of all
the Material components to which your theme is applied.

The Material Design color theming system provides additional colors which don't
represent your brand, but define your UI and ensures accessible color
combinations. These additional color attributes are as follows:

Attribute Name           |Description                                                                                                 |Default Value
-------------------------|------------------------------------------------------------------------------------------------------------|-------------
`android:colorBackground`|The background color appears behind scrollable content.                                                     |#FFFFFF
`colorOnBackground`      |A color that passes accessibility guidelines for text/iconography when drawn on top of the background color.|#000000
`colorSurface`           |Surface colors affect surfaces of components, such as cards, sheets, and menus.                             |#FFFFFF
`colorOnSurface`         |A color that passes accessibility guidelines for text/iconography when drawn on top of the surface color.   |#000000
`colorError`             |Error color indicates errors states, for components such as text fields                                     |#C51162
`colorOnError`           |A color that passes accessibility guidelines for text/iconography when drawn on top of the error color.     |#FFFFFF

Note: We are reusing several existing attributes -- `colorPrimary`,
`colorSecondary`, `android:colorBackground`, and `colorError`.

To select primary and secondary colors, and generate variations of each, use the
[Material palette generator](https://material.io/go/tools-color),
[Material Plugin for Sketch](https://material.io/go/tools-theme-editor), or 2014
Material Design palettes.

## Theming an Individual Component

All Material Design components use a `Widget.MaterialComponents` style, and
these styles reference color attributes from the Material Design theme
(`Theme.MaterialComponents`). So, it is easy to re-color attributes across your
app by simply modifying the color attributes in your theme.

However, if you want to change the color of just one instance of a component
without tweaking theme-level attributes, this can be done by creating a new
component style that extends from a `Widget.MaterialComponents` style.

For example, if you want to change MaterialButton so that it uses
`colorSecondary` for its background tint rather than `colorPrimary`, all you
need to do is define your own button style that extends from a Material Design
style and set the mapping yourself:

```xml
<style name="Widget.MyApp.MyButton" parent="Widget.MaterialComponents.Button">
  <item name="backgroundTint">?attr/colorSecondary</item>
</style>
```

You would then apply the `Widget.MyApp.MyButton` style to any buttons you want
to have this alternate style.

## Theming All Instances of One Component

If, however, you want to change the default styles for **all** instances of a
component, e.g. MaterialButton, this is possible by modifying the
`materialButtonStyle` attribute in your theme.

```xml
<style name="Theme.MyApp" parent="Theme.MaterialComponents.Light">
  ...
  <item name="materialButtonStyle">@style/Widget.MyApp.MyButton</item>
  ...
</style>
```

This will set the default style of any MaterialButtons in your app to
`Widget.MyApp.MyButton`. Similar default style attributes exist for most other
components, e.g. `tabStyle`, `chipStyle`, `textInputStyle`, and so on.

## Theme Attribute Mapping

The following components have been updated to use the theme attributes described
above:

*   [BottomNavigationView](BottomNavigationView.md)
*   [Chip](Chip.md)
*   [FloatingActionButton](FloatingActionButton.md)
*   [MaterialButton](MaterialButton.md)
*   [MaterialCardView](MaterialCardView.md)
*   [TabLayout](TabLayout.md)

To understand how the high-level theme attributes map to specific parts of each
component, please refer directly to the component's documentation.
