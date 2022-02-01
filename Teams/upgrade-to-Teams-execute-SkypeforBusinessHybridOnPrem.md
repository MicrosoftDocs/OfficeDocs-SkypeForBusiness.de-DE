---
title: Upgrade Skype for Business lokalen Upgrades auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Erfahren Sie, wie Sie ein Upgrade Ihrer Organisation Microsoft Teams einer lokalen Skype for Business durchführen können.
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299060"
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

Wenn Sie eine lokale Skype for Business Server oder Microsoft Lync Server bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, folgen Sie den Anleitungen in diesem Artikel. Sie müssen Hybridkonnektivität mit Ihrer organisation Microsoft 365 einrichten, wie unter Planen der [Hybridkonnektivität](/skypeforbusiness/hybrid/plan-hybrid-connectivity) zwischen Skype for Business Server und Teams.

Bevor Sie beginnen, sollten Sie sich später in diesem Artikel auch wichtige Überlegungen für Organisationen mit Skype for Business Server [lokalen](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) Standorts durchgehen.

> [!IMPORTANT]
> Skype for Business Online wurde am 31. Juli 2021 eingestellt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass bei einem erfolgreichen Upgrade die Bereitschaft von Technik und Benutzer ausgerichtet ist. Verwenden Sie daher diese Anleitung, wenn Sie zu Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybridkonnektivität 

Die wichtigste Voraussetzung für ein Upgrade Ihrer lokalen Benutzer auf Teams ist das Konfigurieren von Hybridkonnektivität für Ihre Skype for Business Server lokale Bereitstellung. 

