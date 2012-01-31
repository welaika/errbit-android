Errbit Notifer for Android
===========================

Overview
--------
The Errbit notifier for Android is designed to give you instant notification
of any uncaught exceptions thrown from your Android applications.

It's based on AirBrake Notifer for Android <http://loopj.com/airbrake-android/>

Installation & Setup
--------
Build the .jar and place it in your Android app’s lib/ folder.

Import the ErrbitNotifier class in your app’s main Activity.

    import com.welaika.android.errbit.ErrbitNotifier;

In your activity’s onCreate function, register to begin capturing exceptions:

    ErrbitNotifier.register(this, "errbit.domain.com", "your-api-key-goes-here");

Configuration
--------
The ErrbitNotifier.register call requires a context and Airbrake/Errbit API key to be passed in, and optionally a third argument specifying the environment. The environment defaults to production if not set.

To notify Errbit of non-fatal exceptions, or exceptions you have explicitly caught in your app, you can call ErrbitNotifier.notify. This call takes exactly one argument, a Throwable, and can be called from anywhere in your code. For example:

    try {
        // Something dangerous
    } catch(Exception e) {
        // We don't want this to crash our app, but we would like to be notified
        ErrbitNotifier.notify(e);
    }

Building from Source
--------
To build a .jar file from source, make a clone of the errbit-android github repository and run:

    ant package

This will generate a file named errbit-android.jar.

This is a fork!
--------
Thanks a lot to James Smith that created the original version for Airbrake. Thanks!