- Step 1. Copy library's directory to our project's `root` directory.

- Step 2. Modify the `"settings.gradle"` in your project's root directory, like this:
```
    include ':app',':pulltorefresh'
```

- Step 3. Modify the `"build.gradle"` under directory `"app"`, add a line in the block `"dependencies"`, like this:

```
    dependencies {
	    ...
        compile project(':pulltorefresh')
    }
```

- Step 4. Create a `"build.gradle"` file under the library's root, its content like this:

```
apply plugin: 'com.android.library'

android {
	compileSdkVersion 16
	buildToolsVersion "23.0.3"

	sourceSets {
		main {
			manifest.srcFile 'AndroidManifest.xml'
			java.srcDirs = ['src']
			resources.srcDirs = ['src']
			aidl.srcDirs = ['aidl']
			renderscript.srcDirs = ['src']
			res.srcDirs = ['res']
			assets.srcDirs = ['assets']
		}
	}
}
```

Notice the first line `apply plugin: 'com.android.library'` , it's different from the `app's build.gradle`.

- Step 5. I think it's time to Sync the project. 
