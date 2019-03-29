# SVGAGlidePlugin
> Glide Integration Library for Playing .svga Animation Files

---

## SVGA
you can know more at [svga.io][1] .

## Feature

- Thread pool management.
- Resource cache management（Memory & Disk).
- Users only need to care about loading and displaying a resource from Url, no matter what format it is, JPG, GIF or SVGA.
- Support [RePlugin][2] even with this [ISSUE][3]. 

## Usage

```kotlin
fun loadSVGAFromNetwork(v: View) {
    Glide.with(this)
        .load("https://github.com/yyued/SVGA-Samples/blob/master/kingset.svga?raw=true")
        .into(iv_img)
}

fun loadSVGAFromAssets(v: View) {
    Glide.with(this)
        .load("file:///android_asset/angel.svga")
        .into(iv_img)
}

fun loadSVGAFromRes(v: View) {
    Glide.with(this)
        .load(R.raw.angel)
        .into(iv_img)
}

fun loadSVGAFromNetworkAndAddText(v: View) {
    GlideApp.with(this)
        .asSVGA()
        .load("https://github.com/yyued/SVGA-Samples/blob/master/kingset.svga?raw=true")
        .into(SVGATarget(iv_img, requestDynamicItemWithSpannableText()))
}
```

## Install

```groovy
dependencies {
    // SVGAPlayer
    implementation 'com.github.yyued:SVGAPlayer-Android:2.1.9'
    
    // Glide 
    implementation "com.github.bumptech.glide:glide:$glide_version"
    kapt "com.github.bumptech.glide:compiler:$glide_version"
    
    // integration for them
    implementation 'com.github.YvesCheung.SVGAPlayer-Android:glideplugin:2.1.3.0'
}
```


  [1]: http://svga.io/
  [2]: https://github.com/Qihoo360/RePlugin
  [3]: https://github.com/Qihoo360/RePlugin/issues/351