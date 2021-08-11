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

![6](https://user-images.githubusercontent.com/51405061/129053618-7195a786-1e23-4c57-bfaa-c989515408f5.png)

7. Push and Commit the changes

![7](https://user-images.githubusercontent.com/51405061/129054875-d90504a4-7903-4af2-a1ba-49422d8c5c9f.png)

8. Push to origin

![12_correct](https://user-images.githubusercontent.com/51405061/128645737-c92e25f6-1880-4ada-8a01-e6b97d594ec5.png)

9. Go to Github and press _Compare & pull request_ in your repository

10. Write a description and create pull request

Here is [Github instruction](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). You can use different IDEs to create pull requests.
