# ProblemWithNestedCascadingParams

Shows strange problem with Blazor (C#) cascading parameters and `ValueChangedHelper` helper class (taken from https://github.com/conficient/BlazorBug04).
The problem is that the current counter value is not reflected in page URL.
Problem occurs in `CounterWithRouting.razor` (/counter_with_routing) when `NestedCascading` option is checked and tried to click counter increse/decrease buttons in child component (CounterChild.razor).
Problem disappears when (can be seen in commit history):
* `ValueChangedHelper` is not used in `CounterChild.razor`
* `CascadingParameter] OtherCascadingData OtherCascadingData { get; set; }` declaration is removed from CounterChild.razor
