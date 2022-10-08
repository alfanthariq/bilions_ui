### Bilions UI Components

![Preview](https://github.com/necessarylion/bilions_ui/raw/master/preview.png)

### Functions

##### Alert

```
alert(
  'Title here',
  'Description here',
  variant: Variant.warning, 
)

```
- variant `success, waring, danger, info`

##### Toast

```
toast('Confirmed', variant: Variant.success);

```
- variant `success, waring, danger, info`

##### Confirm Dialog
```
confirm(ConfirmDialog(
    'Are you sure?', 
    variant : Variant.success,
    confirmed: () {
      // do something here
    },
  ),
)
```

##### Image Picker

```
openUploader(context, 
  variant: 'primary',
  onPicked: (FileInfo file) {
    console.log(file.path);
  },
);
```
- add below lines in `ios->Runner->info.plist`
```
<key>NSPhotoLibraryUsageDescription</key>
<string>Allow Image access to upload your profile image</string>
<key>NSCameraUsageDescription</key>
<string>Allow Image access to upload your profile image</string>
```

##### Image Preview

```
preview([
  'https://picsum.photos/id/237/536/354',
  'https://picsum.photos/id/238/536/354',
  'https://picsum.photos/id/239/536/354',
])

```

##### Menu 

```
menu(
  MenuList([
    MenuListItem(
      Icon(
        Icons.edit,
        size: 20,
      ),
      title: 'Edit',
      onPressed: () {
        // do something
      },
    ),
  ])
)
```

### Component Widgets

##### DatePicker Input 

```
BilionsDatePicker(label: 'Date of Birth', onChanged: (date) => {}),
```

##### DateRangePicker Input

```
 BilionsDateRangePicker(
    label: 'Date of Birth',
    onChanged: (start, end) => {

    },
),
```

##### TextInput

```
BilionsTextInput(label: 'Full Name', onChanged: (text) => {})
```

##### Password Input

```
TODO
```

##### Avatar Image 

```
Avatar(
  'https://i.pravatar.cc/150?img=3',
  title: 'Zin Kyaw Kyaw',
  subTitle: 'aj@bilions.org',
)
```

##### Image Slider 

```
ImageSlider([
  'https://picsum.photos/id/237/536/354',
  'https://picsum.photos/id/238/536/354',
  'https://picsum.photos/id/239/536/354',
])
```
##### Primary Button

```
PrimaryButton(
  'Button Title',
  variant : Variant.success,
  onPressed: () {
    // do something
  },
)
```
##### Secondary Button

```
SecondaryButton(
  'Button Title',
  variant : Variant.success,
  onPressed: () {
    // do something
  },
)
```

##### Alert Widget

```
BilionsAlert(
  'Wake Up',
  'You need to code flutter',
  icon: Icon(Icons.alarm),
)
```

##### Card 
```
CardWidget(
  header: const Avatar(
    'https://i.pravatar.cc/150?img=3',
    title: 'Zin Kyaw Kyaw',
    subTitle: 'aj@bilions.org',
  ),
  body: Column(
    children: const [
      Span(
        "Lorem Ipsum is simply dummy text of the printing and variantsetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of variant and scrambled it to make a variant specimen book. It has survived not only five centuries, but also the leap into electronic variantsetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.",
      )
    ],
  ),
  footer: const Text('This is footer'),
)
```

### Date formatter

- get current date time `now()` will return Current `DateTime` instance
- format date to string `moment.dateToString(now())` will return formatted string date
- format date to string `moment(now()).format(format: 'dd MMM yyyy')` will return formatted string date
- format date to string `moment('2022-11-22').parse()` will return `DateTime` instance

### Access Theme Colors

```
- BilionsColor.primary
- BilionsColor.primaryLight

- BilionsColor.warning
- BilionsColor.warningLight

- BilionsColor.danger
- BilionsColor.dangerLight

- BilionsColor.info
- BilionsColor.infoLight

- BilionsColor.success
- BilionsColor.successLight
...
```

### Variants

```
- Variant.primary
- Variant.warning
- Variant.danger
- Variant.info
- Variant.success
...
```

### Color configuration
- Want to set your own colors?
- You can set your own colors in main() function

```
void main() {

  BilionsUI bilionsUI = BilionsUI();
  bilionsUI.setColors(
    ColorConfig(
      danger: Colors.red,
      primary: Colors.blue,
      success: Colors.green,
      warning: Colors.yellow,
      info: Colors.purple,
    ),
  );

  runApp(const MyApp());
}
```