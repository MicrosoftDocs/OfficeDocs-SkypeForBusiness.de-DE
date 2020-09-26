---
title: Identitäts Modelle und Authentifizierung für Microsoft Teams
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
description: Informieren Sie sich über die unterschiedlichen Identitäts Modelle für Microsoft Teams wie Cloud-only und Hybrid. Erfahren Sie auch mehr über die mehrstufige Authentifizierung.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277115"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Identitäts Modelle und Authentifizierung für Microsoft Teams

Microsoft Teams unterstützt alle Identitäts Modelle, die in Microsoft 365 und Office 365 zur Verfügung stehen, einschließlich:

- **Nur**in der Cloud: Benutzerkonten werden in Microsoft 365 oder Office 365 erstellt und verwaltet und in Azure Active Directory (Azure AD) gespeichert. Anmeldeinformationen für Benutzer (Konto Name und Kennwort) werden von Azure AD überprüft.

- **Hybrid**: Benutzerkonten werden in der Regel in einer lokalen Active Directory-Domänendienste (AD DS)-Gesamtstruktur verwaltet. Je nach Konfiguration kann die Validierung von Anmeldeinformationen von Azure AD, AD DS oder einem Verbund Identitätsanbieter durchgeführt werden. Dieses Modell verwendet die Verzeichnissynchronisierung von AD DS zu Azure AD mit Azure AD Connect.

Weitere Informationen finden Sie unter [Microsoft 365 Identity Models und Azure AD](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Konfigurationen

Je nach den Entscheidungen ihrer Organisation, welches Identitätsmodell und welche Konfiguration Sie verwenden, können die Implementierungsschritte unterschiedlich sein.

Wenn Sie nicht bereits Microsoft 365 oder Office 365 und ein Identitätsmodell bereitgestellt haben, verwenden Sie diese Tabelle. 

|Identitätsmodell |Bereitstellungscheckliste  |Weitere Informationen  |
|---------|---------|---------|
|All     |<ol type="1"><li>Vergleichen Sie die Microsoft 365-und Office 365-Planoptionen, und beziehen Sie ein Abonnement und einen Mandanten.</li><li>Erstellen Sie eine Microsoft 365-oder Office 365-Organisation für Ihren Mandanten.</li><li>Erwerben von Microsoft 365-oder Office 365-Lizenzen für den Mandanten</li><li>Konfigurieren von Domänen und Administratorbenutzerkonten</li></ol>  |<ul><li>[Office 365-Planoptionen](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Vergleich von Microsoft 365 for Business-Plänen](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Kaufen oder Entfernen von Abonnementlizenzen](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Hinzufügen von Lizenzen zu einem Abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Einrichten von Microsoft 365 for Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Hinzufügen einer Domäne mit dem Setup-Assistenten](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft](https://www.microsoft.com/fasttrack/microsoft-365) -Soforthilfe steht Ihnen zur Verfügung.  |
|Cloud-Identität     |<ul><li>Erstellen von Benutzerkonten mit dem Microsoft 365 Admin Center</li></ul> |<ul style="list-style-type:none"><li>[Hinzufügen von Benutzern und Zuweisen von Lizenzen](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Hybrid Identität     |<ol type="1"><li>Installieren Sie Azure AD Connect.</li><li>Konfigurieren der Verzeichnissynchronisierung</li><li>Verwalten von Benutzern und Gruppen mit den AD DS-Tools</li></ol> |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Hybrid Identität mit Verbundauthentifizierung    |<ol type="1"><li>Installieren und konfigurieren Sie einen Verbund Identitätsanbieter wie AD FS.</li><li>Installieren Sie Azure AD Connect, und konfigurieren Sie die Verzeichnissynchronisierung und die Verbundauthentifizierung.</li><li>Verwalten von Benutzern und Gruppen mit den AD DS-Tools</li></ol> |<ul><li>[Planen der AD FS-Bereitstellung](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Prüfliste: Bereitstellen der Verbundserverfarm unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Konfigurieren des Extranetzugriffs für AD FS unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Einrichten einer Vertrauensstellung zwischen AD FS und Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Überprüfen und Verwalten von einmaligem Anmelden mit AD FS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Einrichten der Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Kennwörter stellen die häufigste Authentifizierungsmethode für die Anmeldung bei einem Computer oder Onlinedienst dar, sind aber auch am schwächsten. Personen können einfache Kennwörter auswählen und dieselben Kennwörter für mehrere Anmeldungen für verschiedene Computer und Dienste verwenden. 

Wenn Sie eine zusätzliche Sicherheitsstufe für Anmeldungen bereitstellen möchten, verwenden Sie die mehrstufige Authentifizierung (MFA), die sowohl ein Kennwort als auch eine zusätzliche Überprüfungsmethode erfordert, wie beispielsweise:

- Eine an ein Telefon gesendete Textnachricht, für die der Benutzer einen Bestätigungscode eingeben muss.
- Ein Telefonanruf.
- Die Microsoft Authenticator-Smart Phone-app.
- Andere Methoden, die mit Hybrid Identität und Verbundauthentifizierung verfügbar sind.

MFA wird mit einem Microsoft 365-oder Office 365-Plan unterstützt, der Microsoft Teams umfasst. Es wird dringend empfohlen, dass Sie mindestens MFA für diese Konten benötigen, denen [Administratorrollen zugewiesen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)sind, beispielsweise Team Dienstadministrator.

Sie sollten auch MFA für Ihre Benutzer bereitzustellen. Sobald Ihre Benutzer für MFA registriert sind, wird bei der nächsten Anmeldung eine Meldung angezeigt, in der Sie aufgefordert werden, ihre zusätzliche Überprüfungsmethode einzurichten. 

Weitere Informationen finden Sie unter [mehrstufige Authentifizierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
