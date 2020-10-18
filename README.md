# ViewManagementPermissions for Android

License: MIT License 2.0

Permission system for accessing changes to the view from the Android SDK.

Status: In develop.

Preview.


Code example prototype for access change for selected view:

```Kotlin

class MyFragment: Fragment() { 

  private val accessOfficer = AccessOfficer(fragment)

  overrride fun onActivityCreated() {

    // ...
    accessOfficer.manageView(view) // Set management task for view. Only one access officer can manage access to views with all subviews (view.childs)

    accessOfficer.beginChange(view) // Begin changes for view

    //Change any UI paramenter on this UI
    // ...

    accessOfficer.commitChange(view) // End changes for view
    
  }

}

```

After fixing the changes, all critical changes (for text, onClick events, background, foreground, layout options, hints) for viewing will be monitored by the AccessOfficer class and subsystem modules, which will initiate a forced program shutdown and send the developer detailed error data with a report on unplanned changes.
Using this reverse management, you will need to update the interface code for the modules you are using, or reconsider whether to use them.



Code example prototype for ignore changes for selected view:
```Kotlin

accessOfficer.ignoreChange(view)

```
This ignore other untracked changes from all module in Android projects. 


#### Sum up.
This managment fix multimodule-archicture in application and adding implement of "import" control for view changes.
