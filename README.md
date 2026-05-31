# SoftMatrix.PBIRS.PowerBIClient
1. Requirement Overview

When integrating an on-premises Power BI Report Server with a third-party application system, we need to address the Single Sign-On (SSO) challenge between the application and Power BI Report Server. Specifically, the authenticated user identity from the third-party application must be mapped to a corresponding Windows account, and all access to Power BI Report Server must be performed under the security context of that Windows account.

2. Solution

To address this requirement, we developed an HTTP reverse proxy that receives requests from the third-party application destined for Power BI Report Server. The reverse proxy leverages the Windows Server Claims to Windows Token Service (C2WTS) to map the authenticated user identity from the third-party application to a corresponding Windows account.

The reverse proxy then impersonates the mapped Windows account when forwarding requests to Power BI Report Server and returns the responses from Power BI Report Server back to the third-party application. This approach enables seamless Single Sign-On while preserving user-specific authorization and access control within Power BI Report Server.
