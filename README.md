# Securing Microservices with IdentityServer4, OAuth2 and OpenID Connect (via Ocelot API Gateway)

This repository demonstrates how to secure microservices in a real-world e-commerce scenario using IdentityServer4, OAuth2, OpenID Connect, and the Ocelot API Gateway.

## 🔒 Overview

We implement secure communication between multiple services:

- `Movies.API` (protected API resource)
- `Movies.MVC` (interactive client app)
- `IdentityServer` (standalone identity provider)
- `Ocelot API Gateway` (reverse proxy handling authorization)

![System Overview](https://user-images.githubusercontent.com/1147445/97865031-9a4c9f00-1d1a-11eb-8dee-80fc600decfa.png)
![Repository Structure](https://user-images.githubusercontent.com/1147445/97865027-991b7200-1d1a-11eb-927e-3f5580a7f5b5.png)

---

## 🎬 Movies.API

- ASP.NET Core Web API secured using **IdentityServer4** with **OAuth2 (client_credentials)**.
- Protected endpoints accept JWTs issued by IdentityServer4.
- Validates the access token to serve movie data.

---

## 🎥 Movies.MVC

- ASP.NET Core MVC web application as an **interactive OpenID Connect client**.
- Authenticates users via IdentityServer4.
- Uses Authorization Code flow to obtain **JWT tokens** and access protected resources.

---

## 🆔 Identity Server

- Implements a centralized **Identity Provider** using **IdentityServer4**.
- Supports OAuth2 and OpenID Connect protocols.
- Issues tokens for authenticated users and services.
- Acts as the single sign-on entry point for all applications.

---

## 🚪 Ocelot API Gateway

- Routes client requests to backend services securely.
- Accepts **Bearer tokens (JWT)** from clients.
- Forwards the token to protected services (e.g., Movies.API).
- Performs authentication via IdentityServer4 in the authorization pipeline.

Includes **claim-based authorization** for access control.

---

## 🚀 Installation & Running

Follow these steps to set up the development environment:

1. **Check run profiles:** Right-click each project, go to **Properties > Debug**, ensure the **Launch profile is set to 'Project'** and matches the port in the overview diagram.
2. **Set default launch:** Change the default run profile from **IIS Express** to **Project** for each project.
3. **Enable multiple startups:** Right-click the solution → **Properties** → **Multiple startup projects** → Set all 4 apps to **Start**.
4. Click **Start** (or press F5) to run the solution.

This will open 4 console windows (for the microservices) and 1 browser window for the client.

- Client App: `https://localhost:5002/`

### 🔑 Login Credentials

You can use the following test accounts to log in:

- **alice / a1**
- **bob / b1**

---

## 📁 Repository Structure

```
/Movies.API            # Secured API using IdentityServer4
/Movies.MVC            # OpenID Connect interactive client
/IdentityServer        # Centralized authentication and identity service
/OcelotGateway         # API Gateway using Ocelot
```

---

## 🧰 Technologies Used

- ASP.NET Core
- IdentityServer4
- OAuth2 / OpenID Connect
- Ocelot API Gateway
- JWT (JSON Web Tokens)
- Claim-based Authorization

---

## 📄 License

This project is for educational purposes only.
