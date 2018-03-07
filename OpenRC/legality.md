# Is OpenRC legal to use in competition?

In a word, no. However, there is more to the story. OpenRC's build speed improvements and
added features are mostly useful when you're developing your OpModes at team meetings.
It's not actually even that useful when you're at a competition.

### Our solution

While OpenRC was originally legal for competition use, we recognized that the GDC has the
power to change that, and developed a feature called [stock mode](buildvariants) that lets
you build a competition-legal version of the app from within your OpenRC Android Studio
project. [You can read its documentation here](buildvariants).

### Why stock mode is legal

Stock mode is possible because of the exact wording of
[the ruling](https://ftcforum.usfirst.org/forum/i-first-i-tech-challenge-game-q-and-a-forum-this-is-a-moderated-forum/first-relic-recovery-presented-by-qualcomm-game-q-a-forum/robot-inspection-rules/answers-electrical-materials/50465-control-system-answers?p=63242#post63242),
specifically, this sentence:

> "An unauthorized version of the FTC SDK includes any version of the
SDK that modifies or omits any of the libraries included within the Robot Controller app."

In software development, the term "library" is used for software that your program uses,
but that is not developed as a part of your program. Libraries are maintained separately,
often by a third party.

What this means for the FTC Robot Controller app is that you're free to modify any code
that's provided only in the form of its source code. This would include the `TeamCode`
module (obviously), the `FtcRobotController` module, and all of the Gradle files that tell
Android Studio how everything goes together.

What's not legal to modify is everything in the `libs` folder. This includes all of the `.aar`
and `.jar` files that we used to make many of the modules in OpenRC. This is what makes the regular
OpenRC mode illegal.

The stock mode builds the app from the unmodified `.aar` files in the `libs` folder directly, ignoring the
project modules that are based on them. Even though it's not technically required, we also disable all of
our modifications to the `FtcRobotController` module when stock mode is enabled. The result is an app that's
fully legal for competition use.