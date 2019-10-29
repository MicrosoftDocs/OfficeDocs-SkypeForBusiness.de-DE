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
description: IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41630c14c7d1aa9233f53df3c83bd36081d18682
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753290"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Verwalten des Gastzugriffs in Microsoft Teams
======================================

> [!IMPORTANT]
> Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 

**Guest** ist ein Benutzertyp in Microsoft Teams, der in allen Office 365 Business Premium-, Office 365 Enterprise-und Office 365 Education-Abonnements enthalten ist. Eine zusätzliche Office 365-Lizenz ist nicht erforderlich. Weitere Informationen finden Sie unten unter [Gastzugriff-Lizenzierung](#guest-access-licensing-limits) .

Der Gastzugriff auf Microsoft Teams ist eine Einstellung auf Mandantenebene, die standardmäßig deaktiviert ist. Details zum Aktivieren des Gastzugriffs finden Sie unter Aktivieren oder Deaktivieren des Gast [Zugriffs auf Teams](set-up-guests.md)oder verwenden der Checkliste für den [Gastzugriff](guest-access-checklist.md) , um Sie durch das Setup zu führen.

Nachdem Gastzugriff aktiviert ist, können Sie die Einstellungen für Gäste mithilfe der Steuerelemente konfigurieren, die unter [Verwalten von Teams-Einstellungen für Ihre Organisation](enable-features-office-365.md) und [Verwalten von Teams während des Übergangs zum neuen Microsoft Teams Admin Center](manage-teams-skypeforbusiness-admin-center.md)beschrieben sind.     
    
IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten und Berichte über Gastbenutzeraktivität abrufen. Diese Steuerelemente stehen im Team Admin Center zur Verfügung. Der Inhalt und die Aktivitäten von Gastbenutzern unterliegen dem gleichen Compliance-und Überwachungs Schutz wie die restlichen Office 365.

Team Besitzer können neue Gäste einladen und ihren Teams im Team Admin Center vorhandene Verzeichnis Gastbenutzer hinzufügen. Identifizieren Sie Gastbenutzer auf der Seite **Teams** > **Manage Teams** , und legen Sie die Kanal bezogenen Funktionen für Gäste auf der Seite **organisationsweite Einstellungen** > **Gastzugriff** fest. Zu den Einstellungen gehören das Erstellen, aktualisieren und Löschen von Kanälen, wie in der folgenden Abbildung gezeigt.

![Einstellungen von Gastberechtigungen in Teams](media/manage-guest-access-image1.png)
  
Sie können das Azure Active Directory-Portal zum Verwalten von Gästen und deren Zugriff auf Office 365- und Teams-Ressourcen verwenden. Die Teams-Einstellung für Gastzugriff nutzt die Azure AD-B2B-Funktionen (Business-to-Business) zur Zusammenarbeit als zugrunde liegende Infrastruktur zum Speichern der Informationen über Sicherheitsprinzipien, wie zum Beispiel Einstellungen für Identitätseigenschaften, Mitgliedschaften und für die mehrstufige Authentifizierung. Weitere Informationen zu Azure AD B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://go.microsoft.com/fwlink/p/?linkid=853011) und [Häufig gestellte Fragen zur Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=853020).

> [!NOTE]
> Microsoft Teams berücksichtigt immer externe Azure AD-Einstellungen, um das Hinzufügen von Gästen zum Mandanten zuzulassen bzw. zu verhindern. Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).


## <a name="guest-access-licensing-limits"></a>Einschränkungen für Gastzugriffs Lizenzen

Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, basiert jedoch auf dem, was Ihre Azure AD-Lizenzierung zulässt – in der Regel 5 Gäste pro lizenziertem Benutzer. Weitere Informationen finden Sie unter [Lizenzierung für die Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

Aufgrund dieser Lizenzierungseinschränkungen (und um ihren Mandanten auf dem neuesten Stand zu halten) sollten Sie den Gastzugriff in regelmäßigen Abständen überprüfen, um Benutzer zu identifizieren, die Zugriff haben, die Sie nicht mehr benötigen. Mit Azure AD können Sie eine Zugriffsüberprüfung für Mitglieder einer Gruppe oder Benutzer, die einer Anwendung zugewiesen sind, erstellen. Das Erstellen regelmäßiger Zugriffsüberprüfungen kann Zeit sparen. Wenn Sie Benutzer, die Zugriff auf eine Anwendung haben oder Mitglied einer Gruppe sind, routinemäßig überprüfen, können Sie die Häufigkeit dieser Überprüfungen definieren. 

Sie können selbst eine Überprüfung des Gastzugriffs durchführen, Gäste bitten, ihre eigene Mitgliedschaft zu überprüfen oder den Besitzer einer Anwendung bzw. einen Entscheidungsträger bitten, die Zugriffsüberprüfung durchzuführen. Verwenden Sie das Azure-Portal, um Bewertungen von Gastzugriffen durchzuführen. Weitere Informationen finden Sie unter [Verwalten des Gastzugriffs mit Azure AD-Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

###  <a name="prerequisites-for-azure-ad-access-reviews"></a>Voraussetzungen für Azure AD Access-Rezensionen

Zugriffsüberprüfungen sind mit der Premium P2-Edition von Azure AD (in Microsoft Enterprise Mobility + Security E5 enthalten) verfügbar. Weitere Informationen finden Sie unter [Azure Active Directory-Editionen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis). Jeder Benutzer, der mit diesem Feature interagiert (durch Erstellen oder Ausfüllen einer Überprüfung bzw. Bestätigen des Zugriffs), benötigt eine Lizenz.



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a>Verzögerungszeit für die Einstellungen des Gastzugriffs

Für die Einstellungen für den Gastzugriff in Azure Active Directory dauert es 2-24 Stunden, bis die Änderungen in Ihrer Office 365-Organisation wirksam werden. Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder das gastfeature nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind. Hilfe zu Problemen beim Einrichten des Gastzugriffs finden Sie unter [Problembehandlung beim Gastzugriff in Teams](troubleshoot-guest-access.md).

  
## <a name="external-access-federation-vs-guest-access"></a>Externer Zugriff (Föderation) vs. Gastzugriff

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Weitere Informationen

Informationen zur Verwendung von PowerShell zum Verwalten des Gastzugriffs finden Sie unter [Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team](guest-access-powershell.md).


