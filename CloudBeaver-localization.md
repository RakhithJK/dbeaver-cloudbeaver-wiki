Not all localization comes from the Cloudbeaver source code, some of it comes from the backend side. So, if you want to, for example, change or create localization for database objects, you need to do it in another repository, that is https://github.com/dbeaver/dbeaver. Here is a guide how you can contribute to DBeaver localization https://github.com/dbeaver/dbeaver/wiki/Localization.   To create or improve localization for Cloudbeaver interface follow these steps:

1. Open https://github.com/dbeaver/cloudbeaver and fork repository

![1](https://user-images.githubusercontent.com/51405061/128645751-a4671c5d-d644-4e2b-84a8-ae9e9cc169a5.png)

2. Open [Fork](https://git-fork.com/) and go to _File - Clone_

3. Enter your Github repository https://github.com/user_name/cloudbeaver and clone it to your local system

![3](https://user-images.githubusercontent.com/51405061/128645747-5d9ebd7b-1a3f-4357-adf0-01b2b82a6299.png)

4. Right click on _devel_ branch and create new branch (name it, for example, italian-localization)

![4](https://user-images.githubusercontent.com/51405061/128645746-9581157f-3baa-44c7-a6b3-a25a2aa992b5.png)

5. Go to local repository files ../repository_name/webapp/packages/core-localization/src/locales. Duplicate _en.ts_ file in the directory and name it as [locale-code].ts (e.g. it.ts for Italian)

6. Open the created file and translate tokens to your language. Change _en_ on [locale-code] in the file here `export const defaultENLocale`.

Here is the structure of the language tokens: ['token-name', 'token-value']. You need to change only the second part: 'token-value'. For example, if you want to translate the Loading... token, which is ['ui_processing_loading', 'Loading...'], it will look like this: ['ui_processing_loading', 'Caricamento in corso...']. 

7. Go back to Fork, open _Local Changes_, select your created file and press _Stage_

![9](https://user-images.githubusercontent.com/51405061/128645741-5a75f4ac-f3bc-483b-9488-3ae9e91993bc.png)

8. Press Push

![10](https://user-images.githubusercontent.com/51405061/128645740-90d93cde-4496-4403-9454-592381d19254.png)

9. Fill _Commit Subject_ field and and commit the changes

![11](https://user-images.githubusercontent.com/51405061/128645738-1da0e8f7-bb6c-4ef5-9221-15bd6742c439.png)

10. Open context menu for your branch and select _Push to origin_

11. Go to Github and press _Compare & pull request_ in your repository

![14](https://user-images.githubusercontent.com/51405061/128645735-44ca4c14-df8d-439b-befd-d6972f1afbe3.png)

12. Write a description and create pull request

![15](https://user-images.githubusercontent.com/51405061/128645733-4dff533a-8f98-4065-aec0-1043ee52c346.png)

Here is [Github instruction](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). You can use different IDEs to create pull requests.
