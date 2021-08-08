Not all localization comes from the Cloudbeaver source code, some of it comes from the backend side. So, if you want to, for example, change or create localization for database objects, you need to do it in another repository, that is https://github.com/dbeaver/dbeaver. Here is a guide how you can contribute to DBeaver localization https://github.com/dbeaver/dbeaver/wiki/Localization.

To create or improve localization for Cloudbeaver interface follow these steps:
1. Open Eclipse https://www.eclipse.org/downloads/ or another IDE. The next steps describe how to do it in Eclipse:
2. Open File - Import - Projects from Git

![Screenshot 2021-08-08 at 18 01 51](https://user-images.githubusercontent.com/51405061/128636541-543ad94c-a918-4248-abcc-08a616096d63.png)

![2_1](https://user-images.githubusercontent.com/51405061/128636362-9003dc4f-e5f9-4b35-879d-350bf1c942c9.png)

3. Select clone URI

![3](https://user-images.githubusercontent.com/51405061/128636361-cdc58986-89f8-49c8-b7ba-0a9f03b5ea5d.png)

4. Paste https://github.com/dbeaver/cloudbeaver to URI field

![4](https://user-images.githubusercontent.com/51405061/128636360-d497c3ca-a76a-449c-a951-ce57cfea3677.png)

5. Select devel branch

![5](https://user-images.githubusercontent.com/51405061/128636359-ba602e70-0825-4a36-ac2b-4a14ba46863e.png)

6. Enter local directory

![6](https://user-images.githubusercontent.com/51405061/128636357-3ff96119-7698-4952-b916-ac4ea86608ba.png)

7. Select Import as general project 

![7](https://user-images.githubusercontent.com/51405061/128636356-29cd50a2-e69b-44b0-b982-959542c205d9.png)

8. Create project name and hit Finish

![8](https://user-images.githubusercontent.com/51405061/128636355-68ca5317-4a9e-465a-b065-7c8244daae08.png)

9. Open Window - Show view - Navigator

![9](https://user-images.githubusercontent.com/51405061/128636353-1d85c2c8-8657-4d21-aa96-cf555776dd9b.png)

10. Expand the project in Navigator tree and open webapp - packages - core-localization - src - locales, copy-paste _en.ts_ file and rename it to e.g. _it.ts_

![10](https://user-images.githubusercontent.com/51405061/128636352-2705936c-fc1b-423e-934d-932d041492d4.png)

11. Open the pasted file with a text editor and translate text to your language.

Here is the structure of the language tokens: ['token-name', 'token-value']. You need to change only the second part, 'token-value'. For example, if you want to translate the Loading... token, which is ['ui_processing_loading', 'Loading...'], it will look like this: ['ui_processing_loading', 'Caricamento in corso...']. Save changes

![11](https://user-images.githubusercontent.com/51405061/128636350-05bb111b-5d1c-45aa-85b6-d8cf647e98e1.png)

12. Select in the context menu Team - Commit

![12](https://user-images.githubusercontent.com/51405061/128636349-a95ad47d-0040-4f09-be9c-1e0b2a5f24a9.png)

13. Hit Push HEAD in the opened panel

![13](https://user-images.githubusercontent.com/51405061/128636348-78900eba-d350-42ed-a7b5-9bd16f7aea57.png)

14. Create a branch name, e.g. Italian_translation

![14](https://user-images.githubusercontent.com/51405061/128636347-06ad4ff2-113e-4d20-8a59-295e83031df8.png)

15. Enter your Github credentials

![15](https://user-images.githubusercontent.com/51405061/128636346-e8bbae8b-35f6-4e2b-937f-fb7bf18ebd20.png)

16. Hit Push and enter your Github credentials again

![16](https://user-images.githubusercontent.com/51405061/128636345-9feeaead-1d2e-4c66-b4e3-92a0353e8de6.png)

Pull request is created.

![17](https://user-images.githubusercontent.com/51405061/128636343-80959c54-30ff-46ea-a052-9a56777ee78b.png)

