# Identity, Governance, Privacy, and Compliance Features
## Contents Page

## Azure Identity Services
### Authentication and Authorization
- Authentication: is the process of establishing the identity of a person or service that wants to access a resource
- It involves asking for legitimate credentials and provides the basis for creating a security principal for identity and access control
- Authorization: is the process of establishing what level of access an authenticated person or service has
- It specifies what data they're allowed to access and what they can do with it

![Authentication and Authorization](img/AuthN-AuthZ.png)
### Azure Active Directory (Azure AD)
- Active Directory: gives organizations the ability to manage multiple on-prem infrastructure components and systems by using a single identity per user
- For on-prem environments, Active Directory running on Windows Server provides an identity and access management service that's managed by your own organization
- Azure AD: cloud-based identity and access management service, you control the identity accounts, but Microsoft ensures that the service is available globally
- When you connect Active Directory with Azure AD, Microsoft can help protect you by detecting suspicious sign-in attempts at no extra cost
- Azure AD is for:
  - IT Admins: use Azure AD to control access to applications and resources based on their business requirements
  - App Devs: use Azure AD to provide a standards-based approach for adding functionality to applications
  - Users: can manage their identities (self-service password reset)
  - Online Service Subscribers: Microsoft 365, Office 365, Azure, and Dynamics CRM Online tenant is automatically an Azure AD tenant. A tenant is a representation of an organization (own identity)
- Azure AD provides services such as:
  - Authentication: includes verifying identity to access applications and resources. It also includes providing functionality such as self-service password reset, MFA, list of banned passwords, and smart lockout services
  - Single Sign-On: enables you to remember only one username and one password to access multiple applications
  - Application Management: manage your cloud and on-premises apps by using Azure AD. Features like Application Proxy, SaaS apps, the My Apps portal, and SSO provide a better user experience.
  - Device Management: registration enables devices to be managed through tools like Microsoft Intune. It also allows for device-based Access policies to restrict access to known devices, regardless of the requesting user account
- Azure AD helps users access both external and internal resources
- External resources might include Microsoft Office 365, the Azure portal (other SaaS apps)
- Internal resources might include apps on your corporate network and intranet, along with any cloud applications developed within your organization
- Azure AD Connect synchronizes user identities between on-prem Active Directory and Azure AD
- Azure AD Connect synchronizes changes between both identity systems, so you can use features like SSO and MFA

![Active Directory](img/Azure-AD.png)
### 