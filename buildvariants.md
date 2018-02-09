# OpenRC Stock Build Variant

Beginning with version 2.0 beta 1, OpenRC projects have the ability to build a stock version of the app
without moving any code. Modified SDKs
[have been ruled illegal for competition use by the GDC](https://ftcforum.usfirst.org/forum/i-first-i-tech-challenge-game-q-and-a-forum-this-is-a-moderated-forum/first-relic-recovery-presented-by-qualcomm-game-q-a-forum/robot-inspection-rules/answers-electrical-materials/50465-control-system-answers?p=63242#post63242),
but with this feature, you can easily use the features and speed of OpenRC while you develop your OpModes,
and then quickly deploy a legal version of the app to your phone before a competition.

### Note: Any modifications you make to any built-in modules other than FtcRobotController and TeamCode will NOT be applied when you are using the stock build variant.
If you've added your own modules (e.g. for OpenCV), those are safe.

## Instructions
To switch between the "stock" and "openrc" build variants, choose `Build > Select Build Variant` from the menu.
There's also a Build Variants tab in the lower left corner area of Android Studio  (assuming that you haven't
collapsed the bars along the edges by clicking on the little window icon in the very bottom left corner).

Choose the appropriate option from the dropdown next to the `TeamCode` module. The build variants will have
`Debug` appended to them.

When you switch to a new build variant, it's recommended to sync the project with the Gradle files. 
For Android Studio 3.0, you can find that option under `Tools > Android`. Starting in Android Studio 3.1, that
option is located in the `File` menu.

## How it works

The app is built using the stock, official AAR files, instead of the customized library modules. The ruling is that
you can't modify these files, so the stock build variant is competition-legal.