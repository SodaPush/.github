# SodaPush

SodaPush is an open-source, self-hosted Apple Push Notification service. It combines a portable server, a native SwiftUI administration client, and a Swift SDK so teams can own their device data and APNs delivery infrastructure.

## Repositories

| Project | Purpose |
| --- | --- |
| [Server](https://github.com/SodaPush/Server) | Hono API for Cloudflare Workers/D1/Queues or self-hosted Node.js/SQLite |
| [AdminClient-Swift](https://github.com/SodaPush/AdminClient-Swift) | Native iOS and macOS app for apps, credentials, devices, audiences, pushes, and access control |
| [SDK-Swift](https://github.com/SodaPush/SDK-Swift) | Swift package for signed device registration on Apple platforms |

## Highlights

- Deploy on Cloudflare or your own Docker/Node.js host.
- Keep APNs signing keys, registration secrets, and device tokens encrypted at rest.
- Separate sandbox and production devices and APNs credentials.
- Target all active devices, explicit installations, custom tags, device languages, or application-defined user IDs.
- Send alert, background, Live Activity, and custom JSON payloads.
- Inspect delivery results and remove completed push history.
- Use role-based access with one immutable instance owner and per-app administrators, developers, and viewers.

## How the pieces fit together

1. Deploy [SodaPush Server](https://github.com/SodaPush/Server) and bootstrap its single owner account.
2. Use [SodaPush Admin](https://github.com/SodaPush/AdminClient-Swift) to create an app, upload sandbox/production APNs keys, and create a registration key.
3. Add [SodaPush SDK](https://github.com/SodaPush/SDK-Swift) to the receiving app and register its APNs device token.
4. Send notifications from the admin client to an environment and audience using the default APNs key or an explicitly selected key.

Each repository contains its own deployment, integration, security, and testing documentation.

## License

SodaPush repositories are distributed under their included license files.
