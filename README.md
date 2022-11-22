# StrawberryShake_13_Console

Sample of code generated from https://chillicream.com/docs/strawberryshake/get-started/console. But using StrawberryShake 13.preview.
This Proejcte is only used to generate ConferenceClient.Client.cs code for testing in other Unity test proejcts.

---

In This Branch I also experimented modifying the .csproj file so the project would output the correct netstandard 2.x DLLs instead of netcoreapp3.1 DLLs. This would make it possible to automatic copied over the DLLs (e.g., with a git sub modules). At the current state I must update the DLLs by hand.

What I tried was change <TargetFramework>net6.0</TargetFramework> to <TargetFramework>netstandard2</TargetFramework>
That doesn't work because:
 1. compiling for netstandard2 will use C# 8
 2. it breaks the StrawberryShake.Server Package in a way that the dependencies are thrown out

I fixed 1. by adding <LangVersion>10.0</LangVersion> as it is described in C# language versioning (https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/configure-language-version).
I tried to fix 2. by adding the dependencies of StrawberryShake.Server manually as nuget packages.

I gave up on this because after all this changes the console says "StrawberryShake.Core ..." or some other dependency is missing.

Repo link https://github.com/firedrill-gmbh/StrawberryShake_13_Console/tree/TargetFramework_netstandard2
