# WatchComplicationLaunchDismissBug

When a WatchKit app is active, the user may choose to go back to the home screen by pressing the Home button. The app is then suspended in the background. The user may then later wish to return to the app in its previous state. That state may be, for example, with a modal presented on screen.

If the user returns to the watch app by navigating to the honeycomb view of apps or list view of apps, then tapping on the app name, the modal still appears presented. This is also true if the user returns to the watch app by opening the Dock and resuming the app from there. However, if the user chooses to re-enter the app from a complication, the app automatically dismisses the modal on screen. This is a problem, because watchface complications are encouraged by Apple to be treated as shortcuts to quickly re-launch apps.

Steps to reproduce:

- The sample project supports one type of complication, modular small, but this appears to be true from all complication types.
- Run the sample project on a watch, either in the Simulator or real hardware. 
- Install the modular small complication for the app on the modular watch face - the complication icon depicts breast-feeding.
- From the main watch app, tap the button to present a modal. Then press the home button on the watch to background the watch app.
- Resume the watch app from the honeycomb view or list view of apps or the Dock - the modal should still be visible. Press the home button to background the watch app again.
- Resume the watch app from the supported modular small complication. Notice that the modal has been dismissed automatically.
