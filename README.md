# Rider.Namespaces

This repo contains a sample Blazor Server application to demonstrate the bug described in this [issue](https://youtrack.jetbrains.com/issue/RIDER-68514).

## Bug reproduction

In order to reproduce the bug, simply use the quick fix `To file-scoped namespace -> To file-scoped namespaces in project` to convert the namespace `Example.Sample.Data` in [WeatherForecast.cs](Example.Sample/Data/WeatherForecast.cs) to be file-scoped project wide.
This will result in the `@namespace` declaration in [Index.razor](Example.Sample/Pages/Index.razor) to change:
```diff
- @namespace Example.Sample.Pages
+ @namespace Example.Sample.Pages ;
```
