# Sensitive modules

## Three levels

| Level | Examples | Wall visibility |
| --- | --- | --- |
| Open operational | Most incidents, tasks, log | Control room |
| Security-sensitive | Some security notes, ejections detail, suspicious activity narrative | Security roles |
| Restricted | Medical extras, safeguarding cases | Named roles + audit on read |

## Medical

Allowed extras (minimise):

- presenting issue in short operational language
- team dispatched
- ambulance requested / arrived
- hospital transfer yes/no + hospital name
- response timestamps
- close-out operational notes

Avoid:

- diagnosis essays
- medication lists unless the customer insists and the DPIA allows
- photos of injuries by default (permission + warning if uploaded)

## Safeguarding

Separate table. Separate ID prefix. Separate nav.

A control operator who hears “safeguarding at welfare tent” logs a **control-log line** and notifies the safeguarding lead. They do not get the case body.

## Security

Ejections, searches, and suspicious activity can be ordinary incidents with a `restricted_detail` flag. If flagged, body is security-manager+.

## Search and AI

Global search and later AI skip restricted bodies without permission.
