{% include alert.html  type="warning" title=".Net Native Tool chain" content="UWP disables us to profile it when it is compiled with the 
<a href=\"https://docs.microsoft.com/en-us/dotnet/framework/net-native/\" target=\"_blanc\">.Net Native Tool chain</a> (You can find the setting in the UWP project settings in Visual Studio)" %}

{% include alert.html  type="warning" title="Debug Mode" content="Currently we only support profing UWP applications that are build in debug mode, we are looking into ways of also supporting release mode applications" %}
