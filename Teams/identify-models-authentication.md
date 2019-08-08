---
title: Identitätsmodelle und Authentifizierung in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Hier erhalten Sie Informationen zu den verschiedenen Identitätsmodellen in Microsoft Teams, beispielsweise „Cloud-Identität“, „Synchronisierte Identität“ und „Partneridentität“. Außerdem erhalten Sie Informationen zur mehrstufigen Authentifizierung.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabd8a853202f49fb66c9b796a84beff554afdb5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241904"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Identitätsmodelle und Authentifizierung in Microsoft Teams
==========================================

Microsoft Teams unterstützt alle Identitätsmodelle, die in Office 365 verfügbar sind. Zu den unterstützten Identitätsmodellen gehören:

-   **Cloud-Identität**: In diesem Modell wird ein Benutzer in Office 365 erstellt und verwaltet und in Azure Active Directory gespeichert. Das Kennwort wird von Azure Active Directory überprüft.

-   **Synchronisierte Identität**: In diesem Modell wird die Benutzeridentität auf einem lokalen Server verwaltet, und die Konten und Kennworthashes werden mit der Cloud synchronisiert. Der Benutzer gibt lokal das gleiche Kennwort wie in der Cloud ein, und bei der Anmeldung wird das Kennwort von Azure Active Directory überprüft. Bei diesem Modell wird das Microsoft Azure Active Directory Connect-Tool verwendet.

-   **Partneridentität**: Dieses Modell erfordert, dass eine synchronisierte Identität mit dem Benutzerkennwort durch den lokalen Identitätsanbieter überprüft wird. Bei diesem Modell muss der Kennworthash nicht mit Azure AD synchronisiert werden, und die Active Directory-Verbunddienste (Active Directory Federation Services, AD FS) oder ein Drittanbieter-Identitätsanbieter werden verwendet, um Benutzer gegenüber der lokalen Active Directory-Instanz zu authentifizieren.

<a name="configurations"></a>Konfigurationen
--------------

Abhängig von den Entscheidungen Ihrer Organisation über das zu implementierende und zu verwendende Identitätsmodell können unterschiedliche Implementierungsanforderungen gelten. Sehen Sie sich die folgende Anforderungstabelle an, um sicherzustellen, dass Ihre Bereitstellung diese Voraussetzungen erfüllt. Wenn Sie bereits Office 365 bereitgestellt und die Identitäts- und Authentifizierungsmethode implementiert haben, können Sie diese Schritte überspringen.


|Identitätsmodell |Bereitstellungscheckliste  |Weitere Informationen  |
|---------|---------|---------|
|Alle     |<ol type="1"><li>Vergleichen der Optionen für Office 365-Pläne und Abschließen eines Abonnements</li><li>Erstellen eines Office 365-Mandanten</li><li>Zuweisen von Office 365-Lizenzen zu dem Mandanten</li><li>Konfigurieren von Domänen und Administratorbenutzern</li><li>Fortfahren mit identitätsmodellspezifischen Anweisungen</li></ol>          |<ul style="list-style-type:none"><li>[Optionen für Office 365-Pläne](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Vergleichen der Pläne für Office 365 Business](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Erwerben von Lizenzen für Ihr Office 365 Business-Abonnement](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Hinzufügen von Lizenzen zu einem Abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Einrichten von Office 365 Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Hinzufügen einer Domäne und von Benutzern zu Office 365](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Hinweis: Wenn Sie Unterstützung benötigen, steht Ihnen [das Microsoft FastTrack-Team für Office 365](https://go.microsoft.com/fwlink/?linkid=854618) zur Verfügung.</li></ul>          |
|Cloud-Identität     |<ol type="1"><li>Erstellen von Benutzern über das Office 365-Verwaltungsportal</li></ol>           |<ul style="list-style-type:none"><li>[Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Synchronisierte Identität     |<ol type="1"><li>Installieren von Azure AD Connect</li><li>Konfigurieren der Verzeichnissynchronisierung</li><li>Erstellen von Benutzern mit lokalen Active Directory-Verwaltungstools</li></ol>         |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Hinweis: Kennworthashes müssen synchronisiert werden, damit Office 365 die Authentifizierung ausführt.</li></ul>         |
|Partneridentität    |<ol type="1"><li>Installieren von Azure AD Connect</li><li>Konfigurieren der Verzeichnissynchronisierung</li><li>Installieren und Konfigurieren eines Partneridentitätsanbieters (empfohlen: AD FS)</li><li>Erstellen von Benutzern mit lokalen Active Directory-Verwaltungstools</li></ol>           |<ul style="list-style-type:none"><li>[Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planen der AD FS-Bereitstellung](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Prüfliste: Bereitstellen der Verbundserverfarm unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Konfigurieren des Extranetzugriffs für AD FS unter Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Einrichten einer Vertrauensstellung zwischen AD FS und Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Überprüfen und Verwalten von einmaligem Anmelden mit AD FS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD-Verbund – Kompatibilitätsliste](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Hinweis: Kennworthashes müssen nicht mit Azure Active Directory synchronisiert werden.</li></ul>         |

Zusätzliche Details finden Sie in den Leitfäden [Auswählen eines Anmeldemodells für Office 365](https://go.microsoft.com/fwlink/?linkid=854626) und [Grundlegendes zu Office 365-Identitäten und Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).

<a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung
----------------------------

Office 365-Pläne unterstützen die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), die die Sicherheit der Benutzeranmeldungen bei Office 365-Diensten erhöht. Bei MFA für Office 365 müssen Benutzer nach der Eingabe des richtigen Kennworts einen Telefonanruf, eine SMS oder eine App-Benachrichtigung auf ihrem Smartphone bestätigen. Erst nach der erfolgreichen Überprüfung dieses zweiten Authentifizierungsfaktors können sich die Benutzer anmelden.

Die mehrstufige Authentifizierung wird mit einem Office 365-Plan unterstützt, der Microsoft Teams umfasst. Die Office 365-Abonnement Pläne, die Microsoft Teams enthalten, werden später im Abschnitt Lizenzierung weiter unten erläutert.

Wenn sich die Benutzer für MFA registriert haben, sehen sie bei der nächsten Anmeldung eine Meldung, in der sie aufgefordert werden, ihren zweiten Authentifizierungsfaktor einzurichten. Die folgenden Authentifizierungsmethoden werden unterstützt:


|Mandantentyp  |Verfügbare Optionen für den zweiten MFA-Faktor  |Notizen  |
|---------|---------|---------|
|**Nur Cloud**     |MFA für Office 365 <ul><li>Telefonanruf</li><li>SMS</li><li>Benachrichtigung in einer mobilen App</li><li>Prüfcode in einer mobilen App</li></ul>        |[Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Hybridsetup (Modell für synchronisierte Identität oder Partneridentität)**     |<ul><li>MFA für Office 365</li><li>Azure MFA-Modul (in AD FS integriert)</li><li>Physische oder virtuelle Smartcard (in AD FS integriert)</li></ul>         |Hinweis: Zusätzliche MFS-Lösungen sind verfügbar über [Identitätsanbieter, die mit dem Azure AD-Verbund kompatibel sind](https://go.microsoft.com/fwlink/p/?LinkId=510953).         |
