---
title: Identitäts Modelle und Authentifizierung
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Learn about the different identity models in Microsoft Teams such as Cloud, Synchronized, and Federated. Also learn about multi-factor authentication.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 330a197f2e042ee8d87e294f9ff822c6bf6d5ac6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121565"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Identitätsmodelle und Authentifizierung in Microsoft Teams
==========================================

Microsoft Teams supports all the identity models that are available with Microsoft 365 and Office 365. Supported identity models include:

-   **Cloud-Identität**: in diesem Modell wird ein Benutzer in Microsoft 365 oder Office 365 erstellt und verwaltet und in Azure Active Directory gespeichert, und das Kennwort wird von Azure Active Directory überprüft.

-   **Synchronized Identity**: In this model, the user identity is managed in an on-premises server, and the accounts and password hashes are synchronized to the cloud. The user enters the same password on-premises as they do in the cloud, and at sign-in the password is verified by Azure Active Directory. This model uses the Microsoft Azure Active Directory Connect Tool.

-   **Federated Identity**: This model requires a synchronized identity with the user password is verified by the on-premises identity provider. With this model, the password hash does not need to be synchronized to Azure AD, and Active Directory Federation Services (ADFS) or a third-party identity provider is used to authenticate users against the on-premises Active Directory.

<a name="configurations"></a>Konfigurationen
--------------

Depending on your organization's decisions of which identity model to implement and use, the implementation requirements may vary. Refer to the requirements table below to ensure that your deployment meets these prerequisites. If you have already deployed Microsoft 365 or Office 365 and have already implemented the identity and authentication method, you may skip these steps.


|Identitätsmodell |Bereitstellungscheckliste  |Weitere Informationen  |
|---------|---------|---------|
|Alle     |<ol type="1"><li>Vergleichen von Microsoft 365-und Office 365-Plan Optionen und Anfordern eines Abonnements</li><li>Erstellen einer Microsoft 365-oder Office 365-Organisation</li><li>Zuweisen von Microsoft 365-oder Office 365-Lizenzen zum Mandanten</li><li>Konfigurieren von Domänen und Administratorbenutzern</li><li>Fortfahren mit identitätsmodellspezifischen Anweisungen</li></ol>          |<ul style="list-style-type:none"><li>[Optionen für Microsoft 365 und Office 365-Plan](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Vergleichen von Microsoft 365-Apps für Business-Pläne](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Verwalten von Abonnementlizenzen](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Hinzufügen von Lizenzen zu einem Abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Einrichten von Microsoft 365 for Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Hinzufügen einer Domäne und von Benutzern zu Office 365](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Hinweis: Wenn Sie Hilfe benötigen, steht Ihnen [das Microsoft](https://go.microsoft.com/fwlink/?linkid=854618) -Programm zur Verfügung.</li></ul>          |
|Cloud-Identität     |<ol type="1"><li>Erstellen von Benutzern mit Microsoft 365 Admin Center</li></ol>           |<ul style="list-style-type:none"><li>[Benutzer einzeln oder in Massen hinzufügen](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Synchronisierte Identität     |<ol type="1"><li>Installieren von Azure AD Connect</li><li>Konfigurieren der Verzeichnissynchronisierung</li><li>Erstellen von Benutzern mit lokalen Active Directory-Verwaltungstools</li></ol>         |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Hinweis: Kenn Wort Hashes müssen für Microsoft 365 und Office 365 synchronisiert werden, um eine Authentifizierung durchzuführen.</li></ul>         |
|Partneridentität    |<ol type="1"><li>Installieren von Azure AD Connect</li><li>Konfigurieren der Verzeichnissynchronisierung</li><li>Installieren und Konfigurieren eines Partneridentitätsanbieters (empfohlen: AD FS)</li><li>Erstellen von Benutzern mit lokalen Active Directory-Verwaltungstools</li></ol>           |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planen der AD FS-Bereitstellung](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Prüfliste: Bereitstellen der Verbundserverfarm unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Konfigurieren des Extranetzugriffs für AD FS unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Einrichten einer Vertrauensstellung zwischen AD FS und Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Überprüfen und Verwalten von einmaligem Anmelden mit AD FS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD-Verbund – Kompatibilitätsliste](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Hinweis: Kennworthashes müssen nicht mit Azure Active Directory synchronisiert werden.</li></ul>         |

Weitere Informationen finden Sie unter [Auswählen eines Anmelde Modells](https://go.microsoft.com/fwlink/?linkid=854626) und [Grundlegendes zu Identitäts Modellen und Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) -Führungslinien.


<a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung
----------------------------

Microsoft 365 and Office 365 plans support Multi-Factor Authentication (MFA) that increases the security of user logins to services. With MFA, users are required to acknowledge a phone call, text message, or an app notification on their smartphone after correctly entering their password. Only after this second authentication factor has been satisfied, can a user sign in.

Multi Factor authentication is supported with any Microsoft 365 or Office 365 plan that includes Microsoft Teams. The subscription plans that include Microsoft Teams are discussed later in the Licensing section below.

Once the users are enrolled for MFA, the next time a user signs in, they will see a message that asks them to set up their second authentication factor. Supported authentication methods are:


|Mandantentyp  |Verfügbare Optionen für den zweiten MFA-Faktor  |Notizen  |
|---------|---------|---------|
|**Nur Cloud**     |MFA für Microsoft 365 oder Office 365 <ul><li>Telefonanruf</li><li>SMS</li><li>Benachrichtigung in einer mobilen App</li><li>Prüfcode in einer mobilen App</li></ul>        | |
|**Hybridsetup (Modell für synchronisierte Identität oder Partneridentität)**     |<ul><li>MFA für Microsoft 365 oder Office 365</li><li>Azure MFA-Modul (in AD FS integriert)</li><li>Physische oder virtuelle Smartcard (in AD FS integriert)</li></ul>         |Hinweis: zusätzliche MFA-Lösungen sind mit [Azure AD Identity Provider Compatibility docs](https://www.microsoft.com/download/details.aspx?id=56843) verfügbar         |
