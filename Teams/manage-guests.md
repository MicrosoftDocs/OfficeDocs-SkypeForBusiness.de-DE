---
title: Verwalten des Benutzerzugriffs in Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 02faf85d91657c487c02503b69b08078b81c88de
ms.sourcegitcommit: 70fc5217f588e10ab0edb400f329ea597efaab52
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2018
---
<a name="manage-guest-access-in-microsoft-teams"></a>Verwalten des Benutzerzugriffs in Microsoft Teams
======================================

**Gast** ist ein Benutzer-Lizenz in Microsoft-Teams, die alle Abonnements für Office 365 Business Premium, Office 365 Enterprise und Office 365 Education enthalten ist. Eine zusätzliche Office 365-Lizenz ist nicht erforderlich. Der Gastzugriff auf Microsoft Teams ist eine Einstellung auf Mandantenebene, die standardmäßig deaktiviert ist. Ausführliche Informationen zum Gastzugriff zu ermöglichen finden Sie unter [Aktivieren oder Deaktivieren der Gastzugriff auf Microsoft-Teams](set-up-guests.md).

Nach der **Gast** User-Lizenz Typ aktiviert ist, können Sie Einstellungen für Gäste über den Steuerelementen im [Microsoft-Teams, Verwalten von Features in Office 365-Organisation](enable-features-office-365.md#settings-by-userlicense-type)beschrieben konfigurieren.     
    
IT-Administratoren können Gäste auf der Mandantenebene hinzufügen, Richtlinien und Berechtigungen für Gastbenutzer festlegen und verwalten, festlegen, welche Benutzer Gäste einladen können, und Berichte über Gastbenutzeraktivität abrufen. Diese Steuerelemente sind über das Office 365 Admin Center verfügbar. Inhalte und Aktivitäten von Gastbenutzern unterliegen dem gleichen Compliance- und Überwachungsschutz wie der Rest von Office 365.

Team Besitzer können neue Gäste einladen und ihre Teams vorhandenen Directory Gastbenutzer hinzuzufügen. Darüber hinaus können Teams Besitzer Channel-bezogenen Funktionen festlegen, für Gäste über **Teams verwalten** > **Gastberechtigungen**, einschließlich zulassen Gäste zu erstellen, aktualisieren und Löschen von Kanäle, wie im folgenden Screenshot dargestellt:

![Gast berechtigungseinstellungen in Teams.](media/view-guests-guest-permissions.png)
  

Zudem können Sie das Azure Active Directory-Portal zum Verwalten von Gästen und deren Zugriff auf Office 365- und Teams-Ressourcen verwenden. Die Teams-Einstellung für Gastzugriff nutzt die Azure Active Directory-B2B-Funktionen (Business-to-Business) zur Zusammenarbeit als zugrunde liegende Infrastruktur zum Speichern der Informationen über Sicherheitsprinzipien, wie zum Beispiel Einstellungen für Identitätseigenschaften, Mitgliedschaften und für die mehrstufige Authentifizierung. Weitere Informationen zu Azure Active Directory B2B finden Sie unter [Was ist die Azure AD B2B-Zusammenarbeit?](https://go.microsoft.com/fwlink/p/?linkid=853011) und [Häufig gestellte Fragen zur Azure Active Directory B2B-Zusammenarbeit](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Microsoft-Teams berücksichtigt immer externe Azure Active Directory-Einstellungen zum Zulassen oder Sperren von Gast Benutzer zusätzlich zu den Mandanten. Weitere Informationen finden Sie unter [Autorisieren Gast Access in Microsoft-Teams](Teams-dependencies.md).
  
