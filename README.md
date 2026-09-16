# KLRN Calendar

A browser-based tool for creating, maintaining and printing KLRN TV's monthly Prime Time Schedule.

## How it works

- `KLRN-Prime-Time-Schedule.html` is the standalone calendar application
- The application provides an editable monthly calendar designed for printing
- Calendars can be saved locally as HTML files using the File System Access API
- The application can check a server-side template for newer versions before creating a new calendar
- `template.php` delivers the current HTML template, including the app version

## Setup

Place `template.php` and `KLRN-Prime-Time-Schedule.html` in the same server directory.

Set `APP.templateUrl` in `KLRN-Prime-Time-Schedule.html` to the URL of `template.php`:

    templateUrl: 'https://example.com/klrn-calendar/template.php',

Set the current application version in the HTML:

    <meta name="app-version" content="1.0.0">

When releasing an update, update the version number in the HTML template. The application will detect the newer version when the user chooses **New Calendar**.

If `templateUrl` is empty or `null`, update checking is disabled.

## Development

The application runs entirely in the browser. PHP is only used to provide the current HTML template for update checking.

## Planned

- Drag-and-drop TV schedule parsing to seed calendar entries.
