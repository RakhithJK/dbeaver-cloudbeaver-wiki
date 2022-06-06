### CloudBeaver 22.1.0 - 2022-06-06

Changes since 22.0.0
- The new Resource Manager allows users to store and manage scripts in CloudBeaver.
- Data Editor:
  - The auto-refresh tool has been added to update table data automatically;
  - Big values can be saved to an external file;
  - The Value panel supports BLOB images.
- SQL Editor:
  - Object names can be added to the SQL Editor field by dragging them from the Navigator Tree;
  - The SQL Editor for a connection can be opened via URL.
- Metadata Editor:
  - Objects DDL can be opened in the SQL Editor.
- Authentication:
  - Users can login to the application via Nginx.
- Connection:
  - Keep-Alive interval and Connect timeout parameters can be configured for an SSH Tunnel;
  - SQL Server supports NTLM authentication;
  - Administrators can use PgPass authentication for PostgreSQL.
- Administration:
  - The Resource Manager can be disabled;
  - Administrators can revoke and return permissions to a user with a single click in the user's dialog.
- Local configuration:
  - The size limit of the Resource Manager scripts and the Value panel files can be configured to improve CloudBeaver performance;
  - SSH key value for a connection can be stored in the configuration file.
  - Application fields can be returned to a default size by double-clicking on the field's separator.
- Different bug fixes and enhancements have been made.