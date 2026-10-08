# Quality score

The **Quality** tab in the macro settings scores the docs out of 100 and lists what's missing, so you know what to improve in the spec. It checks things like:

- an API description and contact details,
- servers and security schemes,
- a summary, description, operation ID and tag for each endpoint,
- descriptions for tags, parameters and schemas,
- documented success and error responses,
- examples for requests and responses.

Some checks count double because readers notice them most. Each failed check lists the first few endpoints or parameters that need work.

The score is worked out from what readers will see, so tag and path filters count. It runs in your browser; nothing is sent anywhere. AsyncAPI specs don't get a score.
