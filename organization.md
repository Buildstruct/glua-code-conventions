# Organization

### Structure
* There should be a minimal amount of code in the `autorun` folder. All other code should be put into another project-unique folder (if applicable).
* Namespace tables are tables that hold the publicly accessible code and variables for your project, you should generally have one. They should be named after the project ID (see below).
* Public variables and functions are those which are under namespace tables.
* Only namespace tables and simple (ie. booleans or numbers) constants may be direct members of the global table. All other items should be under a namespace table.
* Prefer making local variables/functions over global ones.
* Prefer making local variables of lower scope over higher scope.

### Naming
* The project should have a 'project ID' which is just a condensed name of the project (it will be used in the names of many other things, namely the namespace table).
* Lua files should always be prefixed with their realm(s): `cl_`, `sh_`, or `sv_`.
* Lua files should be in lowercase only.
* Global variables not meant to be changed should be in `CAPITALIZED_SNAKE_CASE`.
* Local variables and local functions should be in `camelCase`.
* Public variables, public functions, and methods should be in `PascalCase`.
* Truly global constants (which are direct members of the global table) should be prefixed with the project ID: `ID_GLOBAL_CONST`.
* Overridden methods, hook names, timer names, and custom vgui names should be prefixed with the project ID and put in `PascalCase`: `ID_MyThingy`.
