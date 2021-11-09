---
title: Upgrade Skype for Business lokalen Upgrades auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Hier erfahren Sie, wie Sie Ihre Organisation auf Microsoft Teams Bereitstellung Skype for Business lokalen Bereitstellung aktualisieren.
ms.localizationpriority: medium
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
ms.openlocfilehash: 5269cd9033c179ad748fb8909b3010fe09311e4a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850518"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Upgrade von Skype for Business lokalen Lokalen auf Teams

![Upgrade-Wegdiagramm mit Hervorhebung von Bereitstellung und Implementierung.](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Phase Bereitstellung und Implementierung Ihres Upgrades. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

-   [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
-   [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
-   [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
-   [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)
-   [Durchgeführtes Pilotprojekt](./pilot-essentials.md)

Wenn Sie eine lokale Skype for Business Server oder Microsoft Lync bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, folgen Sie den Anleitungen in diesem Artikel. Sie müssen hybride Konnektivität mit Ihrer Microsoft 365- oder Office 365-Organisation einrichten und die Anforderungen an die Koexistenz festlegen, wenn Sie Ihre Benutzer phasenweise auf Teams verschieben.

Bevor Sie beginnen, sollten [IT-Profis](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) und -Administratoren die wichtigen Überlegungen für Organisationen mit Skype for Business Server lokal in diesem Artikel lesen.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt. Ab diesem Zeitpunkt kann nicht mehr darauf zugegriffen werden, und es wird nicht mehr unterstützt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass bei einem erfolgreichen Upgrade die bereitschafts- und technischen Anforderungen der Benutzer ausgerichtet sind. Verwenden Sie daher diese Anleitung, wenn Sie zu Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybridkonnektivität 

Die wichtigste Voraussetzung für ein Upgrade Ihrer lokalen Benutzer auf Teams ist das Konfigurieren von Hybridkonnektivität für Ihre Skype for Business Server lokale Bereitstellung. 

Lesen Sie zunächst [Planen der Hybridkonnektivität,](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json)und folgen Sie dann den Aufgaben unter [Konfigurieren der Hybridkonnektivität.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Festlegen des Koexistenzmodus für Die Koexistenz (optional)

Koexistenz und Interoperabilität zwischen Skype for Business und Teams Clients und Benutzern werden durch Teams Upgrademodi definiert.  Hybridorganisationen sowie alle vor dem 3. September 2019 erstellten Organisationen befinden sich standardmäßig im Islands-Modus. Im Modus "Inseln" können Benutzer sowohl Teams als Skype for Business Clients nebeneinander verwenden. Für eine Organisation, die in den Teams wechselt, ist der TeamsOnly-Modus das endgültige Ziel für jeden Benutzer– allerdings müssen nicht allen Benutzern TeamsOnly (oder ein beliebiger anderer Modus) gleichzeitig zugewiesen werden.

Bevor Benutzer den TeamsOnly-Modus erreichen, können Organisationen optional jeden der Skype for Business-Koexistenzmodi verwenden, um eine vorhersehbare Kommunikation zwischen Benutzern imOnly-Modus und Benutzern sicherzustellen, die sich noch nicht imOnly-Modus befinden.  Der Zweck der Skype for Business-Koexistenzmodi (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) besteht im Bereitstellen einer einfachen, vorhersagbaren Erfahrung für Endbenutzer, wenn Organisationen von Skype for Business zu Teams. Einem in einer lokalen Skype for Business Server Benutzer kann ein anderer Modus als TeamsOnly zugewiesen werden. Nachdem ein Benutzer in die Cloud verschoben wurde, handelt es sich um TeamsOnly.  Nur-Cloud-Benutzern kann kein anderer Modus als TeamsOnly zugewiesen werden. (Sie können jedoch wieder in die lokale Lokale verschoben werden, was dazu führen würde, dass sie die globale Richtlinie des Mandanten von TeamsUpgradePolicy erhalten.)

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Client des Skype for Business des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden die Anruf- und Chatfunktionen im Teams-Client deaktiviert, wenn sich ein Benutzer in einem der Skype for Business befindet. Ebenso wird die Besprechungsplanung in Teams explizit deaktiviert, wenn sich Benutzer im Modi SfBOnly oder SfBWithTeamsCollab befinden, und explizit aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den geeigneten Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Upgradepfad zuweisen. Weitere Informationen finden Sie unter Anleitungen für Migration und Interoperabilität für Organisationen, die [Teams](migration-interop-guidance-for-teams-with-skype.md) zusammen mit Skype for Business und Festlegen Ihrer [Koexistenz- und Upgradeeinstellungen verwenden.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern aus der lokalen Skype for Business in den Teams

Microsoft hat kürzlich den Vorgang zum Verschieben von Benutzern nach TeamsOnly vereinfacht. Dieser Vorgang ist jetzt ein einziger Schritt, unabhängig davon, welche Skype for Business Server oder Lync Server 2013 Sie verwenden. Weitere Informationen finden Sie unter [Verschieben von Benutzern](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) zwischen der lokalen und der Cloud und [Verschieben](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)von Benutzern aus der lokalen Teams. 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Schritt 4: Deaktivieren der Hybridbereitstellung zum Abschließen der Migration in die Cloud

Nachdem Sie alle Benutzer aus der lokalen Bereitstellung in die Cloud verschoben haben, können Sie die lokale Bereitstellung Skype for Business außer Betrieb stellen. Weitere Informationen finden Sie unter [Deaktivieren der Hybridbereitstellung zum Abschließen der Migration in die Cloud.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem und Festnetzanbindung

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Islands-Modus befindet, Telefonsystem nur mit der Skype for Business.) 

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Beim Erwägen der Konnektivitätsoptionen für das public Switched Telephone Network (PSTN) gibt es zwei mögliche Szenarien, wenn Sie vom lokalen Skype for Business in den TeamsOnly-Modus wechseln:

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und einen Microsoft-Anrufplan verwendet: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit entweder A) dem Portieren der Telefonnummer dieses Benutzers in einen Microsoft-Anrufplan oder B) dem Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen.  Weitere Informationen finden Sie unter Von Skype for Business Server lokal mit Enterprise-VoIP [zum Microsoft-Anrufplan.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und die lokale Festnetzanbindung beibehält: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit dem Übergang des Benutzers zu Direct Routing. Weitere Informationen finden Sie unter Vom Skype for Business Server lokal mit Enterprise-VoIP [zum Direct-Routing.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Wichtige Überlegungen für Organisationen mit Skype for Business Server lokal

- In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:
    - [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
    - [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Das Einrichten Skype for Business Hybrid ist Voraussetzung für die Migration in den TeamsOnly-Modus. Lokale Skype for Business Server-Benutzer können Teams zwar im Islands-Modus ohne Hybridmodus verwenden, aber der Übergang in den TeamsOnly-Modus kann nicht vorgenommen werden, ohne den Benutzer mithilfe von [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)in die Cloud zu verschieben, für die Hybridkonnektivität erforderlich ist. Weitere Informationen finden Sie unter Konfigurieren [der Hybridkonnektivität.](/skypeforbusiness/hybrid/configure-hybrid-connectivity) Außerdem ändert sich diese Anforderung Skype for Business bevorstehenden Endes von Skype for Business Online nicht. Damit Organisationen von Skype for Business Server zu Teams wechseln können, müssen sie weiterhin eine Hybridlösung mit demselben Toolset einrichten und konfigurieren, genau wie vor der *-Rente.*

- Um einen lokalen Benutzer in die Cloud zu verschieben, verwenden Sie `Move-CsUser` in den lokalen Verwaltungstools. Es ist nicht mehr erforderlich, den Wechsel zum direkten Verschieben von Benutzern aus der lokalen Lokalen zu `-MoveToTeams` TeamsOnly festzulegen. Wenn Sie einen Benutzer mit aus der lokalen in die Cloud verschieben, wird den Benutzern jetzt automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus dem lokalen Modus werden automatisch in Teams-Besprechungen konvertiert, genauso, als ob die Option tatsächlich angegeben `Move-CsUser` `-MoveToTeams switch had been specified` wurde.

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybridkonnektivität konfiguriert haben, Sie aber dennoch Teams verwenden möchten, müssen Sie zum Verwalten der Teams-Funktionalität ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt. Ohne Hybridkonnektivität erkennen die Verwaltungstools Ihre lokalen Domänen nicht. 

- Teams-Benutzer, die lokal über ein Skype for Business-Konto verfügen (d. h., sie wurden noch nicht mithilfe von Move-CsUser in die Cloud verschoben), können weder mit Skype for Business-Benutzern zusammenarbeiten noch mit externen Benutzern zusammenarbeiten. Diese Funktionalität ist nur verfügbar, wenn die Benutzer in die Cloud verschoben werden und TeamsOnly-Benutzer sind. 

- Wenn Sie über lokale Skype for Business-Konten verfügen oder wenn Sie noch über einen lyncdiscover-DNS-Eintrag für eine lokale Bereitstellung verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Zunächst müssen Sie alle Benutzer mit lokalen Skype for Business-Konten mithilfe von in die Cloud verschieben und dann die unter Deaktivieren einer Hybridbereitstellung zum Abschließen der Migration in die Cloud beschriebenen Schritte ausführen, einschließlich Entfernen von `Move-CsUser` DNS-Einträgen. [](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Ort als Office 365.

- Sie müssen sicherstellen, dass die Benutzer ordnungsgemäß mit den Azure AD korrekten Skype for Business synchronisiert werden. Bei diesen Attributen handelt es sich um alle Präfixe mit dem Präfix "msRTCSIP-". Wenn Die Benutzer nicht ordnungsgemäß mit den Azure AD synchronisiert werden, können die Teams benutzerverwaltungstools diese Benutzer nicht verwalten. (Beispielsweise können Sie lokalen Benutzern keine Teams-Richtlinien zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren Azure AD Verbinden für Teams und Skype for Business.](/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Zum Erstellen eines neuen TeamsOnly in einer Hybridorganisation müssen Sie zuerst den Benutzer *in Skype for Business Server* lokal aktivieren und dann mithilfe von Move-CsUser aus der lokalen Cloud in die Cloud verschieben.  Indem Sie den Benutzer zuerst lokal erstellen, wird sichergestellt, dass alle anderen lokal Skype for Business Benutzer die Route zu dem neu erstellten Benutzer finden. Nachdem *alle* Benutzer online verschoben wurden, ist es nicht mehr erforderlich, benutzer zuerst lokal zu aktivieren.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie TeamsUpgradePolicy im lokalen Toolset verwenden. Nur der Parameter NotifySfbUsers ist für lokale Benutzer relevant.  Lokale Benutzer erhalten ihren Modus von den Onlineinstanzen von TeamsUpgradePolicy. Weitere Informationen finden Sie in den Notizen unter [Grant-CsTeamsUpgradePolicy.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September 2019 erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge zum Identifizieren von lokalen Skype for Business Server Organisationen. Wenn Ihre Organisation über lokale Einträge Skype for Business Server öffentlichen DNS-Einträgen verfügt, müssen Sie den Microsoft-Support anrufen, damit der neue Mandant heruntergestuft wird. 

## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
