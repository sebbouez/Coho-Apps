# Create multilingual Websites

Creating a multilingual website is very easy with PageFabric.

You can configure your website languages when you create a new Website.

Manage languages in the Website settings dialog
Open the website settings dialog and go to the Languages section.

## Using the redirect script

If your website supports several languages, you can include a redirect script at the root of the deployment folder.

You can choose to use a fixed language as default when your visitors open your website, or detect the user's language
using its browser properties. If the redirect fails, your visitors will be redirected to the first language.

> Note: This technique is based on Javascript because PageFabric doesn't generate server code.

## Adding and removing languages

To add a new language to your website, click the Add languages button. A popup will ask you which language you want to
add, then click the Add button. The new language will be added to the Supported languages list.

To remove a language from your website, click the Remove button on each supported language item.

> Note: When you remove a language, we don't delete each version of your pages. The impact is just on the published
> website. If you add again the language, you will find your old pages versions for this language.

Switch page language in the editor
Click on the button at the bottom right of the window to change the current language of the page you are changing.

Select the language to edit by clicking the language name.

If you do not plan to publish the page in a specific language, click the Delete button. When you generate your website,
the page will be skipped in that language.