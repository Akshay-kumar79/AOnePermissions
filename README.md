# AOne Permissions

## Dependency setup

Add jitpack in your projects settings.gradle.kts
```
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
      mavenCentral()
      maven { setUrl("<https://jitpack.io>") }
    }
}
```

Add the dependency
```
dependencies {
    implementation("com.github.Akshay-kumar79:AOnePermissions:1.0.2-alpha")
}
```

## Usage

Add permission in your manifest file
```
<uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
```

Initialize permission requester. Safely run your code with the required permission. 
Library handles permission and permission rational within these few lines of code.
```
val permissionRequester = rememberPermissionRequester(
    Manifest.permission.POST_NOTIFICATIONS
)

Button(
    onClick = {
        permissionRequester.requestAndExecute {
            // Do your work with required permission
            Toast.makeText(context, "Do your work now", Toast.LENGTH_SHORT).show()
        }
    }
) {
    Text("Do work")
}
```

Feel free to contribute to this repository. You are always welcomed.

**THANK YOU**
