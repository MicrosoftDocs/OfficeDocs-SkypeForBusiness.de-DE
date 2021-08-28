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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Hier erhalten Sie Informationen zu den verschiedenen Identitätsmodellen für Microsoft Teams, z. B. nur Cloud und Hybrid. Außerdem erhalten Sie Informationen zur mehrstufigen Authentifizierung.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7123a2456da9e8a18c3d665e41e15cf44550a6da
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598519"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Identitätsmodelle und Authentifizierung für Microsoft Teams

Microsoft Teams unterstützt alle Identitätsmodelle, die für Microsoft 365 und Office 365 zur Verfügung stehen. Dazu gehören:

- **Nur in der** Cloud: Benutzerkonten werden in einem Microsoft 365 Oder Office 365 erstellt und verwaltet und in Azure Active Directory (Azure AD) gespeichert. Anmeldeinformationen für Benutzer (Kontoname und Kennwort) werden von Azure AD überprüft.

- **Hybrid:** Benutzerkonten werden in der Regel in einer lokalen AD DS-Gesamtstruktur (Active Directory Domain Services) verwaltet. Je nach Konfiguration kann die Überprüfung der Anmeldeinformationen von Azure AD, AD DS oder einem Verbundidentitätsanbieter durchgeführt werden. Dieses Modell verwendet die Verzeichnissynchronisierung von AD DS zu Azure AD mit Azure AD Verbinden.

Weitere Informationen finden Sie unter [Microsoft 365 und Azure AD.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Konfigurationen

Je nachdem, welches Identitätsmodell und welche Konfiguration Sie in Ihrer Organisation verwenden, können die Implementierungsschritte variieren.

Wenn Sie noch kein Identitätsmodell und ein Microsoft 365 oder Office 365 bereitgestellt haben, verwenden Sie diese Tabelle. 

|Identitätsmodell |Bereitstellungscheckliste  |Weitere Informationen  |
|---------|---------|---------|
|All     |<ol type="1"><li>Vergleichen Microsoft 365 und Office 365, und beziehen Sie ein Abonnement und einen Mandanten.</li><li>Erstellen Sie Microsoft 365 oder Office 365 Organisation für Ihren Mandanten.</li><li>Erwerben Microsoft 365 oder Office 365 lizenzen für den Mandanten</li><li>Konfigurieren Sie Domänen und Administratorbenutzerkonten.</li></ol>  |<ul><li>[Office 365 von Planoptionen](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Vergleich Microsoft 365 for Business-Pläne](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Kaufen oder Entfernen von Abonnementlizenzen](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Hinzufügen von Lizenzen zu einem Abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Einrichten von Microsoft 365 Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Hinzufügen einer Domäne mit dem Setup-Assistenten](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) steht Ihnen zur Unterstützung zur Verfügung.  |
|Cloudidentität     |<ul><li>Erstellen von Benutzerkonten mit Microsoft 365 Admin Center</li></ul> |<ul style="list-style-type:none"><li>[Hinzufügen von Benutzern und Zuweisen von Lizenzen](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Hybrididentität     |<ol type="1"><li>Installieren Sie Azure AD Verbinden.</li><li>Konfigurieren Sie die Verzeichnissynchronisierung.</li><li>Verwalten Sie Benutzer und Gruppen mit AD DS-Tools.</li></ol> |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Hybrididentität mit Verbundauthentifizierung    |<ol type="1"><li>Installieren und konfigurieren Sie einen Verbundidentitätsanbieter wie AD FS.</li><li>Installieren Sie Azure AD Verbinden und konfigurieren Sie die Verzeichnissynchronisierung und Verbundauthentifizierung.</li><li>Verwalten Sie Benutzer und Gruppen mit AD DS-Tools.</li></ol> |<ul><li>[Planen der AD FS-Bereitstellung](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Prüfliste: Bereitstellen der Verbundserverfarm unter Windows Server 2012 R2](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Konfigurieren des Extranetzugriffs für AD FS unter Windows Server 2012 R2](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Einrichten einer Vertrauensstellung zwischen AD FS und Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Überprüfen und Verwalten von einmaligem Anmelden mit AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Einrichten der Verzeichnissynchronisierung](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Kennwörter sind die häufigste Authentifizierungsmethode für die Anmeldung an einem Computer oder Onlinedienst, sind aber auch am anfälligsten. Benutzer können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen bei verschiedenen Computern und Diensten verwenden. 

Wenn Sie zusätzliche Sicherheit für Anmeldungen bereitstellen möchten, verwenden Sie die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), für die sowohl ein Kennwort als auch eine zusätzliche Überprüfungsmethode erforderlich ist, z. B.:

- Eine text message sent to a phone that requires the user to type a verification code.
- Ein Telefonanruf.
- Die Microsoft Authenticator-Smartphone-App.
- Andere Methoden sind für Hybrididentität und Verbundauthentifizierung verfügbar.

MFA wird von allen Microsoft 365-Office 365 unterstützt, die Microsoft Teams. Es wird dringend empfohlen, mindestens MFA für Die Konten zu [benötigen,](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)denen Administratorrollen zugewiesen sind, z. B. Teams Dienstadministrator.

Außerdem sollten Sie MFA für Ihre Benutzer verfügbar machen. Sobald Ihre Benutzer für MFA registriert sind, sehen sie bei der nächsten Anmeldung eine Meldung, in der sie zum Einrichten ihrer zusätzlichen Überprüfungsmethode gefragt werden. 

Weitere Informationen finden Sie unter [Mehrstufige Authentifizierung für Microsoft 365.](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)