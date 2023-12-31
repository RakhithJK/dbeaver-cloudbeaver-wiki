Not all localization comes from the Cloudbeaver source code. Some of it comes from the backend side. So, if you want to, for example, to change or create localization for database objects, you need to do it in another repository, at https://github.com/dbeaver/dbeaver. Here is a guide to how you can contribute to DBeaver's localization https://github.com/dbeaver/dbeaver/wiki/Localization.   To create or improve localization for the Cloudbeaver interface, follow these steps:

_Note_: The images below are taken from [Fork](https://git-fork.com/). You can use another application to create pull-requests.

1. Open https://github.com/dbeaver/cloudbeaver and fork repository

![Screenshot 2021-08-12 at 15 14 33](https://user-images.githubusercontent.com/51405061/129194932-622192b0-a718-4575-ba8d-b4c526293932.png)

2. Clone the forked repository https://github.com/.../cloudbeaver to your local system.


![3](https://user-images.githubusercontent.com/51405061/128645747-5d9ebd7b-1a3f-4357-adf0-01b2b82a6299.png)

3. Create a new branch from _devel_ branch (name it, for example, italian-localization).

![4](https://user-images.githubusercontent.com/51405061/128645746-9581157f-3baa-44c7-a6b3-a25a2aa992b5.png)

4. Go to the local repository and find the localization files you want to translate.

In Cloudbeaver, all translatable resources are located in the locales folder. The path to the folder is [package-name]\src\locales\[locale-code].ts.<br/>
Create a copy of `en.ts` file in the package you want to change the localization in and name it [locale-code].ts (e.g. `it.ts` for Italian)

Example: `../repository_name/webapp/packages/core-localization/src/locales`

5. Open the created file and translate the tokens to your language. Change _EN_ on [locale-code] in the top of the file `export const defaultENLocale` => `export const defaultITLocale`.

Here is the structure of the language tokens: `['token-name', 'token-value']`. You only need to change the second part: `'token-value'`. For example, if you wanted to translate the _Loading..._ token, which is `['ui_processing_loading', 'Loading...']`, it would look like this: `['ui_processing_loading', 'Caricamento in corso...']`. 

6. Open the branch changes and _stage_ them

![Screenshot 2021-08-12 at 15 16 59](https://user-images.githubusercontent.com/51405061/129195225-f18201dc-4323-43cb-b521-eb7a48d18152.png)

7. Commit the changes

![Screenshot 2021-08-12 at 15 19 08](https://user-images.githubusercontent.com/51405061/129195517-dfc52cef-e9a2-46d1-81a5-4e176f5265ac.png)

8. Push to origin

![Screenshot 2021-08-12 at 15 21 39](https://user-images.githubusercontent.com/51405061/129195949-f78f9be0-1631-4a19-840c-265a1e1e1292.png)

9. Go to Github and press _Compare & pull request_ in your repository

10. Write a description and create pull request

Here is [Github instruction](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). You can use different IDEs to create pull requests.
