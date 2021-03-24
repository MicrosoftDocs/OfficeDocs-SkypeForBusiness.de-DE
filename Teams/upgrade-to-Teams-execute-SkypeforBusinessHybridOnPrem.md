---
title: Upgrade von Skype for Business lokal auf Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Erfahren Sie, wie Sie Ihr Unternehmen über eine lokale Skype for Business-Bereitstellung auf Microsoft Teams aktualisieren.
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
ms.openlocfilehash: b35a757ecd70fbf2926e668bef86cb21e51d8b8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093785"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Upgrade von Skype for Business lokal auf Teams

![Upgrade-Reisediagramm mit Betonung auf Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

-   [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
-   [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
-   [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
-   [Vorbereiten Ihrer Organisation](./upgrade-prepare-organization.md)
-   [Pilot durchgeführt](./pilot-essentials.md)

Wenn Sie Skype for Business Server oder Microsoft Lync lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, folgen Sie den Anweisungen in diesem Artikel. Sie müssen hybride Konnektivität mit Ihrer Microsoft 365- oder Office 365-Organisation einrichten und die Anforderungen an die Koexistenz festlegen, wenn Sie Ihre Benutzer phasenweise nach Teams verschieben.

Bevor Sie beginnen, sollten IT-Profis und Administratoren die wichtigen Überlegungen für Organisationen lesen, die [Skype for Business Server](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) lokal verwenden.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass ein erfolgreiches Upgrade die technische Bereitschaft und Benutzerbereitschaft an sich richtet. Verwenden Sie daher unbedingt die hierin enthaltenen Anleitungen, während Sie auf Ihrem Weg zu Microsoft Teams navigieren.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybridkonnektivität 

Die wichtigste Voraussetzung für das Upgrade Ihrer lokalen Benutzer auf Teams besteht in der Konfiguration der Hybridkonnektivität für Ihre lokale Skype for Business Server-Bereitstellung. 

Lesen Sie zunächst [Planen der Hybridkonnektivität,](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) und folgen Sie dann den unter [Konfigurieren der Hybridkonnektivität beschriebenen Aufgaben.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Festlegen des Übergangsmodus für die Koexistenz (optional)

Die Koexistenz und Interoperabilität zwischen Skype for Business- und Teams-Clients und -Benutzern werden durch die Upgrademodi von Teams definiert.  Organisationen befinden sich standardmäßig im Inselmodus, der Benutzern die gleichzeitige Verwendung von Teams- und Skype for Business-Clients ermöglicht.

Für eine Organisation, die zu Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer . Allerdings müssen nicht allen Benutzern TeamsOnly (oder ein anderer Modus) gleichzeitig zugewiesen werden.

Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen optional jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersagbare Kommunikation zwischen Benutzern im TeamsOnly-Modus und Benutzern sicherzustellen, die noch nicht sind.  Der Zweck der Skype for Business-Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht in der Bereitstellung einer einfachen, vorhersagbaren Benutzererfahrung, während Organisationen von Skype for Business zu Teams wechseln. 

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business-Client des Benutzers geroutet. Um Verwirrung zwischen Endbenutzern zu vermeiden und die ordnungsgemäße Routing-, Anruf- und Chatfunktion im Teams-Client sicherzustellen, wird die Funktion deaktiviert, wenn sich ein Benutzer in einem der Skype for Business-Modi befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden und explizit aktiviert werden, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den geeigneten Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Upgradepfad zuweisen. Weitere Informationen finden Sie unter [Migrations-](migration-interop-guidance-for-teams-with-skype.md) und Interoperabilitätsleitfäden für Organisationen, die Teams zusammen mit Skype for Business verwenden, und Festlegen [Ihrer Koexistenz- und Upgradeeinstellungen.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern von Skype for Business lokal zu Teams Only

Schließlich möchten Sie Ihre Benutzer in den TeamsOnly-Modus verschieben. Dies kann je nach ihrer lokalen Umgebung ein oder zwei Schritte umfassen.  

Weitere Informationen finden Sie unter Verschieben von Benutzern zwischen lokal und der [Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) und Verschieben von Benutzern von lokal nach [Teams.](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Schritt 4: Deaktivieren der Hybridbereitstellung zum Abschließen der Migration in die Cloud

Nachdem Sie alle Benutzer aus der lokalen Cloud in die Cloud verschoben haben, können Sie die lokale Skype for Business-Bereitstellung außer Betrieb lassen. Weitere Informationen finden Sie unter [Deaktivieren der Hybridsteuerung zum Abschließen der Migration in die Cloud.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem- und PSTN-Konnektivität

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Inselmodus befindet, wird Telefonsystem nur mit Skype for Business unterstützt.) 

### <a name="pstn-connectivity-options"></a>PstN-Konnektivitätsoptionen

Bei der Berücksichtigung der Konnektivitätsoptionen für das öffentliche Telefonnetz (PSTN) gibt es zwei mögliche Szenarien, wenn Sie lokal von Skype for Business in den TeamsOnly-Modus wechseln:

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP, der zu online geht und einen Microsoft Calling-Plan verwendet. Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und der Wechsel mit A) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B) das Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.  Weitere Informationen finden Sie unter Lokal von [Skype for Business Server mit](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)Enterprise-VoIP zu Microsoft Calling Plan .

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP, der auf online umgeschaltet wird und die lokale PSTN-Konnektivität behält. Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und dieser Wechsel mit der Migration des Benutzers zu Direct Routing koordiniert wird. Weitere Informationen finden Sie unter [Von Skype for Business Server](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)lokal mit Enterprise-VoIP zu Direct Routing .


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Wichtige Überlegungen für Organisationen mit lokalem Skype for Business Server

- In den folgenden Artikeln werden wichtige Upgradekonzepte und das Verhalten der Koexistenz beschrieben:
    - [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
    - [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Das Einrichten von Skype for Business Hybrid ist eine Voraussetzung für die Migration in den TeamsOnly-Modus. Obwohl teams im Inselmodus ohne Hybridmodus verwendet werden kann, kann der Übergang zum TeamsOnly-Modus erst vorgenommen werden, wenn der Benutzer von Skype for Business lokal zu Skype for Business Online (mithilfe von [Move-CsUser)](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)verschoben wird. Weitere Informationen finden Sie unter [Konfigurieren von Hybridkonnektivität.](/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybridkonnektivität konfiguriert haben, Sie aber dennoch Teams verwenden möchten, um die Funktionen von Teams zu verwalten, müssen Sie ein Administratorkonto verwenden, das über eine .onmicrosoft.com-Domäne verfügt. 

- Teams-Benutzer, die über ein lokales Skype for Business-Konto verfügen (d. h., sie wurden noch nicht mithilfe von Move-CsUser in die Cloud verschoben) können weder mit Skype for Business-Benutzern zusammenarbeiten noch mit externen Benutzern zusammenarbeiten. Diese Funktion ist nur verfügbar, wenn die Benutzer in die Cloud verschoben werden (entweder im Inselmodus oder als TeamsOnly-Benutzer). 

- Wenn Sie über benutzer mit lokalen Skype for Business-Konten verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Sie müssen zuerst alle Benutzer mit lokalen Skype for Business-Konten mithilfe von in die Cloud verschieben und dann hybrid deaktivieren, um die Migration in die `Move-CsUser` [Cloud abschließen zu können.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.

- Sie müssen sicherstellen, dass Ihre Benutzer ordnungsgemäß mit Azure AD mit den richtigen Skype for Business-Attributen synchronisiert werden. Diese Attribute sind alle Präfixe mit "msRTCSIP-". Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Teams diese Benutzer nicht verwalten. (Beispielsweise können Sie lokalen Benutzern keine Teams-Richtlinien zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Connect für Teams und Skype for Business.](/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Um einen neuen TeamsOnly- oder Skype for Business Online-Benutzer in einer Hybridorganisation zu erstellen, müssen Sie den Benutzer zuerst *lokal in Skype for Business Server* aktivieren und dann mithilfe von Move-CsUser aus der lokalen Cloud in die Cloud verschieben.  Wenn Sie den Benutzer zuerst lokal erstellen, wird sichergestellt, dass alle anderen lokalen Skype for Business-Benutzer die Route zum neu erstellten Benutzer führen können. Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr erforderlich, benutzer zuerst lokal zu aktivieren.

- Wenn ein Benutzer von der lokalen in die Cloud verschoben wird, werden von diesem Benutzer organisierte Besprechungen zu Skype for Business Online oder Teams migriert – je nachdem, ob der Schalter "MoveToTeams" angegeben ist.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie TeamsUpgradePolicy im lokalen Toolset verwenden. Nur der Parameter NotifySfbUsers ist für lokale Benutzer relevant.  Lokale Benutzer erhalten ihren Modus von den Onlineinstanzen von TeamsUpgradePolicy. Weitere Informationen finden Sie in den Notizen in [Grant-CsTeamsUpgradePolicy.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September 2019 erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge, um lokale Skype for Business Server-Organisationen zu identifizieren. Wenn Ihre Organisation über einen lokalen Skype for Business Server ohne öffentliche DNS-Einträge verfügt, müssen Sie den Microsoft-Support anrufen, damit Ihr neuer Mandant heruntergestuft wird. 

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)