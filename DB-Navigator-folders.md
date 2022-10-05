## Database Navigator folders

Users can use folders to group and store connections in the most appropriate way in the Navigator tree.

Any logged user can create folders for their connections in the Private project.

Administrators can also create folders for shared connections in the Shared project. Folders for connections will be available only in the Navigator tree, the Connection Management view in the Administration will remain unchanged. 

Both, Private and Shared, projects are completely independent and it isn't possible to move connections and folders between them.
Any number of connections and other folders can be placed in one folder.

To create a folder in the Database Navigator:
1. Click a connection in the Navigator tree, then press the New folder button on the top Navigator toolbar.

![new_folder_button](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/new_folder_button.png)

2. Enter a folder name in the pop up dialog box and press the Create button.

![new_folder_name](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/new_folder_name.png)

**Note**: a folder name can contain any letters, numbers and following symbols: _-$.()@. The folder name must be unique in the project. But a subfolder can have the same name as a folder at a level above.
If a user uses unsupported characters or a non-unique name for the folder, an error message appears and the user needs to change the name in order to create or rename the folder.                                         

The new empty folder will appear in the Navigator tree. You can then place connections there. Just drag and drop the connection into the folder.                          

![connection_in_the_folder](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/connection_in_the_folder.png)

Once a connection is placed into a folder, the information about it appears in the connection window.

![connection_dialog_with_folder](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/connection_dialog_with_folder.png)

To move a connection out of a folder, drag and drop it above the list of Navigator objects.

![move_connection_from_a_folder](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/move_connection_from_a_folder.png)                                                                                               

If you want to place a subfolder in a folder:
drag and drop a folder into another folder or 
click on a folder and create a new one.The created folder will be placed in the selected folder.

If you want to move a subfolder out of a folder, drag and drop it above the list of Navigator objects or into another folder.

If you want to rename a folder, select Rename from the folder context menu and change the name in the pop up dialog box.

![navigator_folder_context_menu](https://github.com/dbeaver/cloudbeaver/wiki/images/navigator_folders/navigator_folder_context_menu.png) 

To delete a folder, select Delete from the folder context menu and confirm the action in the pop up dialog box. 
**Note**: the folder and subfolders within it will only be deleted. All folder’s connections remain in the Navigator tree.

If you want to update a folder's content, select Refresh from the folder context menu.
