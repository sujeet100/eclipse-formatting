# Spotless eclipse-formatting

Has eclipse formatting xml file and the .editorconfig file for intellij which is almost in sync
To use eclipse formatting xml with spotless configure spotless task as below

``` gradle
spotless {
	format 'misc', {
		target '.gradle', '.md', '.gitignore'

		trimTrailingWhitespace()
		indentWithTabs() // or spaces. Takes an integer argument if you don't like 4
		endWithNewline()
	}
	java {
		eclipse().configFile('custom-eclipse-formatting.xml')
		indentWithSpaces(4)
		removeUnusedImports()
		trimTrailingWhitespace()
	}
}
```
