---
title: Upgrade von Skype for Business (lokal) auf Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Erfahren Sie, wie Sie Ihre Organisation auf Microsoft Teams über eine lokale Skype for Business-Bereitstellung aktualisieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b63473dcb07c5fcac49902ced6d11777217a0c5
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940595"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Upgrade von Skype for Business lokal in Teams

![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

-   [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
-   [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
-   [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Durchgeführt eines Pilotprojekts](https://aka.ms/SkypeToTeams-Pilot)

Wenn Sie Skype for Business Server oder Microsoft lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, befolgen Sie die Anleitungen in diesem Artikel. Sie müssen eine hybridverbindung mit Ihrer Microsoft 365-oder Office 365-Organisation einrichten und die Anforderungen an die Koexistenz ermitteln, wenn Sie Ihre Benutzer in Phasen in Teams verschieben. 

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Beachten Sie, dass ein erfolgreiches Upgrade die technische und Benutzer Bereitschaft ausrichtet, damit Sie die hierin beschriebenen Anleitungen für die Navigation in Ihrer Reise zu Microsoft Teams nutzen können.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybrid Konnektivität 

Die wichtigste Voraussetzung für das Upgrade Ihrer lokalen Benutzer auf Teams ist die Konfiguration der Hybrid Konnektivität für Ihre lokale Skype for Business Server-Bereitstellung. 

Beginnen Sie mit dem Lesen der [Plan-Hybrid Konnektivität](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) , und folgen Sie dann den Aufgaben, die unter [Konfigurieren der Hybrid Konnektivität](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)beschrieben werden.


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Einrichten des Übergangsmodus für Koexistenz (optional)

Die Koexistenz und Interoperabilität zwischen Skype for Business-und Microsoft Teams-Clients und-Benutzern wird durch die Upgrade-Modi von Teams definiert.  Standardmäßig befinden sich Organisationen im Inseln-Modus, sodass Benutzer beide Teams und Skype for Business-Clients nebeneinander verwenden können.

Für eine Organisation, die in Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer, wobei nicht allen Benutzern gleichzeitig TeamsOnly (oder ein beliebiger anderer Modus) zugewiesen werden muss.

Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen optional einen beliebigen Skype for Business-Koexistenzmodus verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern zu gewährleisten, die sich im TeamsOnly-Modus befinden, und Benutzern, die noch nicht angemeldet sind.  Der Zweck der Koexistenz-Modi von Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht darin, den Endbenutzern eine einfache, vorhersagbare Erfahrung zu bieten, wenn Organisationen von Skype for Business zu Teams wechseln. 

Wenn sich ein Nutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers weitergeleitet. Um die Verwirrung von Endbenutzern zu vermeiden und die ordnungsgemäße Weiterleitung zu gewährleisten, ist die Funktion für Anrufe und Chats im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Terminplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly-oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den entsprechenden Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Aktualisierungspfad zuweisen. Weitere Informationen finden Sie unter [Migrations-und Interoperabilitäts Anleitungen für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) und [Ihre Koexistenz-und Upgradeeinstellungen festlegen](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern von Skype for Business lokal in Teams

Letztendlich möchten Sie Ihre Benutzer in den TeamsOnly-Modus verschieben. Dies kann je nach ihrer lokalen Umgebung ein oder zwei Schritte umfassen.  

Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen lokalen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) und [Verschieben von Benutzern von lokal in Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Schritt 4: Deaktivieren Sie Hybrid, um die Migration in die Cloud abzuschließen.

Nachdem Sie alle Benutzer von lokal in die Cloud verschoben haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb nehmen. Weitere Informationen finden Sie unter [Deaktivieren von Hybriden zur vollständigen Migration in die Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefon System und PSTN-Konnektivität

Das Telefon System mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Modus "Inseln" befindet, wird das Telefon System nur von Skype for Business unterstützt.) 

### <a name="pstn-connectivity-options"></a>PSTN-Verbindungsoptionen

Wenn Sie die Verbindungsoptionen für PSTN (Public Switched Telephone Network) in Betracht ziehen, gibt es zwei mögliche Szenarien beim Umstieg von Skype for Business lokal in den TeamsOnly-Modus:

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP, der in den Online-und mit einem Microsoft-Anrufplan umziehen wird. Wenn Sie diesen Benutzer zu Teams migrieren, müssen Sie das lokale Skype for Business-Konto des Benutzers in die Cloud verschieben und diesen Schritt entweder mit a) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B durch stellen, um eine neue Teilnehmernummer aus verfügbaren Regionen zuzuweisen.  Weitere Informationen finden Sie unter [von Skype for Business Server lokal mit Enterprise-VoIP zu Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP, der zu Online wechseln und die lokale PSTN-Konnektivität aufrecht erhalten soll. Wenn Sie diesen Benutzer zu Teams migrieren, muss das lokale Skype for Business-Konto des Benutzers in die Cloud verschoben und koordiniert werden, um die Migration des Benutzers zur direkten Weiterleitung zu koordinieren. Weitere Informationen finden Sie unter [von Skype for Business Server lokal mit Enterprise-VoIP zum direkten Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).
