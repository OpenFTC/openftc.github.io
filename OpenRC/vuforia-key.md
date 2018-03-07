# Securely storing your Vuforia key

If you publish your source code publicly on GitHub with your
Vuforia key, you're actually violating the Vuforia Developer
Agreement. The solution to avoid this is to load the Vuforia
key from a non-public file when the app is built.

OpenRC has set up this up for you, so that you just need
to set up the external file and change your Vuforia code to
access the key dynamically.

Note that this **WILL work on the stock build variant** as
well, because we didn't need to modify any of the official
libraries to make this work.

1.  In the TeamCode module, you'll find a file called
    `vuforia.template.properties`. You need to make a copy
    of this file in the same folder, called
    `vuforia.properties`.
    
2.  Open up this new copy, and paste your Vuforia key in
    between the quotation marks on the bottom line. It
    should look like `VUFORIA_KEY="VUFORIAKEYTHATLOOKSLIKEGIBBERISH"`.

3.  Change the line where you tell vuforia what your key is 
    to `parameters.vuforiaLicenseKey = BuildConfig.VUFORIA_KEY`.
    
    a.  If you get an error when you try to build the project,
        try changing the line to
        `parameters.vuforiaLicenseKey = org.firstinspires.teamcode.BuildConfig.VUFORIA_KEY`.
        You may have accidentally imported a different `BuildConfig` class.

4.  Copy `vuforia.properties` to the TeamCode module on any
    other computers that you'll be using for programming.
    Remember, the vuforia key won't automatically be synced
    between computers any more.

And you're done! `vuforia.properties` is included in the
`.gitignore` file, which means that Git won't try to add it
to your public GitHub repository.