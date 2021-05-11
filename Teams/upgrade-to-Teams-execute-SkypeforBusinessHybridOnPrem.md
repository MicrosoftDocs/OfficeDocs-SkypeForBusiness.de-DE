---
title: Upgrade Skype for Business lokalen Upgrades auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Hier erfahren Sie, wie Sie ein Upgrade Ihrer Microsoft Teams auf die Skype for Business lokalen Bereitstellung durchführen.
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
ms.openlocfilehash: d323760d4187730b0ae83d45021df44230a982cd
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306049"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Upgrade von Skype for Business lokalen Lokalen auf Teams

![Upgrade-Wegdiagramm mit Hervorhebung von Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Phase Bereitstellung und Implementierung Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

-   [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
-   [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
-   [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
-   [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)
-   [Durchgeführtes Pilotprojekt](./pilot-essentials.md)

Wenn Sie eine lokale Skype for Business Server oder Microsoft Lync bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, folgen Sie den Anleitungen in diesem Artikel. Sie müssen Hybridkonnektivität mit Ihrer Microsoft 365- oder Office 365-Organisation einrichten und die Anforderungen an die Koexistenz festlegen, wenn Sie Ihre Benutzer phasenweise auf Teams verschieben.

Bevor Sie beginnen, sollten [IT-Profis](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) und -Administratoren die wichtigen Überlegungen für Organisationen mit Skype for Business Server lokal in diesem Artikel lesen.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass bei einem erfolgreichen Upgrade die technische und die Benutzerbereitschaft ausgerichtet ist. Verwenden Sie daher unbedingt die hier angegebenen Anleitungen, wenn Sie zu Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybridkonnektivität 

Die wichtigste Voraussetzung für das Upgrade Ihrer lokalen Benutzer auf Teams ist das Konfigurieren von Hybridkonnektivität für Ihre Skype for Business Server lokale Bereitstellung. 

Lesen Sie zunächst [Planen der Hybridkonnektivität,](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) und folgen Sie dann den Aufgaben unter [Konfigurieren der Hybridkonnektivität.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Festlegen des Koexistenzmodus für Die Koexistenz (optional)

Koexistenz und Interoperabilität zwischen Skype for Business und Teams Clients und Benutzern werden durch Teams-Modi definiert.  Organisationen befinden sich standardmäßig im Modus "Inseln", der es Benutzern ermöglicht, Teams und Skype for Business Clients nebeneinander zu verwenden.

Für eine Organisation, die auf Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer– allerdings müssen nicht allen Benutzern TeamsOnly (oder ein beliebiger anderer Modus) gleichzeitig zugewiesen werden.

Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen optional jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern imOnly-Modus und Benutzern sicherzustellen, die sich noch nicht imOnly-Modus befinden.  Der Zweck der Skype for Business-Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht in der Bereitstellung einer einfachen, vorhersagbaren Erfahrung für Endbenutzer beim Übergang von Skype for Business zu Teams. 

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Client des Skype for Business des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden die Anruf- und Chatfunktionen im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im Modi SfBOnly oder SfBWithTeamsCollab befinden, und wird explizit aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den geeigneten Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Upgradepfad zuweisen. Weitere Informationen finden Sie unter Migrations- und Interoperabilitätsleitfäden für Organisationen, die [Teams](migration-interop-guidance-for-teams-with-skype.md) zusammen mit Skype for Business und Festlegen [Ihrer Koexistenz- und Upgradeeinstellungen verwenden.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern aus der lokalen Skype for Business in den Teams

Letztendlich möchten Sie Ihre Benutzer in den TeamsOnly-Modus verschieben. Dies kann je nach Ihrer lokalen Umgebung ein oder zwei Schritte umfassen.  

Weitere Informationen finden Sie unter [Verschieben von Benutzern](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) zwischen der lokalen und der Cloud und Verschieben von Benutzern von der lokalen in die [Teams.](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Schritt 4: Deaktivieren der Hybridbereitstellung zum Abschließen der Migration in die Cloud

Nachdem Sie alle Benutzer aus der lokalen Bereitstellung in die Cloud verschoben haben, können Sie die lokale Bereitstellung Skype for Business außer Betrieb stellen. Weitere Informationen finden Sie unter [Deaktivieren der Hybridbereitstellung zum Abschließen der Migration in die Cloud.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Telefonsystem und PSTN-Konnektivitätsoptionen

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Islands-Modus befindet, Telefonsystem nur mit der Skype for Business.) 

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Bei der Abwäge von Optionen für die Konnektivität über das öffentliche Telefonnetz (PSTN) gibt es zwei mögliche Szenarien, wenn sie vom lokalen Skype for Business in den TeamsOnly-Modus wechseln:

- Ein Benutzer in Skype for Business mit einem Enterprise-VoIP, der zu online und einen Microsoft-Anrufplan verwenden wird. Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud migriert und der Wechsel mit A) der Portierung der Telefonnummer des Benutzers zu einem Microsoft-Anrufplan oder B) die Zuweisung einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.  Weitere Informationen finden Sie unter Vom Skype for Business Server lokal mit Enterprise-VoIP [zum Microsoft-Anrufplan.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Ein Benutzer in Skype for Business lokalen Netzwerk mit Enterprise-VoIP, der zu online gehen und die lokale PSTN-Anbindung wiederherstellen wird. Die Migration dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business-Kontos des Benutzers in die Cloud und die Koordinierung dieses Wechsels mit der Migration des Benutzers zu Direct Routing. Weitere Informationen finden Sie unter Vom Skype for Business Server lokal mit Enterprise-VoIP [zum Direct-Routing.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Wichtige Überlegungen für Organisationen mit Skype for Business Server lokal

- In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:
    - [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
    - [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Das Einrichten Skype for Business Hybrid ist Voraussetzung für die Migration in den TeamsOnly-Modus. Lokale Skype for Business Server-Benutzer können Teams zwar im Islands-Modus ohne Hybridmodus verwenden, aber der Übergang in den TeamsOnly-Modus kann nicht vorgenommen werden, ohne den Benutzer mithilfe von [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)in die Cloud zu verschieben, für die Hybridkonnektivität erforderlich ist. Weitere Informationen finden Sie unter Konfigurieren [der Hybridkonnektivität.](/skypeforbusiness/hybrid/configure-hybrid-connectivity) Außerdem ändert sich diese Anforderung Skype for Business an der bevorstehenden Skype for Business Online nicht. Damit Organisationen von Skype for Business Server zu Teams wechseln können, müssen sie trotzdem eine Hybridlösung mit demselben Toolset einrichten und konfigurieren, genau wie vor der *-Rente.*

- Um einen lokalen Benutzer in die Cloud zu verschieben, verwenden Sie `Move-CsUser` in den lokalen Verwaltungstools. Wenn dieser Schalter nicht angegeben ist, wechseln die Benutzer von der lokalen Skype for Business Server-Migration zu Skype for Business Online, ihr Modus bleibt unverändert, und besprechungen, die sie in Skype for Business Server organisiert haben, werden zu Skype for Business Online migriert. Aufgrund der bevorstehenden Umstellung von Skype for Business Online wird es bald nicht mehr erforderlich sein, den Umstieg festzulegen, um Benutzer direkt aus der lokalen Lokalen zu `-MoveToTeams` `Move-CsUser` TeamsOnly zu verschieben.  Wenn Sie einen Benutzer nach der Deschaltung mit aus der lokalen Cloud in die Cloud verschieben, wird den Benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus dem lokalen Modus werden automatisch in Teams-Besprechungen konvertiert, genauso, als ob der tatsächlich festgelegt `Move-CsUser` `-MoveToTeams switch had been specified` wurde. Wir erwarten, dass diese Funktion vor der tatsächlichen Ende des 31. Juli 2021 veröffentlicht wird.

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybridkonnektivität konfiguriert haben, Sie aber dennoch Teams verwenden möchten, müssen Sie zum Verwalten der Teams-Funktionalität ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt. Ohne Hybridkonnektivität erkennen die Verwaltungstools Ihre lokalen Domänen nicht. 

- Teams-Benutzer, die lokal über ein Skype for Business-Konto verfügen (d. h., sie wurden noch nicht mithilfe von Move-CsUser in die Cloud verschoben), können weder mit Skype for Business-Benutzern zusammenarbeiten noch mit externen Benutzern zusammenarbeiten. Diese Funktionalität ist nur verfügbar, wenn die Benutzer in die Cloud verschoben werden und TeamsOnly-Benutzer sind. 

- Wenn Sie über lokale Skype for Business-Konten verfügen oder wenn Sie noch über einen lyncdiscover-DNS-Eintrag für eine lokale Bereitstellung verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Zuerst müssen Sie alle Benutzer mit lokalen Skype for Business-Konten mithilfe von in die Cloud verschieben und dann die unter Deaktivieren einer Hybridmigration zum Abschließen der Migration in die Cloud beschriebenen Schritte ausführen, einschließlich Entfernen von `Move-CsUser` DNS-Einträgen. [](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Ort als Office 365.

- Sie müssen sicherstellen, dass die Benutzer ordnungsgemäß mit Azure AD mit den richtigen Skype for Business synchronisiert werden. Bei diesen Attributen handelt es sich um alle Präfixe mit dem Präfix "msRTCSIP-". Wenn benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Teams nicht diese Benutzer verwalten. (Beispielsweise können Sie lokalen Benutzern keine Richtlinien Teams zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD Verbinden für Teams und Skype for Business.](/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Um einen neuen TeamsOnly- oder Skype for Business Online-Benutzer in einer Hybridorganisation zu erstellen, müssen Sie den Benutzer zuerst *in Skype for Business Server* lokal aktivieren und dann mithilfe von Move-CsUser aus der lokalen Cloud in die Cloud verschieben.  Indem Sie den Benutzer zuerst lokal erstellen, wird sichergestellt, dass alle anderen lokal Skype for Business Benutzer den Route zu dem neu erstellten Benutzer routen können. Nachdem alle Benutzer online verschoben wurden, ist es nicht mehr erforderlich, benutzer zuerst lokal zu aktivieren.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie TeamsUpgradePolicy im lokalen Toolset verwenden. Nur der Parameter NotifySfbUsers ist für lokale Benutzer relevant.  Lokale Benutzer erhalten ihren Modus von den Onlineinstanzen von TeamsUpgradePolicy. Weitere Informationen finden Sie in den Notizen unter [Grant-CsTeamsUpgradePolicy.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September 2019 erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge zum Identifizieren von lokalen Skype for Business Server Organisationen. Wenn Ihre Organisation über lokale Skype for Business Server ohne öffentliche DNS-Einträge verfügt, müssen Sie den Microsoft-Support anrufen, damit der neue Mandant heruntergestuft wird. 

## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
