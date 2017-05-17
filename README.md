![ANE Inspector tool](http://www.myflashlabs.com/wp-content/uploads/2016/09/myflashlabs-inspector-ane.jpg)
# ANE Inspector V1.0.19 (Android+iOS)
The main job of this ANE is to check the ANEs you are implementing in your Air project to see if the platform you are running on meets the minimum requirements needed by those ANEs. Besides that, this ANE can also check if the target running ANE is having access to all the required dependency ANEs (if any) or not.

Use of this ANE is optional however we do recommend using it in all your projects as it will help you avoid developing mistakes to save you a lot of time. You can also safely know if the running platform can run a specefic ANE or not.

# asdoc
[find the latest asdoc for this ANE here.](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/inspector/Inspector.html)

# Air Usage
Using this ANE is very easy. All you have to do is to call the [check](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/inspector/Inspector.html#check()) method and pass in the name of the ANE class you wish to inspect along with the type of check you wish to construct.
```actionscript
import com.myflashlab.air.extensions.inspector.Inspector;

// pass in the main class name of the target ANE you wish to inspect
if (!Inspector.check(Barcode, true, false))
{
	// if the check method returns false, it means that the target ANE can't run
	// on this platform. in this case, you should avoid initializing the target ANE
	trace("Inspector.lastError = " + Inspector.lastError);
}
```

An important fact you should remember when using the inspector, is the third Boolean parameter you are passing into the ```check``` method. The default value for the third parameter is ```false``` and you are strongly advised to set it to ```false``` when you are releasing your app. the job of this parameter is to check if the target ANE you are inspecting is having access to any dependency ANEs (if any) or not. This operation is RAM hungry and considering that adding or removing ANEs from your project is in your control in the development time, you can use this feature when building your project. When you are releasing your app to the stores, you should make sure you are not inspecting the ANEs for their dependencies. *This is not causing any errors though, it just slows your app a bit*

On the other hand, the second parameter, checks the platform your app is running on. This check process is very light and you should keep it active always so you can know if the target ANE can run on the current platform or not.

# Air .xml manifest
```xml
<extensionID>com.myflashlab.air.extensions.inspector</extensionID>
```

# Changelog
*May 17, 2017 - V1.0.19*
* Updated Facebook to V4.22.1
* Updated RichWebview to V7.1.0
* Updated VR to V2.2.1

*Mar 31, 2017 - V1.0.18*
* Updated Barcode to V3.3.0
* Updated Facebook to V4.17.1
* Updated FileChooser to V4.1.1
* Updated GameServices to V2.2.0
* Updated GPS to V3.2.1
* Updated in-app-payments to V2.2.0
* Updated PDFViewer to V2.1.1
* Updated PermissionCheck to V2.1.0
* Updated RateMe to V1.1.1
* Updated Spotlight to V1.0.1
* Updated VideoPlayer to V3.0.1
* Updated SurfaceVideoPlayer to V3.4.1
* Updated Volume to V1.1.1
* Updated Badge to V1.1.0
* Updated Statusbar to V1.0.1
* Updated ZipManager to V3.0.1

*Mar 07, 2017 - V1.0.17*
* Updated Firebase ANE to V4.0.0
* Updated Admob ANE to V2.1.0

*Jan 14, 2017 - V1.0.16*
* Updated Firebase ANE to V3.0.0

*Jan 10, 2017 - V1.0.15*
* Updated GoogleVR ANE to V2.1.1

*Dec 05, 2016 - V1.0.14*
* Fixed this [issue](https://github.com/myflashlab/ANE-Inspector-Tool/issues/2)

*Nov 27, 2016 - V1.0.13*
* Updated Firebase to 2.0.0

*Nov 11, 2016 - V1.0.12*
* Updated PermissionCheck to V2.0.2
* Updated RichWebview ANE to V6.6.0
* Updated ZipManager ANE to V3.0.0
* Updated VideoPlayer ANE to V3.0.0
* Updated Surface Video Player ANE to V3.4.0
* Updated Volume ANE to V1.1.0
* Updated RateMe ANE to V1.1.0
* Updated PDF ANE to V2.1.0
* Updated in-app-payments ANE to V2.1.0
* Updated GPS ANE to V3.2.0
* Updated GoogleVR ANE to V2.1.0
* Updated GameServices ANE to V2.1.0
* Updated FileChooser ANE to V4.1.0
* Updated Facebook ANE to V4.17.0
* Updated Barcode Scanner ANE to V3.2.0
* Updated Admob ANE to V1.1.0

*Nov 03, 2016 - V1.0.11*
* Updated PermissionCheck to 2.0.2

*Nov 02, 2016 - V1.0.10*
* Updated PermissionCheck to 2.0.1

*Oct 29, 2016 - V1.0.9*
* Updated PermissionCheck to 2.0.0

*Oct 26, 2016 - V1.0.8*
* Added Badge ANE
* Added Statusbar ANE

*Oct 23, 2016 - V1.0.7*
* Fixed [this issue](https://github.com/myflashlab/Firebase-ANE/issues/26)

*Oct 22, 2016 - V1.0.6*
* Updated Google VR to 2.0.1
* Updated SurfacePlayer to 3.3.0

*Oct 07, 2016 - V1.0.5*
* fixed [this issue](https://github.com/myflashlab/Firebase-ANE/issues/24)

*Sep 29, 2016 - V1.0.4*
* Added Firebase FCM ANE

*Sep 25, 2016 - V1.0.3*
* Updated Firebase to 1.2.0
* Updated Google VR to 2.0.0
* Updated GCM to 5.0.1

*Sep 14, 2016 - V1.0.2*
* Updated RichWebview to 6.5.0

*Sep 13, 2016 - V1.0.1*
* Added Firebase Crash ANE

*Sep 12, 2016 - V1.0.0*
* beginning of the journey!