---
title: Überlegungen zum PSTN beim Upgrade von Skype for Business auf Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Überlegungen zur Sprachansprache für ein Upgrade von Skype for Business auf Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72a12cf1dbcb69af7b71bf259568e4a53d1a3a33
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115543"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Überlegungen zur PSTN für ein Upgrade von Skype for Business auf Teams lokal

In diesem Artikel werden Überlegungen zum Public Switched Telephone Network (PSTN) beim Upgrade auf Teams beschrieben.   


Darüber hinaus werden in den folgenden Artikeln wichtige Upgradekonzepte und das Verhalten der Koexistenz beschrieben:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Die Verwendung von Telefonsystem mit Teams wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet.  Wenn sich der Benutzer im Inselmodus befindet, wird Telefonsystem nur mit Skype for Business unterstützt. 
 > - Alle Einstellungen für Anruf weiterleiten, Teamanrufgruppen und Delegierungseinstellungen aus Skype for Business werden nicht migriert und müssen für Teams neu erstellt werden.
 > - Eine allgemeine Übersicht über die Sprachfeatures der Microsoft Teams-Cloud und Hilfe bei der Entscheidung, welche Microsoft-Sprachlösung für Ihre Organisation die richtige ist, finden Sie unter [Planen Ihrer Teams-Sprachlösung.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Szenarien für PSTN-Anrufe

Beim Wechsel in den TeamsOnly-Modus gibt es vier mögliche Anrufszenarien:

- [Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan.](#from-skype-for-business-online-with-microsoft-calling-plans) Nach dem Upgrade hat dieser Benutzer weiterhin einen Microsoft Calling-Plan.

- [Ein Benutzer in Skype for Business Online mit lokalen](#from-skype-for-business-online-with-on-premises-voice) Sprachfunktionen über Skype for Business lokal oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers zu Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.

- [Ein Benutzer in Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)lokal mit Enterprise-VoIP , der zu online geht und die lokale PSTN-Konnektivität behält.  Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und dieser Wechsel mit der Migration des Benutzers zu Direct Routing koordiniert wird. 

- [Ein Benutzer in Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)lokal mit Enterprise-VoIP , der ins Internet umgeschaltet wird und einen Microsoft Calling-Plan verwendet.  Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und der Wechsel mit A) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B) das Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.

Dieser Artikel bietet nur eine Übersicht auf hoher Ebene. Weitere Informationen finden Sie unter [Telefonsystem-Direct-Routing-](direct-routing-landing-page.md) und [Anrufpläne](calling-plan-landing-page.md). 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen 

Dies ist das einfachste Upgradeszenario mit Sprachsteuerung. 

1. Stellen Sie sicher, dass Benutzern eine Teams-Lizenz zugewiesen wurde. Wenn Sie eine Microsoft 365- oder Office 365-Lizenz zuweisen, ist Teams standardmäßig aktiviert. Sofern Sie die Microsoft Teams-Lizenz nicht zuvor deaktiviert haben, sollte keine Aktion erforderlich sein.

2.  Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, besteht die einzige erforderliche Änderung in der Zuweisung des TeamsOnly-Modus des Benutzers in TeamsUpgradePolicy.  Vor dem Zuweisen des TeamsOnly-Modus werden eingehende PSTN-Anrufe im Skype for Business-Client des Benutzers angezeigt. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Teams-Client des Benutzers angezeigt.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit einer lokalen Sprachsteuerung

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online, aber seine PSTN-Konnektivität ist lokal, entweder mit Skype for Business Server im Hybridmodus oder Cloud Connector Edition. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass sie für Direct Routing aktiviert werden, bei dem PSTN-Trunks über Ihren lokalen Session Border Controller (SBC) direkt mit dem Direct Routing-Dienst in der Cloud eine Verbindung herstellen.

Die grundlegenden Schritte sind unten aufgeführt.  Die Schritte 1 bis 4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel ist, dass alle diese Vorschritte vor Schritt 5 abgeschlossen werden sollten.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, stellen Sie sicher, dass Sie alle vorhandenen Benutzer der Inseln explizit zuweisen, wie zuvor beschrieben.

2. Konfigurieren Sie Ihren Mandanten für Direct Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).

3. Konfigurieren Sie bei Bedarf verschiedene Teams-Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies vor dem Upgrade des Benutzers auf den TeamsOnly-Modus tun.

4. Vorbereiten ausgewählter Benutzer für die Sprachmigration: 
   - Weisen Sie bei Bedarf die Teams-Lizenz zu.  Vorausgesetzt, der Benutzer ist bereits in der lokalen Skype for Business Online-Sprachsteuerung funktionsfähig, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft Phone System. Lassen Sie beide Pläne aktiviert, einschließlich der Skype for Business Online Plan 2-Lizenz.  
   - Weisen Sie die gewünschte OnlineVoiceRoutingPolicy zu. 

5. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Aktualisieren Sie in Microsoft 365 oder Office 365 den Benutzer auf den TeamsOnly-Modus (Grant-CsTeamsUpgradePolicy).
   - Konfigurieren Sie im SBC das Sprachrouting, um eingehende Anrufe zu ermöglichen, indem Sie Anrufe an Direct Routing statt an den lokalen Vermittlungsserver senden.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zu Direct Routing

In diesem Szenario befindet sich der Benutzer weiterhin lokal in Skype for Business, und seine PSTN-Konnektivität ist ebenfalls lokal. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass sie für direct Routing aktiviert werden und dann den Benutzer in die Cloud verschieben. 
 
Die grundlegenden Schritte sind unten aufgeführt.  Die Schritte 1 bis 5 werden in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel ist, dass alle diese Vorschritte vor Schritt 6 abgeschlossen werden sollten.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, achten Sie darauf, vorhandene Benutzer der Inseln explizit zuzuordnen, wie zuvor beschrieben.

