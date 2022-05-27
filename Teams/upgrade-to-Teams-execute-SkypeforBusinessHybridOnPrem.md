---
title: Lokales Upgrade Skype for Business auf Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Erfahren Sie, wie Sie Ihr Unternehmen von einer Skype for Business lokalen Bereitstellung auf Microsoft Teams aktualisieren.
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
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681366"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Upgrade von Skype for Business lokal auf Teams

![Upgrade-Journey-Diagramm mit Betonung der Bereitstellung und Implementierung.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Ihre Organisation vorbereitet](./upgrade-prepare-organization.md)
- [Durchführen eines Pilotprojekts](./pilot-essentials.md)

Wenn Sie Skype for Business Server oder Microsoft Lync Server lokal bereitgestellt haben und Ihre Organisation ein Upgrade auf Teams durchführen möchte, folgen Sie den Anweisungen in diesem Artikel. Sie müssen eine Hybridverbindung mit Ihrer Microsoft 365 Organisation einrichten, wie unter [Planen der Hybridkonnektivität zwischen Skype for Business Server und Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity) beschrieben.

Bevor Sie beginnen, sollten Sie auch [wichtige Überlegungen für Organisationen mit Skype for Business Server lokal](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) weiter unten in diesem Artikel lesen.

> [!IMPORTANT]
> Skype for Business Online wurde am 31. Juli 2021 eingestellt. Um den maximalen Nutzen zu erzielen und sicherzustellen, dass Ihre Organisation genügend Zeit hat, Ihr Upgrade durchzuführen, empfehlen wir Ihnen, den Wechsel zu Microsoft Teams bereits heute zu planen. Denken Sie daran, dass ein erfolgreiches Upgrade die technische und benutzertechnische Bereitschaft anordnen kann. Nutzen Sie daher diese Anleitung, während Sie auf Ihrem Weg zu Microsoft Teams navigieren.

## <a name="step-1-configure-hybrid-connectivity"></a>Schritt 1: Konfigurieren der Hybridkonnektivität

Die wichtigste Voraussetzung für das Upgrade Ihrer lokalen Benutzer auf Teams besteht darin, die Hybridkonnektivität für Ihre Skype for Business Server lokale Bereitstellung zu konfigurieren.