Lesen Sie zunächst  [Hybridkonnektivitätplan](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json), und folgen Sie dann den Unter Konfigurieren [der Hybridkonnektivität beschriebenen Aufgaben](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Festlegen des Koexistenzmodus für Die Koexistenz (optional)

Koexistenz und Interoperabilität zwischen Skype for Business und Teams Clients und Benutzern werden durch Modi [für die Koexistenz definiert](migration-interop-guidance-for-teams-with-skype.md). Hybridorganisationen befinden sich standardmäßig im Islands-Modus. Im Modus "Inseln" können Benutzer sowohl Teams als Skype for Business Clients nebeneinander verwenden. Organisationen können optional andere Koexistenzmodi verwenden, um für Endbenutzer eine vorhersehbare Erfahrung zu bieten, wenn Organisationen von einem Skype for Business zu einem Teams. Unabhängig vom Modus, den eine Organisation für ihre lokalen Benutzer verwendet, werden diese Benutzer, wenn sie aus der lokalen Cloud in die Cloud verschoben werden, zu TeamsOnly (und können keinen anderen Modus verwenden).  Solange Benutzer ihr Konto weiterhin Skype for Business Server, kann ihnen ein beliebiger anderer Modus als TeamsOnly zugewiesen werden. Bei Bedarf können TeamsOnly-Benutzer wieder in die lokale Lokale verschoben werden, was dazu führt, dass sie die globale Richtlinie des Mandanten von TeamsUpgradePolicy erhalten.

Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, werden alle eingehenden Chats und Anrufe an den Client des Skype for Business des Benutzers geroutet. Um Verwirrung bei Endbenutzern zu vermeiden und für ordnungsgemäßes Routing zu sorgen, werden die Anruf- und Chatfunktionen im Teams-Client für einen Benutzer deaktiviert, dem ein beliebiger der Modi Skype for Business *wird*. Die Besprechungsplanung in Teams ist deaktiviert, wenn sich Benutzer im Modus SfBOnly oder SfBWithTeamsCollab befinden, und  wird aktiviert, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den geeigneten Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Upgradepfad zuweisen. Weitere Informationen finden Sie unter Anleitungen für Migration und [Interoperabilität](migration-interop-guidance-for-teams-with-skype.md) für Organisationen, die Teams zusammen mit Skype for Business und Festlegen der [Einstellungen für Koexistenz und Upgrade verwenden](./setting-your-coexistence-and-upgrade-settings.md).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern aus der lokalen Skype for Business in den Teams

Microsoft hat kürzlich den Vorgang zum Verschieben von Benutzern nach TeamsOnly vereinfacht. Dieser Vorgang ist jetzt ein einziger Schritt, unabhängig davon, welche Skype for Business Server oder Lync Server 2013 Sie verwenden. Weitere Informationen finden Sie  [unterMove users between on-premises and the cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Schritt 4: Abschließen der Migration in die Cloud durch Deaktivieren der lokalen Hybrid- und außerbetriebnahme Skype for Business

Nachdem Sie alle Benutzer aus der lokalen Bereitstellung in die Cloud verschoben haben, können Sie die lokale Bereitstellung Skype for Business außer Betrieb stellen. Weitere Informationen finden Sie unter [Außerbetriebnahme Ihrer lokalen Skype for Business Umgebung](/skypeforbusiness/hybrid/decommission-on-prem-overview).


## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem und Festnetzanbindung

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Islands-Modus befindet, Telefonsystem nur mit der Skype for Business.) 

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Bei der Abwäge von Optionen für die Konnektivität über das öffentliche Telefonnetz (PSTN) gibt es zwei mögliche Szenarien, wenn sie vom lokalen Skype for Business in den TeamsOnly-Modus wechseln:

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und einen Microsoft-Anrufplan verwendet: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit entweder A) dem Portieren der Telefonnummer dieses Benutzers in einen Microsoft-Anrufplan oder B) dem Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen.  Weitere Informationen finden Sie unter [Von Skype for Business Server lokal mit Enterprise-VoIP zum Microsoft-Anrufplan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und die lokale Festnetzanbindung beibehält: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit dem Übergang des Benutzers zu Direct Routing. Weitere Informationen finden Sie unter Vom Skype for Business Server mit der lokalen [Enterprise-VoIP zum Direct-Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Wichtige Überlegungen für Organisationen mit Skype for Business Server lokal

- Das Einrichten Skype for Business Hybrid ist Voraussetzung für die Migration in den TeamsOnly-Modus. Es ist für lokale Benutzer Skype for Business Server möglich, die Teams ohne Hybridmodus zu verwenden. Der Wechsel in den TeamsOnly-Modus kann jedoch nicht vorgenommen werden, ohne den Benutzer mithilfe von [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) in die Cloud zu verschieben, für die Hybridkonnektivität erforderlich ist. Weitere Informationen finden Sie unter Konfigurieren [von Hybridkonnektivität](/skypeforbusiness/hybrid/configure-hybrid-connectivity). Durch die bevorstehende Skype for Business Online ändert sich diese Anforderung nicht. Damit Organisationen von Skype for Business Server zu Teams wechseln können, müssen sie hybrid weiterhin mit demselben Toolset einrichten und konfigurieren, genau wie vor der *Rente*.

- Um einen lokalen Benutzer in die Cloud zu verschieben, verwenden Sie `Move-CsUser` in den lokalen Verwaltungstools. Sie müssen den Umstieg nicht mehr angeben `-MoveToTeams` , um Benutzer direkt aus der lokalen Lokalen auf TeamsOnly zu verschieben. Benutzern wird automatisch der TeamsOnly-Modus zugewiesen, und ihre lokalen Besprechungen werden automatisch in Teams-Besprechungen `-MoveToTeams` konvertiert – unabhängig davon, ob der Schalter angegeben ist.

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie keine Hybridkonnektivität konfiguriert haben, Sie aber dennoch Teams verwenden möchten, müssen Sie zum Verwalten von Teams-Funktionen ein Administratorkonto verwenden, das über eine onmicrosoft.com-Domäne verfügt. Ohne Hybridkonnektivität erkennen die Verwaltungstools Ihre lokalen Domänen nicht. 

- Teams-Benutzer, die lokal über ein Skype for Business-Konto verfügen (d. h., sie wurden noch nicht mithilfe von Move-CsUser in die Cloud verschoben), können weder mit Skype for Business-Benutzern zusammenarbeiten noch mit externen Benutzern zusammenarbeiten. Diese Funktionalität ist nur verfügbar, wenn die Benutzer in die Cloud verschoben werden und TeamsOnly-Benutzer sind. 

- Wenn Sie über lokale Skype for Business-Konten verfügen oder wenn Sie noch über einen Lyncdiscover-DNS-Eintrag für eine lokale Bereitstellung verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Sie müssen zunächst mit alle Benutzer mit lokalen Skype for Business-Konten in die Cloud verschieben`Move-CsUser`. Führen Sie dann die unter Deaktivieren einer Hybridmigration zum Abschließen [der Migration](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid) in die Cloud beschriebenen Schritte aus, einschließlich entfernen von DNS-Einträgen. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Ort als Office 365.

- Sie müssen sicherstellen, dass die Benutzer ordnungsgemäß mit den Azure AD korrekten Skype for Business synchronisiert werden. Bei diesen Attributen handelt es sich um alle Präfixe mit dem Präfix "msRTCSIP-". Wenn Benutzer nicht ordnungsgemäß mit ihren Azure AD synchronisiert werden, können die Verwaltungstools Teams Benutzer diese Benutzer nicht verwalten. (Beispielsweise können Sie keine Richtlinien Teams lokalen Benutzern zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren Azure AD Verbinden für Teams und Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Zum Erstellen eines neuen TeamsOnly in einer Hybridorganisation müssen Sie zuerst den Benutzer *in Skype for Business Server* lokal aktivieren und dann mithilfe von Move-CsUser aus der lokalen Cloud in die Cloud verschieben.  Indem Sie den Benutzer zuerst lokal erstellen, wird sichergestellt, dass alle anderen lokal Skype for Business Benutzer die Route zu dem neu erstellten Benutzer finden. Nachdem *alle* Benutzer online verschoben wurden, ist es nicht mehr erforderlich, benutzer zuerst lokal zu aktivieren.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie TeamsUpgradePolicy im lokalen Toolset verwenden. Nur der Parameter NotifySfbUsers ist für lokale Benutzer relevant.  Lokale Benutzer erhalten ihren Modus von den Onlineinstanzen von TeamsUpgradePolicy. Weitere Informationen finden Sie in den Notizen unter [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Alle neuen Mandanten, die nach dem 3. September 2019 erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge zum Identifizieren von lokalen Skype for Business Server Organisationen. Weitere Informationen finden Sie unter [Dns-Auswirkungen für lokale Organisationen, die zu einer Hybridlösung werden](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid). 

- In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:
    - [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
    - [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
