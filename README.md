[![](https://img.shields.io/nuget/v/soenneker.extensions.datetime.suite.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.extensions.datetime.suite/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.extensions.datetime.suite/publish-package.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.extensions.datetime.suite/actions/workflows/publish-package.yml)
[![](https://img.shields.io/nuget/dt/soenneker.extensions.datetime.suite.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.extensions.datetime.suite/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.extensions.datetime.suite/codeql.yml?label=CodeQL&style=for-the-badge)](https://github.com/soenneker/soenneker.extensions.datetime.suite/actions/workflows/codeql.yml)

# ![](https://user-images.githubusercontent.com/4441470/224455560-91ed3ee7-f510-4041-a8d2-3fc093025112.png) Soenneker.Extensions.DateTime.Suite

A convenience meta-package that installs six focused `DateTime` extension packages for weekday, hour, week, month, quarter, and year operations.

## Installation

```bash
dotnet add package Soenneker.Extensions.DateTime.Suite
```

The suite contains no extension classes of its own. NuGet adds the included packages transitively, and your code imports the namespace for each feature it uses:

```csharp
using Soenneker.Extensions.DateTime.DayOfWeek;
using Soenneker.Extensions.DateTime.Hour;
using Soenneker.Extensions.DateTime.Month;
using Soenneker.Extensions.DateTime.Quarter;
using Soenneker.Extensions.DateTime.Week;
using Soenneker.Extensions.DateTime.Year;

System.DateTime value = DateTime.UtcNow;

System.DateTime startOfMonth = value.ToStartOfMonth();
System.DateTime nextMonday = value.ToStartOfNextDayOfWeek(DayOfWeek.Monday);
System.DateTime endOfYear = value.ToEndOfYear();
```

## Included packages

| Package | Namespace | Scope |
| --- | --- | --- |
| `Soenneker.Extensions.DateTime.DayOfWeek` | `Soenneker.Extensions.DateTime.DayOfWeek` | Strict previous/next weekday navigation and boundaries |
| `Soenneker.Extensions.DateTime.Hour` | `Soenneker.Extensions.DateTime.Hour` | Hour boundaries and hour formatting |
| `Soenneker.Extensions.DateTime.Week` | `Soenneker.Extensions.DateTime.Week` | Week boundaries and navigation |
| `Soenneker.Extensions.DateTime.Month` | `Soenneker.Extensions.DateTime.Month` | Month boundaries and navigation |
| `Soenneker.Extensions.DateTime.Quarter` | `Soenneker.Extensions.DateTime.Quarter` | Calendar-quarter boundaries and navigation |
| `Soenneker.Extensions.DateTime.Year` | `Soenneker.Extensions.DateTime.Year` | Year boundaries and navigation |

Install an individual package instead when only one feature area is needed. This suite does not include `Soenneker.Extensions.DateTime`, `Soenneker.Extensions.DateTime.Day`, or `Soenneker.Extensions.DateTime.Nullable`.