2. Wenn Sie dies noch nicht getan haben, konfigurieren Sie die Organisation für [Skype for Business Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Konfigurieren Sie Ihren Mandanten für Direct Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).

4. Konfigurieren Sie bei Bedarf verschiedene Teams-Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies vor dem Upgrade auf TeamsOnly tun.

5. Weisen Sie bei Bedarf die Microsoft 365- oder Office 365-Lizenzen zu.  Der Benutzer sollte sowohl über Teams als auch skype for Business Online Plan 2 sowie über Telefonsystem verfügen. Wenn der Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie ihn erneut.  

6. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser -MoveToTeams-Schalter aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den Schalter -MoveToTeams nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus in powerShell oder der Teams Admin Console des Mandanten zu.

   - Konfigurieren Sie im SBC das Sprachrouting, um eingehende Anrufe zu ermöglichen, indem Sie Anrufe an Direct Routing statt an den lokalen Vermittlungsserver senden. 

   - In Microsoft 365 oder Office 365: Weisen Sie die relevante OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu aktivieren. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Vom lokalen Skype for Business Server mit Enterprise-VoIP zum Microsoft-Anrufplan

In diesem Szenario befindet sich der Benutzer weiterhin lokal in Skype for Business, und seine PSTN-Konnektivität ist ebenfalls lokal. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, den Benutzer in die Cloud zu verschieben und entweder seine Nummer vom alten Netzbetreiber zu einem Microsoft Calling-Plan zu portieren oder dem Benutzer eine neue Nummer zu zuweisen. 

Die grundlegenden Schritte sind unten aufgeführt.Die Schritte 1 bis 5 werden in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel ist, dass alle diese Vorschritte vor Schritt 6 abgeschlossen werden sollten. 

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, achten Sie darauf, vorhandene Benutzer der Inseln explizit zuzuordnen, wie zuvor beschrieben. 

2. Wenn Sie dies noch nicht getan haben, konfigurieren Sie die Organisation für [Skype for Business Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Konfigurieren Sie bei Bedarf verschiedene Teams-Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies vor dem Upgrade auf TeamsOnly tun. 

4. Weisen Sie bei Bedarf die Microsoft 365- oder Office 365-Lizenzen zu.Der Benutzer sollte sowohl über Teams als auch skype for Business Online Plan 2 sowie über Telefonsystem verfügen. Wenn der Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie ihn erneut.  

5. Erhalten Sie Telefonnummern für Ihre Benutzer. (Details finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.)](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Wenn Sie die Nummern erneut verwenden, senden Sie eine Portierungsanfrage an Ihren Netzbetreiber.  
   - Alternativ können Sie neue Nummern direkt von Microsoft erwerben. 

6. Aktualisieren Sie den Benutzer, und weisen Sie bei Bedarf LineUri zu. Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser -MoveToTeams-Schalter aus.  

    - Wenn Sie Nummern zu Microsoft portieren, sollten Sie die Anzeigedauer dieses Vorgangs koordinieren, damit er beim Portieren erfolgt. 

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie den LineUri für den Benutzer ändern. Dies muss geschehen, nachdem der Benutzer mithilfe von Set-CsOnlineVoiceUser online verschoben wurde.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration pro Mandant von Direct Routing 

1. Überprüfen Sie diese Liste, um sicherzustellen, dass Ihr Session Border Controller (SBC) mit Direct Routing [unterstützt wird.](direct-routing-border-controllers.md) Sie müssen auch sicherstellen, dass Sie über die richtige Firmwareversion verfügen.  

2. Koppeln Sie Ihren lokalen SBC mit dem Teams Direct Routing-Dienst. Details finden Sie unter [Koppeln des SBC mit dem Direct Routing-Dienst von Phone System.](direct-routing-configure.md) 

3. Diese Konfiguration ist im Wesentlichen eine Spiegelung der lokalen Konfiguration. Die Onlinekonfiguration besteht aus: 
   - OnlineVoiceRoutingPolicy (basierend auf der lokalen VoiceRoutingPolicy, wenn Benutzer aus Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer von lokalen Mit Enterprise-VoIP).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Nutzung). 
   - OnlineVoiceRoute-Objekte (basierend auf lokalem VoiceRoute). 

Weitere Informationen finden Sie unter [Konfigurieren von Direct Routing](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration 

Unabhängig davon, ob er Direct Routing oder einen Microsoft Calling-Plan verwendet, muss ein Benutzer über EnterpriseVoiceEnabled=true in Azure AD verfügen, damit der Benutzer über pstN-Funktionen verfügen kann.  EnterpriseVoiceEnabled ("EV-enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist für Teams wichtig.  Die genaue Logik für die Einstellung von "EV-enabled" auf "true" hängt vom folgenden Szenario ab: 

- Wenn der Benutzer in lokalem Skype for Business Server aktiviert ist und dem Benutzer vor dem Verschieben des Benutzers in die Cloud mit Move-CsUser eine Telefonsystemlizenz zugewiesen wird, wird der Onlinebenutzer mit EV-enabled=true bereitgestellt. 

- Wenn einem vorhandenen TeamsOnly- oder Skype for Business Online-Benutzer eine Telefonsystemlizenz zugewiesen ist, ist ev-enabled standardmäßig nicht auf true festgelegt.  Dies ist auch der Fall, wenn ein lokales Benutzer in die Cloud verschoben wird, bevor die Lizenz für das Telefonsystem zugewiesen wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Verwandte Links

[Planen Ihrer Teams-Sprachlösung](cloud-voice-landing-page.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)