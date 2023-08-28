# Spotless eclipse-formatting

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
