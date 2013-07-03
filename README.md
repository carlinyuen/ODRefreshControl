# CustomPullToRefreshControl

Based off Fabio Ritrovato's ODRefreshControl.

### Properties:

 * UIColor \*tintColor
 * UIColor \*strokeColor
 * UIColor \*shadowColor
 * UIColor \*activityIndicatorViewColor
 * BOOL drawDiskWhenPulling
 * BOOL enableDiskDripEffect
 * BOOL stickToTopWhenRefreshing
 * BOOL scrollUpToCancel

### Added features by Carlin:

 * Custom stroke & shadow colors.
 * Can turn on or off the drippy-slimey effect.
 * Can cancel refresh by scrolling back to rest position for user-defined time,
   and will emit a UIControlEventTouchCancel action for targets to listen to.
 * Can position the refreshing activity indicator / custom view to top of screen
   or top of scrollView.
 * Custom ImageView in place of arrow, which you can animate using custom styles.
 * Custom animation styles using linear and momentum "easing", and spin or rotate transforms.
 * Added functionality to reposition if scrollview gets scrolled horizontally.

![Enhancements](/screenshot.png "Enhancements")

#### Known Issues:

 * You can't use the Rotate style animation with the drippy-slimey effect on.
 * You can only use the custon animation styles on a custon imageview.
 * It looks like if you set this on a regular UIScrollView and enable paging, the activity indicator doesn't stay at the top. Working on this.


-----------------------
### ODRefreshControl Readme

__*Important note if your project doesn't use ARC*: you must add the @-fobjc-arc@ compiler flag to @ODRefreshControl.m@ in Target Settings > Build Phases > Compile Sources.__

*If you are using ODRefreshControl in your app, drop me a line so I can add your app here!*

## ODRefreshControl

![Screenshot](http://www.orangeinaday.com/img/ODRefreshControl.jpg "ODRefresh")

ODRefreshControl is a "pull down to refresh" control for UIScrollView, like the one Apple introduced in iOS6, but available to anyone from iOS4 and up.

### Installation

* Drag the @ODRefreshControl/ODRefreshControl@ folder into your project.
* Add the *QuartzCore* framework to your project.
* @#import "ODRefreshControl.h"@

### Usage

(see sample Xcode project in @/Demo@)

#### Adding a refresh control to your table view

<pre>
ODRefreshControl *refreshControl = [[ODRefreshControl alloc] initInScrollView:self.scrollView];
</pre>

To know when the refresh operation has started, add an action method to the UIControlEventValueChanged event of the control

<pre>
[refreshControl addTarget:self action:@selector(dropViewDidBeginRefreshing:) forControlEvents:UIControlEventValueChanged];
</pre>

If you’d like to programmatically start the refresh operation, use

<pre>
[refreshControl beginRefreshing];
</pre>

Remember to tell the control when the refresh operation has ended

<pre>
[refreshControl endRefreshing];
</pre>

#### Customization

The @ODRefreshControl@ can be customized using the following properties:

<pre>
@property (nonatomic, strong) UIColor *tintColor;
@property (nonatomic, assign) UIActivityIndicatorViewStyle activityIndicatorViewStyle;
@property (nonatomic, strong) UIColor *activityIndicatorViewColor; // iOS5 or more
</pre>

### Credits

ODRefreshControl is brought to you by "Fabio Ritrovato":http://orangeinaday.com and "contributors to the project":https://github.com/Sephiroth87/ODRefreshControl/contributors. If you have feature suggestions or bug reports, feel free to help out by sending pull requests or by "creating new issues":https://github.com/Sephiroth87/ODRefreshControl/issues/new. If you're using ODRefreshControl in your project, attribution would be nice.
!https://cruel-carlota.pagodabox.com/a9d517c98620f7f8e865458f744c1cbb!


------------------------------------
## License
MIT
