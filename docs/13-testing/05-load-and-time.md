# Load and time

This is not a social network. Target:

- 50 concurrent control-room users on one event
- Log create p95 < 500ms server-side
- Live mosaic first meaningful paint usable on a 10 Mbps laptop

A simple k6 or even a script of 50 log inserts is enough. Do not rent a load-test circus.

If realtime dies at 20 browsers, fix channels before the first festival.
