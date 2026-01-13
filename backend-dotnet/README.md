# backend-dotnet 🟣

## Overview

Minimal .NET 8 Web API used for demo purposes. The app serves a single GET route at `/` that returns "Hello from .NET" and is configured to bind to `http://localhost:5000` by default (see `Program.cs`).

## Prerequisites 🔧

- .NET 8 SDK installed (run `dotnet --info` to verify)
- Recommended: an IDE such as Visual Studio, Rider, or VS Code with C# support

## Project layout 📁

- `Program.cs` — app entrypoint (minimal hosting)
- `Controllers/` — API controllers
- `Models/` — request/response models
- `appsettings.json` — configuration
- `backend-dotnet.csproj` — project file

## Build & Run ⚙️

From the `backend-dotnet/` folder:

- Restore dependencies (optional):

```bash
dotnet restore
```

- Build:

```bash
dotnet build
```

- Run (development):

```bash
dotnet run
```

The app will be available at http://localhost:5000 by default. Quick check:

```bash
curl http://localhost:5000/
```

- Run on a custom URL/port (override):

```bash
dotnet run --urls "http://localhost:5001"
# or set environment variable
ASPNETCORE_URLS="http://localhost:5001" dotnet run
```

- Publish for production:

```bash
dotnet publish -c Release -o out
# run the published artifact (dll or executable)
# if a framework-dependent dll was produced:
dotnet out/backend-dotnet.dll
# or if an executable is produced (Linux/macOS):
./out/backend-dotnet
```

## Tests 🧪

There are no test projects included by default. If you add tests, run them with:

```bash
dotnet test
```

## Configuration & notes 📝

- Logging and other settings are in `appsettings.json`.
- The host binding is set explicitly in `Program.cs` (`app.Run("http://localhost:5000")`). To change the port, edit `Program.cs` or override at runtime using `--urls` or `ASPNETCORE_URLS`.

## Troubleshooting ⚠️

- Check runtime with `dotnet --info`.
- If the port is in use, change it via `--urls` or in `Program.cs`.

---

## Contributing

Feel free to add tests, Dockerfile, or a CI workflow and update this README accordingly.

---

License: MIT
