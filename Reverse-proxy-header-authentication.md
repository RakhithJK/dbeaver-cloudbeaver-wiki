Cloudbeaver supports authorization and authentication with reverse proxy headers.
This option authenticates the user in Cloudbeaver via a HTTP header field.

To enable this feature, you need to 
1. enable Reverse proxy header based authentication method in [Authentication settings](https://github.com/dbeaver/cloudbeaver/wiki/Authentication-methods/_edit) of Administration menu
2. Set up your NGINX configuration to send special header fields to your Cloudbeaver app.

The default values for the HTTP header fields are:
1. Header User Name: `X-User`;
2. Header Team Name: `X-Role`.
	
Default teams for user in Cloudbeaver are "user" and "admin".
Delimeter for teams is "|".

For example, if you are a user with username "newuser" and your teams are "user" and "admin" and you want to open an app with enabled reverse proxy header auth, 
you need to set these HTTP headers when you send a request to your CB app:

	X-User: newuser
	X-Role: user|admin