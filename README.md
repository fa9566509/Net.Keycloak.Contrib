# Net.Keycloak.Contrib

<div align="center">
  <img src="assets/kc_logo.svg" alt="Keycloak Logo" width="180">

Community-maintained .NET client for the Keycloak Admin REST API.

Built on the excellent work of the original
[NETCore.Keycloak](https://github.com/Black-Cockpit/NETCore.Keycloak)
project with additional features, fixes, and ongoing support for newer
Keycloak releases.
</div>

---

## Why this fork?

This project exists to provide community-driven improvements while keeping
compatibility with the upstream API.

Current additions include:

- Organization member management
- Organization invitations
- Keycloak 26+ organization serialization fixes
- Bug fixes and API improvements
- Compatibility updates for newer Keycloak releases

Our goal is to remain as API-compatible with the upstream project as possible
while delivering improvements more frequently.

---

## Features

- Complete Keycloak Admin REST API client
- Authentication API
- Users
- Groups
- Roles
- Clients
- Client Scopes
- Identity Providers
- Organizations
- Organization Members
- Organization Invitations
- User Sessions
- Components
- Events
- Fine-Grained Permissions
- OpenID Connect & OAuth 2.0 support

---

## Supported Versions

| Keycloak | Support |
|----------|---------|
| 26.x | ✅ |
| 25.x | ✅ |
| 24.x | ✅ |

| .NET |
|------|
| .NET 8 |
| .NET 9 |
| .NET 10 |

---

## Installation

```powershell
dotnet add package Net.Keycloak.Contrib
```

or

```powershell
Install-Package Net.Keycloak.Contrib
```

---

## Quick Start

Register the client

```csharp
builder.Services.AddKeycloak(...);
```

Authenticate

```csharp
var token = await client.Auth.GetClientCredentialsTokenAsync(
    realm,
    credentials);
```

Use the Admin API

```csharp
var users = await client.Users.GetAsync(
    realm,
    token.AccessToken,
    new KcUserFilter
    {
        Max = 20
    });
```

---

## Documentation

Documentation is organized by feature.

| Area | Description |
|------|-------------|
| Authentication | Client credentials, password, refresh tokens |
| Users | CRUD operations |
| Groups | Group management |
| Roles | Realm and client roles |
| Clients | Client configuration |
| Organizations | Organizations and domains |
| Organization Members | Membership management |
| Organization Invitations | Invite existing and new users |
| Authorization | UMA 2.0 |
| Events | Audit events |
| Components | Component management |

---

## Contributing

Contributions are welcome.

Please open an issue before making large API changes.

Every pull request should include:

- Unit or integration tests
- XML documentation
- Backwards compatibility where possible

---

## Relationship to NETCore.Keycloak

This project is a community-maintained fork of

https://github.com/Black-Cockpit/NETCore.Keycloak

It exists to:

- provide faster support for newer Keycloak releases,
- merge community contributions that are awaiting upstream review,
- maintain API compatibility wherever practical.

Credit goes to the original authors and contributors for creating and maintaining the original library.

---

## License

This project is licensed under the MIT License.

See the LICENSE file for details.