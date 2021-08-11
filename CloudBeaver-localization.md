Not all localization comes from the Cloudbeaver source code, some of it comes from the backend side. So, if you want to, for example, change or create localization for database objects, you need to do it in another repository, that is https://github.com/dbeaver/dbeaver. Here is a guide how you can contribute to DBeaver localization https://github.com/dbeaver/dbeaver/wiki/Localization.   To create or improve localization for Cloudbeaver interface follow these steps:

_Note_: The images below are taken from [Fork](https://git-fork.com/). You can use another application to create pull-requests.

1. Open https://github.com/dbeaver/cloudbeaver and fork repository

![1](https://user-images.githubusercontent.com/51405061/128645751-a4671c5d-d644-4e2b-84a8-ae9e9cc169a5.png)

2. Clone the forked repository https://github.com/.../cloudbeaver to your local system.


![3](https://user-images.githubusercontent.com/51405061/128645747-5d9ebd7b-1a3f-4357-adf0-01b2b82a6299.png)

3. Create new branch from _devel_ branch (name it, for example, italian-localization).

![4](https://user-images.githubusercontent.com/51405061/128645746-9581157f-3baa-44c7-a6b3-a25a2aa992b5.png)

4. Go to local repository files and find the localisation file you want to translate. Create a copy of `en.ts` file in the directory and name it as [locale-code].ts (e.g. `it.ts` for Italian)

   Example: `../repository_name/webapp/packages/core-localization/src/locales`

5. Open the created file and translate tokens to your language. Change _EN_ on [locale-code] in the file here `export const defaultENLocale`.

Here is the structure of the language tokens: `['token-name', 'token-value']`. You need to change only the second part: `'token-value'`. For example, if you want to translate the _Loading..._ token, which is `['ui_processing_loading', 'Loading...']`, it will look like this: `['ui_processing_loading', 'Caricamento in corso...']`. 

6. Open the branch changes and _stage_ them

![9](https://user-images.githubusercontent.com/51405061/128645741-5a75f4ac-f3bc-483b-9488-3ae9e91993bc.png)

7. Push the changes

![10](https://user-images.githubusercontent.com/51405061/128645740-90d93cde-4496-4403-9454-592381d19254.png)

8. Commit the changes

![11](https://user-images.githubusercontent.com/51405061/128645738-1da0e8f7-bb6c-4ef5-9221-15bd6742c439.png)

9. Push to origin

![12_correct](https://user-images.githubusercontent.com/51405061/128645737-c92e25f6-1880-4ada-8a01-e6b97d594ec5.png)

10. Go to Github and press _Compare & pull request_ in your repository

11. Write a description and create pull request

Here is [Github instruction](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). You can use different IDEs to create pull requests.
