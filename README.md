
# Watermark-Test

## Overview

The application can be started with the packaged `activator`.
Tests can be run with the `test` command, the server can be started with the `run` command.

The specified interface is implemented in the `WatermarkService` trait.
A simple implementation of the persistence and watermark generation functionality can be found in the `MockWatermarkService`.

## Testing

An entire execution of the use case can be found in `IntegrationSpec`.

For easier testing and demonstration, there is a web interface implemented in `WatermarkController` that exposes the service as a simple REST API.

### Example

`http://localhost:9000/book/The%20Dark%20Code/Bruce%20Wayne/Science` created and sends a book object for watermark generation and persistence to the service.

`http://localhost:9000/status/:ticketNumber` returns the current status of the ticket processing.
Initially the status is *Generating*, after the watermark is generated and the document persisted the status will change to *Finished*

`http://localhost:9000/document/:ticketNumber` returns the document (or status 404 if no document with the specified ticketNumber is available)
