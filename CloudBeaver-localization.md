Not all localization comes from the Cloudbeaver source code, some of it comes from the backend side. So, if you want to, for example, change or create localization for database objects, you need to do it in another repository, that is https://github.com/dbeaver/dbeaver. Here is a guide how you can contribute to DBeaver localization https://github.com/dbeaver/dbeaver/wiki/Localization.   To create or improve localization for Cloudbeaver interface follow these steps:

1. Open https://github.com/dbeaver/cloudbeaver and _Fork_ repository

![1](https://user-images.githubusercontent.com/51405061/128645751-a4671c5d-d644-4e2b-84a8-ae9e9cc169a5.png)

2. Open [Fork](https://git-fork.com/) and go to _File - Clone_

![2](https://user-images.githubusercontent.com/51405061/128645749-ab0b56c6-c9aa-4c8d-a8f6-4f839b96d8a2.png)

3. Enter your Github repository https://github.com/user_name/cloudbeaver to _URL_ and hit _Clone_ to clone repository to your local system

![3](https://user-images.githubusercontent.com/51405061/128645747-5d9ebd7b-1a3f-4357-adf0-01b2b82a6299.png)

4. Right click on _devel_ branch and select _New Branch_

![4](https://user-images.githubusercontent.com/51405061/128645746-9581157f-3baa-44c7-a6b3-a25a2aa992b5.png)

5. Enter a new branch name (for example, italian-localization) and hit _Create and Checkout_

![5](https://user-images.githubusercontent.com/51405061/128645745-9951d367-614a-4c82-ba97-9ee7fe1611ce.png)

6. Go to local repository files ../repository_name//webapp/packages/core-localization/src/locales

![6](https://user-images.githubusercontent.com/51405061/128645743-e9e5ae96-3ef1-4f3b-8ca6-280fc9f362a7.png)

7. Duplicate en.ts file in the directory and name it as [locale-code].ts (e.g. it.ts for Italian)

8. Open the created file and translate tokens to your language. Change _en_ on [locale-code] in the file.

Here is the structure of the language tokens: ['token-name', 'token-value']. You need to change only the second part: 'token-value'. For example, if you want to translate the Loading... token, which is ['ui_processing_loading', 'Loading...'], it will look like this: ['ui_processing_loading', 'Caricamento in corso...']. 

9. Go back to Fork, open _Local Changes_, select your created file, then hit _Stage_

![9](https://user-images.githubusercontent.com/51405061/128645741-5a75f4ac-f3bc-483b-9488-3ae9e91993bc.png)

10. Press _Push_ on the top toolbar and in the pop up

![10](https://user-images.githubusercontent.com/51405061/128645740-90d93cde-4496-4403-9454-592381d19254.png)

11. Fill _Commit Subject_ field and hit _Commit_

![11](https://user-images.githubusercontent.com/51405061/128645738-1da0e8f7-bb6c-4ef5-9221-15bd6742c439.png)

12. Open context menu for your branch and select _Push to origin_

![12_correct](https://user-images.githubusercontent.com/51405061/128645737-c92e25f6-1880-4ada-8a01-e6b97d594ec5.png)

![12_correct2](https://user-images.githubusercontent.com/51405061/128645736-ca7ca0bf-433e-4ea4-aa80-2f30d8217ec3.png)

13. Enter your Github credentials

![13_creds](https://user-images.githubusercontent.com/51405061/128645739-63be3074-ade9-4256-a1ed-80999f27c2e1.png)

14. Go to Github and press _Compare & pull request_ in your repository

![14](https://user-images.githubusercontent.com/51405061/128645735-44ca4c14-df8d-439b-befd-d6972f1afbe3.png)

15. Write a description and create pull request

![15](https://user-images.githubusercontent.com/51405061/128645733-4dff533a-8f98-4065-aec0-1043ee52c346.png)

Here is [Github instruction](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). You can use different IDEs to create pull requests.
