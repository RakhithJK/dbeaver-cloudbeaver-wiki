## Service naming

As we have several service types, we want to reflect these types in the file name. It will allow us to easily determine the purpose of usage.

**Default service** (general-purpose, application business logic): `*Service`  
_Examples: `LocalisationService`, `NavigationTreeService`_


**Resource service** (state management): `*Resource`  
_Examples: `UserInfoResource`, `ConnectionInfoResource`_


**Bootstrap service** (application initiation logic): `*Bootstrap`  
_Examples: `CustomConnectionMenuBootstrap`, `SQLEditorBootstrap`_