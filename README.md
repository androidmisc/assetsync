# assetsync
sync asset folder to target folder by following step, will do nothing if the target file exists and its md5sum equals to the asset file

## example:
there is a folder in the app's asset 

- assetfolder
	- resource1
	- resource2
	- subfolder1
		- subresource1
		- subresource2
		
by calling:
<pre><code>
	AssetFolderSync.syncAssetFolderToFile(getContext(), "assetFolder", new File("/sdcard/test"));
</code></pre>


/sdcard/test content will be
- test
	- resource1
	- resource2
	- subfolder1
		- subresource1
		- subresource2

## Notice:
The sync operation will only create or replace file in target folder. It will not delete other old files in the output folder if there is not corresponding file in the assets.

## Usage:
First useable version is 1.1

In projects' build.gradle, add following repo.

<pre><code>
allprojects {
    repositories {
		...
        maven { url "https://github.com/androidmisc/assetsync/raw/master"}
	}
</code></pre>

In the modoule's build.gradle, add following dependencies:
<pre><code>
dependencies {
    debugImplementation 'com.bestcloudbrain:assetsync:1.1@aar'
    releaseImplementation 'com.bestcloudbrain:assetsync:1.1@aar'	
	....
}
</code></pre>
