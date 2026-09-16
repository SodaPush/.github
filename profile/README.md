# SodaPush

SodaPush is an open-source APNs backend you deploy in your own Cloudflare account. Workers, D1, and Queues provide a low-operations path that can fit within Cloudflare's free-plan limits for small workloads. You keep control of APNs credentials, device data, audience labels, and delivery records instead of handing them to a hosted push vendor. The portable server, native SwiftUI admin client, and Swift SDK work together as one self-managed system.

[Deploy to Cloudflare](https://deploy.workers.cloudflare.com/?url=https://github.com/SodaPush/Server) · [Server setup guide](https://github.com/SodaPush/Server#cloudflare-deployment)

## Repositories

| Project | Purpose |
| --- | --- |
| [Server](https://github.com/SodaPush/Server) | Hono API for Cloudflare Workers/D1/Queues or self-hosted Node.js/SQLite |
| [AdminClient-Swift](https://github.com/SodaPush/AdminClient-Swift) | Native iOS and macOS app for apps, credentials, devices, audiences, pushes, and access control |
| [SDK-Swift](https://github.com/SodaPush/SDK-Swift) | Swift package for signed device registration on Apple platforms |

> [!WARNING]
>
> Please use SodaPush reasonably. SodaPush project is only provided as tools, and SodaPush itself is not a service provider. We are not responsible for the information sent or the behavior of the users.

## Highlights

- Deploy into your own Cloudflare account using the setup script or Cloudflare's deploy-button flow; Docker/Node.js remains available.
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

Cloudflare's free plan has usage limits, and SodaPush still requires Apple APNs credentials. Self-deployment also means you are responsible for secret backups and access control.

## License

SodaPush repositories are distributed under their included license files.
