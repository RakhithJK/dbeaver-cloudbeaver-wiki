Not all localization comes from the Cloudbeaver source code, some of it comes from the backend side. So, if you want to, for example, change or create the localization for database objects, you need to do it in another repository, that is https://github.com/dbeaver/dbeaver. Here is a guide on how you can contribute to dbeaver localization https://github.com/dbeaver/dbeaver/wiki/Localization.

To create or improve the localization for Cloudbeaver follow these steps:

## Prepare for changes
  1. Fork repository https://github.com/dbeaver/cloudbeaver.
  2. Clone it to your local system.
  3. Make a new branch (for example, **italian-localization**).
## Make changes
  4. Find the package you want to change the localization in.<br/>
In Cloudbeaver all translatable resources are located in the **locales** folder. The path to the folder is **[package-name]\src\locales\\[locale-code].ts**.<br/> For example, you can find basic UI language tokens in the **core-localization\src\locales\\[locale-code].ts** file.
  5. Create localization file.<br/> 
For example, if you want to add localization for the Italian language create ```it.ts``` file next to the ```en.ts``` file in the directory we have discussed before. After that, copy all content from the ```en.ts``` file to the ```it.ts``` file.
  6. Translate tokens to your language.<br/>
Here is the structure of the language tokens: ```['token-name', 'token-value']```. You need to change only the second part, **'token-value'**.<br/>
For example, if you wanted to translate the **Loading...** token, which is ```['ui_processing_loading', 'Loading...']```, it would look like this:  ```['ui_processing_loading', 'Caricamento in corso...']```.
  7. Commit and Push your changes back to your repo.
  8. Click the Compare & pull request button.
  9. Click Create pull request to open a new pull request (in branch `devel`) https://help.github.com/articles/creating-a-pull-request-from-a-fork/.

To find the right localization files, you can go to https://github.com/dbeaver/cloudbeaver -> press **Go to file** -> paste **en.** in the input and you should see all available localization files.
