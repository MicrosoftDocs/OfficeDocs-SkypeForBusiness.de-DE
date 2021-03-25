---
title: Identitätsmodelle und Authentifizierung für Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
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
description: Erfahren Sie mehr über die verschiedenen Identitätsmodelle für Microsoft Teams, z. B. Cloud-only und Hybrid. Erfahren Sie auch mehrstufige Authentifizierung.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dff34a6a56294c8c62295e143f753777875bfbda
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112361"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Identitätsmodelle und Authentifizierung für Microsoft Teams

Microsoft Teams unterstützt alle Identitätsmodelle, die mit Microsoft 365 und Office 365 verfügbar sind, wie:

- **Nur in** der Cloud: Benutzerkonten werden in Microsoft 365 oder Office 365 erstellt und verwaltet und in Azure Active Directory (Azure AD) gespeichert. Anmeldeinformationen für Benutzer (Kontoname und Kennwort) werden von Azure AD überprüft.

- **Hybrid:** Benutzerkonten werden in der Regel in einer lokalen Active Directory Domain Services (AD DS)-Gesamtstruktur verwaltet. Je nach Konfiguration kann die Überprüfung der Anmeldeinformationen von Azure AD, AD DS oder einem Verbundidentitätsanbieter durchgeführt werden. Dieses Modell verwendet die Verzeichnissynchronisierung von AD DS zu Azure AD mit Azure AD Connect.

Weitere Informationen finden Sie unter [Microsoft 365-Identitätsmodelle und Azure AD.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Konfigurationen

Je nach den Entscheidungen Ihrer Organisation, welches Identitätsmodell und welche Konfiguration Sie verwenden, können die Implementierungsschritte variieren.

Wenn Sie Microsoft 365 oder Office 365 und ein Identitätsmodell noch nicht bereitgestellt haben, verwenden Sie diese Tabelle. 

|Identitätsmodell |Bereitstellungscheckliste  |Weitere Informationen  |
|---------|---------|---------|
|All     |<ol type="1"><li>Vergleichen Sie die Optionen für Microsoft 365- und Office 365-Pläne, und rufen Sie ein Abonnement und einen Mandanten ab.</li><li>Erstellen Sie eine Microsoft 365- oder Office 365-Organisation für Ihren Mandanten.</li><li>Erwerben von Microsoft 365- oder Office 365-Lizenzen für den Mandanten</li><li>Konfigurieren Sie Domänen und Administratorbenutzerkonten.</li></ol>  |<ul><li>[Office 365-Planoptionen](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Vergleichen von Microsoft 365 Business-Plänen](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Kaufen oder Entfernen von Abonnementlizenzen](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Hinzufügen von Lizenzen zu einem Abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Einrichten von Microsoft 365 Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Hinzufügen einer Domäne mit dem Setup-Assistenten](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) steht Ihnen zur Verfügung.  |
|Cloudidentität     |<ul><li>Erstellen von Benutzerkonten im Microsoft 365 Admin Center</li></ul> |<ul style="list-style-type:none"><li>[Hinzufügen von Benutzern und Zuweisen von Lizenzen](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Hybrididentität     |<ol type="1"><li>Installieren Sie Azure AD Connect.</li><li>Konfigurieren sie die Verzeichnissynchronisierung.</li><li>Verwalten Sie Benutzer und Gruppen mit AD DS-Tools.</li></ol> |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Hybrididentität mit Verbundauthentifizierung    |<ol type="1"><li>Installieren und Konfigurieren eines Verbundidentitätsanbieters wie AD FS.</li><li>Installieren Sie Azure AD Connect, und konfigurieren Sie die Verzeichnissynchronisierung und die Verbundauthentifizierung.</li><li>Verwalten Sie Benutzer und Gruppen mit AD DS-Tools.</li></ol> |<ul><li>[Planen der AD FS-Bereitstellung](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Prüfliste: Bereitstellen der Verbundserverfarm unter Windows Server 2012 R2](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Konfigurieren des Extranetzugriffs für AD FS unter Windows Server 2012 R2](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Einrichten einer Vertrauensstellung zwischen AD FS und Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Überprüfen und Verwalten von einmaligem Anmelden mit AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Einrichten der Verzeichnissynchronisierung](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Kennwörter sind die am häufigsten verwendeten Authentifizierungsmethoden für die Anmeldung bei einem Computer oder Onlinedienst, sind aber auch am anfälligsten. Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen bei verschiedenen Computern und Diensten verwenden. 

Verwenden Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), die sowohl ein Kennwort als auch eine zusätzliche Überprüfungsmethode erfordert, um ein zusätzliches Sicherheitsniveau für Anmeldungen zu gewährleisten, z. B.:

- Eine an ein Telefon gesendete Textnachricht, in der der Benutzer einen Überprüfungscode eingeben muss.
- Ein Telefonanruf.
- Die Microsoft Authenticator-Smartphone-App.
- Weitere Methoden, die mit Hybrididentität und Verbundauthentifizierung verfügbar sind.

MFA wird mit jedem Microsoft 365- oder Office 365-Plan unterstützt, der Microsoft Teams enthält. Es wird dringend empfohlen, dass Sie mindestens MFA für konten benötigen, denen Administratorrollen [zugewiesen](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)sind, z. B. Der Dienstadministrator von Teams.

Sie sollten MFA auch für Ihre Benutzer rollouten. Sobald Ihre Benutzer für MFA registriert sind, wird bei der nächsten Anmeldung eine Meldung angezeigt, in der sie zum Einrichten ihrer zusätzlichen Überprüfungsmethode gefragt werden. 

Weitere Informationen finden Sie unter [Mehrstufige Authentifizierung für Microsoft 365.](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)