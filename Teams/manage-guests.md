---
title: Verwalten des Gastzugriffs in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie Ihre ersten Teams und Kanäle erstellen, die Nutzung und das Feedback überwachen und Ressourcen für die Planung Ihres organisationsweiten Rollouts erhalten.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4751f274e4bc7a874c1469041787d7d145c11bb8
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637664"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Verwalten des Gastzugriffs in Microsoft Teams
======================================

> [!IMPORTANT]
> Möglicherweise müssen Sie einige Stunden warten, bis Ihre Änderungen wirksam werden. 

**Guest** ist ein Benutzertyp in Microsoft Teams, der in allen Microsoft 365 Business Standard, Office 365 Enterprise, Microsoft 365 Business Basic und Office 365 Education-Abonnements enthalten ist. Es ist keine zusätzliche Microsoft 365-oder Office 365-Lizenz erforderlich. Weitere Informationen finden Sie unten unter [Gastzugriff-Lizenzierung](#guest-access-licensing-limits) .

Der Gastzugriff auf Microsoft Teams ist eine Einstellung auf Mandantenebene, die standardmäßig deaktiviert ist. Details zum Aktivieren des Gastzugriffs finden Sie unter Aktivieren oder Deaktivieren des Gast [Zugriffs auf Teams](set-up-guests.md)oder verwenden der Checkliste für den [Gastzugriff](guest-access-checklist.md) , um Sie durch das Setup zu führen.

Nachdem Gastzugriff aktiviert ist, können Sie die Einstellungen für Gäste mithilfe der Steuerelemente konfigurieren, die unter [Verwalten von Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md) und [Verwalten von Teams während des Übergangs zum neuen Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md)beschrieben sind.     
    
IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten und Berichte über Gastbenutzeraktivität abrufen. Diese Steuerelemente stehen im Team Admin Center zur Verfügung. Der Inhalt und die Aktivitäten von Gastbenutzern unterliegen dem gleichen Compliance-und Überwachungs Schutz wie der restliche Microsoft 365 oder Office 365.

Team Besitzer können neue Gäste einladen und ihren Teams im Team Admin Center vorhandene Verzeichnis Gastbenutzer hinzufügen. Identifizieren Sie Gastbenutzer auf der Seite **Teams**  >  **Manage Teams** , und legen Sie die Kanal bezogenen Funktionen für Gäste auf der Seite **organisationsweite Einstellungen**  >  **Gastzugriff** fest. Zu den Einstellungen gehören das Erstellen, aktualisieren und Löschen von Kanälen, wie in der folgenden Abbildung gezeigt.

![Einstellungen von Gastberechtigungen in Teams](media/manage-guest-access-image1.png)
  
Sie können das Azure Active Directory (Azure AD)-Portal verwenden, um Gäste und deren Zugriff auf Microsoft 365-oder Office 365-und Teamressourcen zu verwalten. Die Teams-Einstellung für Gastzugriff nutzt die Azure AD-B2B-Funktionen (Business-to-Business) zur Zusammenarbeit als zugrunde liegende Infrastruktur zum Speichern der Informationen über Sicherheitsprinzipien, wie zum Beispiel Einstellungen für Identitätseigenschaften, Mitgliedschaften und für die mehrstufige Authentifizierung. Weitere Informationen zu Azure AD B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://go.microsoft.com/fwlink/p/?linkid=853011) und [Häufig gestellte Fragen zur Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams berücksichtigt immer externe Azure AD-Einstellungen, um das Hinzufügen von Gästen zum Mandanten zuzulassen bzw. zu verhindern. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Einschränkungen für Gastzugriffs Lizenzen

Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Allerdings basiert die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, darauf, was gemäß Ihrer Azure AD-Lizenzierung zulässig ist – in der Regel 5 Gäste pro lizenziertem Benutzer. Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

Aufgrund dieser Lizenzierungseinschränkungen (und um ihren Mandanten auf dem neuesten Stand zu halten) sollten Sie den Gastzugriff in regelmäßigen Abständen überprüfen, um Benutzer zu identifizieren, die Zugriff haben, die Sie nicht mehr benötigen. Mit Azure AD können Sie eine Zugriffsüberprüfung für Mitglieder einer Gruppe oder Benutzer, die einer Anwendung zugewiesen sind, erstellen. Das Erstellen regelmäßiger Zugriffsüberprüfungen kann Zeit sparen. Wenn Sie Benutzer, die Zugriff auf eine Anwendung haben oder Mitglied einer Gruppe sind, routinemäßig überprüfen, können Sie die Häufigkeit dieser Überprüfungen definieren. 

Sie können selbst eine Überprüfung des Gastzugriffs durchführen, Gäste bitten, ihre eigene Mitgliedschaft zu überprüfen oder den Besitzer einer Anwendung bzw. einen Entscheidungsträger bitten, die Zugriffsüberprüfung durchzuführen. Verwenden Sie das Azure-Portal, um Bewertungen von Gastzugriffen durchzuführen. Weitere Informationen finden Sie unter [Verwalten des Gastzugriffs mit Azure AD-Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Voraussetzungen für Azure AD Access-Rezensionen

Zugriffsüberprüfungen sind mit der Premium P2-Edition von Azure AD (in Microsoft Enterprise Mobility + Security E5 enthalten) verfügbar. Weitere Informationen finden Sie unter [Azure Active Directory-Editionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Jeder Benutzer, der mit diesem Feature interagiert (durch Erstellen oder Ausfüllen einer Überprüfung bzw. Bestätigen des Zugriffs), benötigt eine Lizenz.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Verzögerungszeit für die Einstellungen des Gastzugriffs

Für die Einstellungen für den Gastzugriff in Azure Active Directory dauert es einige Stunden, bis die Änderungen in Microsoft 365 oder Office 365 wirksam werden. Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder das gastfeature nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind. Hilfe zu Problemen beim Einrichten des Gastzugriffs finden Sie unter [Problembehandlung beim Gastzugriff in Teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Weitere Informationen

Informationen zur Verwendung von PowerShell zum Verwalten des Gastzugriffs finden Sie unter [Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team](guest-access-powershell.md).


