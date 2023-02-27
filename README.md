# Serilog.Enrichers.OpenTelemetry
Enriches Serilog events with an Open Telemetry trace id and/or span id for tracking requests.

To use the enricher, first install the NuGet package:
```bash
Install-Package Serilog.Enrichers.OpenTelemetry
```

Then you can apply the enrichers to your `LoggerConfiguration`:
```csharp
Log.Logger = new LoggerConfiguration()
    .Enrich.WithTraceId()
    // ...other configuration...
    .CreateLogger();
```

The `WithTraceId()` enricher will add a `TraceId` property to the produced events.

## Included enrichers
The package includes the following enrichers:
* `WithTraceId()` adds a `TraceId` to track logs for the current web request.
* `WithSpanId()` adds a `SpanId` to track logs for the current span.