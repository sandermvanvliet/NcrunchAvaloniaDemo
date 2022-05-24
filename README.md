# NCrunch Avalonia demo

This project shows that with the default configuration NCrunch is not able to build projects that use Avalonia.

The reason for this is that `*.axaml` files are not included which results in the `XamlNameReferenceGenerator` not generating the `InitializeComponent` methods for Avalonia views. 
As the code-behind (`*.axaml.cs` files) are included the build fails because `InitializeComponent` does not exist.

The workaround for this is to add `Views\*.axaml` to the _Additional files to include_ setting on the project that uses Avalonia.

This demo project does not set this so that it shows the problem in action.