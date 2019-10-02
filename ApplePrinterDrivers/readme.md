Please note that there have been a few revisions to these recipes that may require you to take another look at them.

Discussion about these changes can be found at https://groups.google.com/d/topic/autopkg-discuss/zkA-iSwbODQ/discussion

### Recipe Name Changes
The original recipe names were

* `XeroxPrinterDrivers.download.recipe`
* `XeroxPrinterDrivers.munki.recipe`

They are now

* `AppleXeroxPrinterDrivers.download.recipe`
* `AppleXeroxPrinterDrivers.munki.recipe`

Notice that `Apple` is now prepended.
#### What does this mean?
This means that some of your scripts that may be statically calling these recipes will need to be updated.

For example
`autopkg run XeroxPrinterDrivers.munki` will need to become `autopkg run AppleXeroxPrinterDrivers.munki`

### Name Variable Changes
The original name names were

* `XeroxPrinterDrivers`

They are now

* `AppleXeroxPrinterDrivers`

Notice that `Apple` is now prepended.
#### What does this mean?
When using the `AppleXeroxPrinterDrivers.munki.recipe` recipe, these drivers will be imported to your repository with a new Name.
Any manifests that are set to deploy or require these drivers will need to be updated to use the new name.
A quick way to fix this would be to use MunkiAdmin (https://github.com/hjuutilainen/munkiadmin).
Find a package currently named `XeroxPrinterDrivers` and rename it to `AppleXeroxPrinterDrivers`.
MunkiAdmin will notice that there are other items referencing this item and apply the new name to the referencing items.

### Identifier Changes
The original identifier for these recipes were

* `com.github.n8felton.download.XeroxPrinterDrivers`
* `com.github.n8felton.munki.XeroxPrinterDrivers`

They are now

* `com.github.n8felton.download.AppleXeroxPrinterDrivers`
* `com.github.n8felton.munki.AppleXeroxPrinterDrivers`

Notice that `Apple` is now prepended.
#### What does this mean?
If you have any custom recipes or recipe overrides referencing the old identifer names (via `ParentRecipe`), they will need to be updated to reference the new identifiers.