Lesen Sie zunächst ["Hybridkonnektivität](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) planen", und folgen Sie dann den Unter [Konfigurieren der Hybridkonnektivität](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) beschriebenen Aufgaben.

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Schritt 2: Festlegen des Übergangskoexistenzmodus (optional)

Koexistenz und Interoperabilität zwischen Skype for Business und Teams Clients und Benutzern werden durch [Koexistenzmodi](migration-interop-guidance-for-teams-with-skype.md) definiert. Hybridorganisationen befinden sich standardmäßig im Inselmodus. Im Inselmodus können Benutzer sowohl Teams als auch Skype for Business Clients nebeneinander verwenden. Organisationen können optional andere Koexistenzmodi verwenden, um Endbenutzern beim Übergang von Skype for Business zu Teams eine vorhersehbare Erfahrung zu bieten. Unabhängig davon, welchen Modus eine Organisation für ihre lokalen Benutzer verwendet, werden diese Benutzer, wenn sie von der lokalen In die Cloud verschoben werden, zu TeamsOnly (und können keinen anderen Modus haben).  Solange Benutzer noch Skype for Business Server verwenden, können sie jedem anderen Modus als TeamsOnly zugewiesen werden. Bei Bedarf können TeamsOnly-Benutzer wieder in die lokale Umgebung verschoben werden, was dazu führen würde, dass sie die globale Richtlinie des Mandanten "TeamsUpgradePolicy" erhalten.

Wenn sich ein Benutzer in einem der Skype for Business Modi befindet, werden alle eingehenden Chats und Anrufe an den Skype for Business Client des Benutzers weitergeleitet. Um Verwirrung bei Endbenutzern zu vermeiden und die ordnungsgemäße Routing-, Anruf- und Chatfunktion im Teams-Client sicherzustellen, ist *dies für einen Benutzer deaktiviert, dem einer der Skype for Business Modi zugewiesen ist*. Die Besprechungsplanung in Teams ist deaktiviert, wenn sich Benutzer im SfBOnly- oder SfBWithTeamsCollab-Modus befinden, und *aktiviert*, wenn sich ein Benutzer im SfBWithTeamsCollabAndMeetings-Modus befindet.

Je nach Ihren Anforderungen können Sie den entsprechenden Koexistenzmodus basierend auf dem von Ihrer Organisation ausgewählten Upgradepfad zuweisen. Weitere Informationen finden Sie unter [Migrations- und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit Skype for Business](migration-interop-guidance-for-teams-with-skype.md) und [Festlegen Ihrer Koexistenz- und Upgradeeinstellungen](./setting-your-coexistence-and-upgrade-settings.md) verwenden.

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Schritt 3: Verschieben von Benutzern von Skype for Business lokal in nur Teams

Microsoft hat kürzlich den Prozess zum Verschieben von Benutzern nach TeamsOnly vereinfacht. Dieser Vorgang ist jetzt ein einzelner Schritt, unabhängig davon, welche Version von Skype for Business Server oder Lync Server 2013 Sie verwenden. Weitere Informationen finden Sie unter [Verschieben von Benutzern zwischen der lokalen Bereitstellung und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) und Verschieben von Benutzern von lokalen zu Teams.For more information, see Move users between on-premises and the cloud and [Move users from on-premises to Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Schritt 4: Abschließen der Migration in die Cloud durch Deaktivieren der Hybridbereitstellung und Außerbetriebnahme lokaler Skype for Business

Nachdem Sie alle Benutzer aus der lokalen Umgebung in die Cloud verschoben haben, können Sie die lokale Skype for Business Bereitstellung außer Betrieb lassen. Weitere Informationen finden Sie unter [Außerbetriebnahme Ihrer lokalen Skype for Business Umgebung](/skypeforbusiness/hybrid/decommission-on-prem-overview).

## <a name="phone-system-and-pstn-connectivity-options"></a>Optionen für Telefonsystem und Festnetzanbindung

Telefonsystem mit Teams wird unterstützt, nachdem sich der Benutzer im TeamsOnly-Modus befindet. (Wenn sich der Benutzer im Inselmodus befindet, wird Telefonsystem nur mit Skype for Business unterstützt.)

### <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Bei der Betrachtung der PSTN-Konnektivitätsoptionen (Public Switched Telephone Network, PSTN) gibt es zwei mögliche Szenarien beim Wechsel von Skype for Business lokal in den TeamsOnly-Modus:

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und einen Microsoft-Anrufplan verwendet: Die Migration dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business Kontos des Benutzers in die Cloud und die Koordination dieser Verschiebung mit A) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B), der eine neue Abonnentennummer aus verfügbaren Regionen zuweist.  Weitere Informationen finden Sie unter ["Von Skype for Business Server lokal mit Enterprise-VoIP zum Microsoft-Anrufplan.For more information, see From Skype for Business Server on-premises, with Enterprise-VoIP, to Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Ein Benutzer in lokalem Skype for Business mit Enterprise Voice, der in den Onlinemodus wechselt und die lokale Festnetzanbindung beibehält: Die Migration dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business Kontos des Benutzers in die Cloud und die Koordination dieser Migration mit der Migration des Benutzers zu Direct Routing. Weitere Informationen finden Sie unter ["Von Skype for Business Server lokal mit Enterprise-VoIP zu Direct Routing.For more information, see From Skype for Business Server on-premises, with Enterprise-VoIP, to Direct Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Wichtige Überlegungen für Organisationen mit Skype for Business Server lokal

- Das Einrichten Skype for Business Hybridbereitstellung ist eine Voraussetzung für die Migration in den TeamsOnly-Modus. Es ist für lokale Skype for Business Server-Benutzer möglich, Teams im Inselmodus ohne Hybridbereitstellung zu verwenden. Der Übergang in den TeamsOnly-Modus kann jedoch nicht erfolgen, ohne den Benutzer mit [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) in die Cloud zu verschieben, für den eine Hybridkonnektivität erforderlich ist. Weitere Informationen finden [Sie unter Konfigurieren der Hybridkonnektivität](/skypeforbusiness/hybrid/configure-hybrid-connectivity). Die bevorstehende Einstellung von Skype for Business Online ändert diese Anforderung nicht. Damit Organisationen von Skype for Business Server zu Teams wechseln können, müssen sie die Hybridbereitstellung weiterhin mit demselben Toolset einrichten und konfigurieren, *genau wie vor der Einstellung*.

- Verwenden Sie die lokalen Verwaltungstools, `Move-CsUser` um einen lokalen Benutzer in die Cloud zu verschieben. Sie müssen den `-MoveToTeams` Wechsel zum direkten Verschieben von Benutzern aus der lokalen Umgebung zu TeamsOnly nicht mehr angeben. Benutzern wird automatisch der TeamsOnly-Modus zugewiesen, und ihre lokalen Besprechungen werden automatisch in Teams Besprechungen konvertiert – unabhängig davon, ob die `-MoveToTeams` Option angegeben ist.

- Wenn Ihre Organisation über Skype for Business Server verfügt und Sie die Hybridkonnektivität nicht konfiguriert haben, sie aber dennoch Teams verwenden möchten, müssen Sie zum Verwalten Teams Funktionen ein Administratorkonto verwenden, das über eine .onmicrosoft.com-Domäne verfügt. Ohne Hybridkonnektivität erkennen die Verwaltungstools Ihre lokalen Domänen nicht.

- Teams Benutzer, die über ein lokales Skype for Business-Konto verfügen (d. h. sie wurden noch nicht mitHilfe von Move-CsUser in die Cloud verschoben), können weder mit Skype for Business Benutzern zusammenarbeiten noch mit externen Benutzern verbunden werden. Diese Funktionalität ist nur verfügbar, sobald die Benutzer in die Cloud verschoben wurden und TeamsOnly-Benutzer sind.

- Wenn Sie Benutzer mit Skype for Business lokalen Konten haben oder noch über einen lyncdiscover-DNS-Eintrag für eine lokale Bereitstellung verfügen, können Sie den TeamsOnly-Modus nicht auf Mandantenebene zuweisen. Sie müssen zunächst alle Benutzer mit lokalen Skype for Business-Konten in die Cloud verschieben.`Move-CsUser` Führen Sie dann die unter ["Hybrid deaktivieren" beschriebenen Schritte aus, um die Migration in die Cloud abzuschließen](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid), was das Entfernen von DNS-Einträgen umfasst. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`funktioniert nicht auf Mandantenebene, wenn ein lyncdiscover-DNS-Eintrag erkannt wird, der auf einen anderen Speicherort als Office 365 verweist.

- Sie müssen sicherstellen, dass Ihre Benutzer ordnungsgemäß mit Azure AD mit den richtigen Skype for Business Attributen synchronisiert werden. Diese Attribute sind alle Präfixe mit "msRTCSIP-". Wenn Benutzer nicht ordnungsgemäß mit Azure AD synchronisiert werden, können die Verwaltungstools in Teams diese Benutzer nicht verwalten. (Sie können z. B. lokalen Benutzern keine Teams Richtlinien zuweisen, es sei denn, Sie synchronisieren diese Attribute ordnungsgemäß.) Weitere Informationen finden Sie unter [Konfigurieren von Azure AD-Verbinden für Teams und Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Um ein neues TeamsOnly in einer Hybridorganisation zu erstellen, *müssen Sie zuerst den Benutzer in Skype for Business Server lokal aktivieren* und den Benutzer dann mit Move-CsUser von der lokalen in die Cloud verschieben.  Wenn Sie den Benutzer zuerst lokal erstellen, wird sichergestellt, dass alle anderen verbleibenden lokalen Skype for Business Benutzer an den neu erstellten Benutzer weitergeleitet werden können. Nachdem *alle* Benutzer online verschoben wurden, ist es nicht mehr erforderlich, benutzer zuerst lokal zu aktivieren.

- Wenn Sie Benachrichtigungen im Skype for Business-Client für lokale Benutzer anzeigen möchten, müssen Sie TeamsUpgradePolicy im lokalen Toolset verwenden. Nur der NotifySfbUsers-Parameter ist für lokale Benutzer relevant.  Lokale Benutzer erhalten ihren Modus von den Onlineinstanzen von TeamsUpgradePolicy. Weitere Informationen finden Sie in den Notizen in [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

> [!NOTE]
> Alle neuen Mandanten, die nach dem 3. September 2019 erstellt wurden, werden als TeamsOnly-Mandanten erstellt, es sei denn, die Organisation verfügt bereits über eine lokale Bereitstellung von Skype for Business Server. Microsoft verwendet DNS-Einträge, um lokale Skype for Business Server Organisationen zu identifizieren. Weitere Informationen finden Sie unter [DNS-Implikationen für lokale Organisationen, die hybrid werden](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid).

- In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:
  - [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
  - [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Konfigurieren der Hybridverbindung zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
