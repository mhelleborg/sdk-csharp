![Build](https://github.com/cloudevents/sdk-csharp/actions/workflows/build.yml/badge.svg)

## Status

This SDK current supports the following versions of CloudEvents:

- v1.0

# sdk-csharp

.NET Standard 2.0 (C#) SDK for CloudEvents

The `CloudNative.CloudEvents` package provides support for creating, encoding,
decoding, sending, and receiving [CNCF
CloudEvents](https://github.com/cloudevents/spec). Most applications
will want to add dependencies on other `CloudNative.CloudEvents.*`
packages for specific event format and protocol binding support. See
the [user guide](docs/guide.md) for details of the packages available.

## A few gotchas highlighted for the impatient who don't usually read docs

1. The [CloudEvent](src/CloudNative.CloudEvents/CloudEvent.cs) class is not meant to be used with 
   object serializers like JSON.NET. If you need to serialize or deserialize a CloudEvent directly, always use a
   [CloudEventFormatter](src/CloudNative.CloudEvents/CloudEventFormatter.cs)
   such as  [JsonEventFormatter](src/CloudNative.CloudEvents.NewtonsoftJson/JsonEventFormatter.cs).
2. Protocol binding integration is provided in the form of extensions and the objective of those extensions
   is to map the CloudEvent to and from the respective protocol message, such as an HTTP request or response.
   The application is otherwise fully in control of the client. Therefore, the extensions do not
   add security headers or credentials or any other headers or properties that may be required to interact
   with a particular product or service. Adding this information is up to the application.

## User guide and other documentation

The [docs/](docs) directory contains more documentation, including
the [user guide](docs/guide.md). Feedback on what else to include in
the documentation is particularly welcome.

## Changes since 1.x

From version 2.0.0-beta.2, there are a number of breaking changes
compared with the 1.x series of releases. New code is
strongly encouraged to adopt the latest version rather than relying
on the 1.3.80 stable release.

The stable 2.0.0 version was released on June 15th 2021, and all
users are encouraged to use this (or later) versions.

A [more details list of changes](docs/changes-since-1x.md) is
provided within the documentation.

## Community

- There are bi-weekly calls immediately following the [Serverless/CloudEvents
  call](https://github.com/cloudevents/spec#meeting-time) at
  9am PT (US Pacific). Which means they will typically start at 10am PT, but
  if the other call ends early then the SDK call will start early as well.
  See the [CloudEvents meeting minutes](https://docs.google.com/document/d/1OVF68rpuPK5shIHILK9JOqlZBbfe91RNzQ7u_P7YCDE/edit#)
  to determine which week will have the call.
- Slack: #cloudeventssdk channel under
  [CNCF's Slack workspace](https://slack.cncf.io/).
- Email: https://lists.cncf.io/g/cncf-cloudevents-sdk
- Contact for additional information: Clemens Vasters (`@Clemens Vasters`
  on slack).

Each SDK may have its own unique processes, tooling and guidelines, common
governance related material can be found in the
[CloudEvents `docs`](https://github.com/cloudevents/spec/tree/main/docs)
directory. In particular, in there you will find information concerning
how SDK projects are
[managed](https://github.com/cloudevents/spec/blob/main/docs/SDK-GOVERNANCE.md),
[guidelines](https://github.com/cloudevents/spec/blob/main/docs/SDK-maintainer-guidelines.md)
for how PR reviews and approval, and our
[Code of Conduct](https://github.com/cloudevents/spec/blob/main/docs/GOVERNANCE.md#additional-information)
information.
