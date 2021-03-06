# XCarousel

## Build Status

| XCarousel.Touch  | XCarousel.Droid | .Touch.Sample  | .Droid.Sample |
| ------------- | ------------- | ------------- | ------------- |
|![Build status](https://build.appcenter.ms/v0.1/apps/561b6d5c-f52e-46cb-b97f-655044511616/branches/master/badge)|![Build status](https://build.appcenter.ms/v0.1/apps/8b739197-554d-40e1-b73c-7b19c87f4c19/branches/master/badge)|![Build status](https://build.appcenter.ms/v0.1/apps/e88b8cee-33be-4324-be8d-06e067577194/branches/master/badge)|![Build status](https://build.appcenter.ms/v0.1/apps/e535c92f-2f2a-4808-9e13-eab56e508d85/branches/master/badge)|

## Preview
![](carouselPicker.gif)

## Blogs

1. https://butonium.com/xamarin-carouselpicker/
2. https://alexandrustefan.com/xcarouselpicker/

## Setup 

On client projects install the nuget XCarouselPicker ([![NuGet](https://img.shields.io/nuget/v/XCarouselPicker.svg?label=NuGet)](https://www.nuget.org/packages/XCarouselPicker/)) and then follow the steps based on platform:

## Android

#### Standard

1. Add a new XCarouselView inside your Main layout file:

```
     <XCarousel.Droid.Views.XCarouselView
            android:id="@+id/picker"
            android:background="@android:color/transparent"
            android:layout_centerInParent="true"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">
    </XCarousel.Droid.Views.XCarouselView>
```

2. In your Activity you'll need to assign a Collection to this view:

```
    var picker = FindViewById<XCarouselView>(Resource.Id.picker);
    
    var products = new List<PickerItem>();

    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));
    products.Add(new DrawableItem(Resource.Drawable.CoffeeAsset));

    picker.Items = products;
```

3. And for the FadeEffect to take place you'll need to assign the desired FadeColor:

```
    picker.FadeColor = "#ecf0f1";
```

## iOS

#### Standard

Note that this UICollectionView customization was designed to work with one row and horizontal scrolling. If you have a different case, create a pull request to see if we can addapt the component to more general needs.

1. Add a new UICollectionView to your view. Within Widget properties, select "XCarouselView" as you CollectionViewType.

2. Create your UICollectionViewCell. There is no known restriction on what can be in here.

3. Create your UICollectionViewDataSource.

4. Wire everything together:

```
    customCollectionView.RegisterNibForCell(CustomCollectionViewCell.Nib, CustomCollectionViewCell.Key);
    customCollectionView.DataSource = new CustomDataSource();
```

Now your project should have a UICollectionView that resembles the behaviour from the Preview gif.

## Known issues/difficulties/notes

- The current state of the component works properly only with one image within the element of the XCarouselPicker. If you have a different scenario, please do create an issue and we'll see how we can addapt the component to it.

## Conclusion

### If you have a question or a suggestion, please add an issue and we'll discuss over it. We're open to respond, add new features, fine tune our solutions or, last, but most important, to fix bugs/problems that you encounter. 
#### As you've got this far and our code might helped you, support us to build more content like this through: 
<a href="https://www.buymeacoffee.com/grendio" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>
