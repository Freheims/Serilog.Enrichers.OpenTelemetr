# Serilog.Enrichers.OpenTelemetry
Enriches Serilog events with an Open Telemetry trace id and/or span id for tracking requests.

To use the enricher, first install the NuGet package:
```bash
Install-Package Serilog.Enrichers.OpenTelemetry
```

Then you can apply the enrichers to your `LoggerConfiguration`:
```csharp
Log.Logger = new LoggerConfiguration()
    .Enrich.WithOpenTelemetryTraceId()
    // ...other configuration...
    .CreateLogger();
```

The `WithOpenTelemetryTraceId()` enricher will add a `TraceId` property to the produced events.

## Included enrichers
The package includes the following enrichers:
* `WithOpenTelemetryTraceId()` adds a `TraceId` to track logs for the current web request.
* `WithOpenTelemetrySpanId()` adds a `SpanId` to track logs for the current span.