![ANE Inspector tool](http://www.myflashlabs.com/wp-content/uploads/2016/09/myflashlabs-inspector-ane.jpg)

:point_right: **NOTICE:** The inspector ANE is now deprecated. The [ANE-LAB software](https://github.com/myflashlab/ANE-LAB/) will be using it internally and this repository will no longer be updated. You are encouraged to remove this ANE from your project and instead use the ANE-LAB. :point_left:

# ANE Inspector V1.0.26 (Android+iOS)
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