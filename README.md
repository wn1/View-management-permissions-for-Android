# ViewManagementPermissions for Android

License: MIT License 2.0

Permission system for accessing changes to the view from the Android SDK.

Status: In develop.

Preview.


Code example prototype for access change for selected view:
+++++++++++++++++++

class MyFragment: Fragment() { 

  private val accessOfficer = AccessOfficer(fragment)

  overrride onActivityCreated() {

    ...

    accessOfficer.beginChange(view)

    //Change any UI paramenter on this UI
    ...

    accessOfficer.commitChange(view)
    
  }

}

+++++++++++++++++++

After commitChange all changes for view stop programm and track bug for developer security callback.
If it response, need update code interfaces for used moduls.




Code example prototype for ignore changes for selected view:
+++++++++++++++++++

accessOfficer.ignoreChange(view)

+++++++++++++++++++



This system block other untracked changes from all module in Android projects. 
This fix multimodule-archicture in application and adding implement of "import" control for view changes.
