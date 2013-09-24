This fork of the [Sqlite Client for Windows Phone](http://sqlitewindowsphone.codeplex.com/) C# implementation of SQLite was created for a [cordova plugin](https://github.com/Smile-SA/cordova-plugin-websqldatabase).

## Modifications

### Non-typed result

The original plugin doesn't provide a non-typed result query function.
So, you need to create a C# bean object for each SQLite table !


And you don't want to create a data binding in C# if you want to use this lib as a cordova plugin.

In SQLiteClient.cs the "ExecuteSql" has been added to provide a non-typed result query function.

### Temporary directory crash

On Windows Phone, application rights forbid to access the temporary directory. If you use the original lib as is, your WP app will crash !

In SQLiteClient.cs and os_win_c.cs, a patch has been added to use an application-scoped temporary directory.

## Cordova plugin using this fork

https://github.com/Smile-SA/cordova-plugin-websqldatabase
