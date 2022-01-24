---
title: Überlegungen zum PSTN beim Upgrade auf Teams von Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Überlegungen zur Verbesserung der Skype for Business auf Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19c1860c3a351cd7ed6a6240e20dc253f204ab1
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180888"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Überlegungen zur PSTN-Teams von Skype for Business lokalen Telefonnetz

In diesem Artikel werden Überlegungen zum öffentlichen Telefonnetz (PSTN) beim Upgrade auf Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Die Telefonsystem mit Teams wird nur unterstützt, wenn dem Konto des Benutzers eine Teams mit dem Teams zugewiesen wurde.  
 > - Die Telefonsystem mit Skype for Business wird nur unterstützt, wenn dem Konto des Benutzers eine Teams einem SfB-Modus zugewiesen wurde. 
 > - Telefonsystem wird nicht unterstützt, wenn dem Konto des Benutzers eine Upgraderichtlinie Teams dem Islands-Modus zugewiesen wurde.
 > - Alle Anruf weiterleitungs-, Teamanrufgruppen- und Delegierungseinstellungen von Skype for Business werden nicht migriert und müssen für andere Benutzer neu Teams.
 > - Eine allgemeine Übersicht über die Microsoft Teams-Sprachfeatures in der Cloud und Hilfe bei der Entscheidung, welche Microsoft-Sprachlösung für Ihre Organisation die richtige ist, finden Sie unter Planen ihrer [Teams-Sprachlösung.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Szenarien für Anrufe über das Festnetz

Beim Wechsel in den TeamsOnly-Modus gibt es vier mögliche Anrufszenarien:

- [Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan](#from-skype-for-business-online-with-microsoft-calling-plans): Bei einem Upgrade verfügen diese Benutzer weiterhin über einen Microsoft-Anrufplan.

- [Ein Benutzer in Skype for Business Online](#from-skype-for-business-online-with-on-premises-voice) mit lokalen Sprachfunktionen über eine lokale Skype for Business oder Cloud Connector Edition. Um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt, müssen Sie das Upgrade des Benutzers auf Teams mit der Migration des Benutzers zu Direct-Routing koordinieren.

- [Ein Benutzer in Skype for Business lokalen](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)Netzwerk mit Enterprise-VoIP, der zu online gehen und die lokale PSTN-Anbindung wiederherstellen wird.  Um diesen Benutzer zu Teams zu migrieren, müssen Sie das lokale Skype for Business-Konto des Benutzers in die Cloud verschieben und die Migration mit der Migration des Benutzers zu Direct-Routing koordinieren. 

- [Ein Benutzer in Skype for Business mit](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)dem Enterprise-VoIP, der zu online und einen Microsoft-Anrufplan verwendet.  Um diesen Benutzer zu einem anderen Teams, müssen Sie das lokale Konto des Benutzers Skype for Business in die Cloud verschieben. Sie müssen den Wechsel entweder mit A) dem Portieren der Telefonnummer des Benutzers zu einem Microsoft-Anrufplan koordinieren oder B) eine neue Abonnentennummer aus verfügbaren Regionen zuweisen.

Dieser Artikel bietet nur eine Übersicht auf einer hohen Ebene. Weitere Informationen finden Sie unter [Telefonsystem Direct-Routing](direct-routing-landing-page.md) und [Anrufpläne.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen 

Dieses Szenario ist das einfachste Upgradeszenario mit Sprache. 

1. Stellen Sie sicher, dass Benutzern eine Lizenz Teams wurde. Wenn Sie eine Lizenz zuweisen, Microsoft 365 sie Office 365, ist Teams aktiviert. Sofern Sie die Teams zuvor deaktiviert haben, ist keine Aktion erforderlich.

2.  Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, ist die einzige erforderliche Änderung das Zuweisen des TeamsOnly-Modus des Benutzers in TeamsUpgradePolicy. Vor der Zuweisung des TeamsOnly-Modus werden eingehende PSTN-Anrufe im Client des Skype for Business des Benutzers landen. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Client des Teams landen.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit lokalem Sprachanruf

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online. Die PSTN-Konnektivität des Benutzers ist lokal, entweder mithilfe Skype for Business Server Hybridmodus oder Cloud Connector Edition. Um diese Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität zu migrieren, müssen Sie die Benutzer für Direct-Routing aktivieren. Mit Direct Routing stellen PSTN-Trunks eine direkte Verbindung mit dem Direct-Routingdienst über Ihren lokalen Session Border Controller (SBC) fest.

Die grundlegenden Schritte sind nachfolgend aufgeführt.  Die Schritte 1 bis 4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Diese Schritte sollten vor Schritt 5 abgeschlossen werden.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, achten Sie darauf, alle vorhandenen Islands-Benutzer zu zuordnen, indem Sie diesen explizit den Islands-Modus zuweisen, wie zuvor beschrieben.

2. Konfigurieren Sie Ihren Mandanten für Direct-Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct-Routing.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy und so weiter). Sie können die Poicies jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer in den TeamsOnly-Modus aktualisiert wird.

4. Vorbereiten ausgewählter Benutzer für die Sprachmigration: 
   - Weisen Sie bei Bedarf die Teams zu.  Sofern der Benutzer bereits in der lokalen Skype for Business Online-Sprachfunktion funktioniert, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft-Telefon System. Lassen Sie beide Pläne aktiviert, einschließlich der Skype for Business Online Plan 2-Lizenz.  
   - Weisen Sie die gewünschte OnlineVoiceRoutingPolicy zu. 

5. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Führen Microsoft 365 oder Office 365 für den Benutzer ein Upgrade auf den TeamsOnly-Modus (Grant-CsTeamsUpgradePolicy) durch.
   - Konfigurieren Sie auf dem SBC das Sprachrouting so, dass eingehende Anrufe durch Senden von Anrufen an Direct-Routing statt an den lokalen Vermittlungsserver aktiviert werden.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Vom Skype for Business Server lokalen Standort mit Enterprise-VoIP zum Direct-Routing

In diesem Szenario wird der Benutzer weiterhin lokal Skype for Business. Die PSTN-Anbindung des Benutzers ist ebenfalls lokal. Um diesen Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität zu migrieren, müssen Sie den Benutzer für Direct-Routing aktivieren und den Benutzer dann in die Cloud verschieben. 
 
Die grundlegenden Schritte sind nachfolgend aufgeführt. Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Sie müssen die Schritte 1 bis 5 vor Schritt 6 ausführen.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen möchten, achten Sie darauf, vorhandene Islands-Benutzer durch explizite Zuweisung des Islands-Modus zu zuordnen, wie zuvor beschrieben.

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie die Organisation für Skype for Business [Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Konfigurieren Sie Ihren Mandanten für Direct-Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct-Routing.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Konfigurieren Sie bei Bedarf Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy). Sie können Richtlinien jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer auf TeamsOnly aktualisiert wird.

5. Weisen Sie die Microsoft 365 oder Office 365 zu, falls erforderlich.  Der Benutzer sollte sowohl über Teams als Skype for Business Online Plan 2 und Telefonsystem. Wenn das Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

6. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Führen Sie mithilfe der lokalen Skype for Business-Tools eine Move-CsUser -MoveToTeams-Option aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den Schalter -MoveToTeams nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus in Der Mandanten-Remote-PowerShell oder Teams Admin Console zu.

   - Konfigurieren Sie auf dem SBC das Sprachrouting so, dass eingehende Anrufe durch Senden von Anrufen an Direct-Routing statt an den lokalen Vermittlungsserver aktiviert werden. 

   - In Microsoft 365 oder Office 365: Weisen Sie die relevante OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu aktivieren. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Vom Skype for Business Server lokalen Standort mit Enterprise-VoIP zum Microsoft-Anrufplan

In diesem Szenario wird der Benutzer weiterhin lokal Skype for Business. Die PSTN-Anbindung des Benutzers ist ebenfalls lokal. Um diesen Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität zu migrieren, müssen Sie den Benutzer in die Cloud verschieben und entweder seine Nummer vom alten Netzbetreiber zu einem Microsoft-Anrufplan portieren oder dem Benutzer eine neue Nummer zuweisen. 

Die grundlegenden Schritte sind nachfolgend aufgeführt.Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Sie müssen die Schritte 1 bis 5 vor Schritt 6 ausführen. 

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen möchten, achten Sie darauf, vorhandene Islands-Benutzer durch explizite Zuweisung des Islands-Modus zu zuordnen, wie zuvor beschrieben. 

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie die Organisation für Skype for Business [Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy und so weiter). Sie können Richtlinien jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer auf TeamsOnly aktualisiert wird. 

4. Weisen Sie die Microsoft 365 oder Office 365 zu, falls erforderlich.Der Benutzer sollte sowohl über Teams als Skype for Business Online Plan 2 und Telefonsystem. Wenn das Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

5. Erhalten Sie Telefonnummern für Ihre Benutzer. (Details finden Sie [unter Verwalten von Telefonnummern für Ihre Organisation.)](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Wenn Sie die Nummern wiederver verwenden werden, senden Sie eine Portierungsanforderung an Ihren Netzbetreiber.  
   - Alternativ können Sie neue Nummern direkt von Microsoft erwerben. 

6. Aktualisieren Sie den Benutzer, und weisen Sie bei Bedarf LineUri zu. Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser -MoveToTeams-Schalter aus.  

    - Wenn Sie Nummern zu Microsoft portieren, sollten Sie den Zeitpunkt des Portierungsvorgangs koordinieren. 

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie den LineUri für den Benutzer ändern, nachdem der Benutzer mithilfe von Set-CsPhoneNumberAssignment online gezogen ist.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration pro Mandant von Direct Routing 

1. Stellen Sie sicher, dass Ihr Session Border Controller (SBC) mit Direct Routing unterstützt wird, indem Sie [sich diese Liste durcharbeiten.](direct-routing-border-controllers.md) Stellen Sie außerdem sicher, dass Sie über die richtige Firmwareversion verfügen.  

2. Koppeln Sie Ihren lokalen SBC mit dem Teams Direct-Routingdienst. Details finden Sie unter [Koppeln des SBC mit dem Direct-Routingdienst Telefonsystem](direct-routing-configure.md). 

3. Diese Konfiguration ist im Wesentlichen ein Spiegelbild der lokalen Konfiguration. Die Onlinekonfiguration besteht aus: 
   - OnlineVoiceRoutingPolicy (basierend auf der lokalen VoiceRoutingPolicy, wenn Benutzer von Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer mit Enterprise-VoIP lokal migriert werden).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Verwendung) 
   - OnlineVoiceRoute-Objekte (basierend auf lokalem VoiceRoute). 

Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration 

Unabhängig davon, ob Sie Direct Routing oder einen Microsoft Calling-Plan verwenden, müssen Benutzer EnterpriseVoiceEnabled=true in Azure AD damit der Benutzer über PSTN-Funktionen verfügen kann.  EnterpriseVoiceEnabled ("EV-enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist wichtig für Teams.  Die genaue Logik, wie EV-enabled auf "true" festgelegt wird, hängt vom folgenden Szenario ab: 

- Wenn der Benutzer in lokalem Skype for Business Server aktiviert ist und dem Benutzer vor dem Verschieben des Benutzers in die Cloud mit Move-CsUser eine Telefonsystem-Lizenz zugewiesen wird, wird dem Onlinebenutzer EV-enabled=true bereitgestellt. 

- Wenn einem vorhandenen TeamsOnly- oder Skype for Business Online-Benutzer eine Telefonsystem-Lizenz zugewiesen ist, ist EV-enabled nicht standardmäßig auf "true" festgelegt. Dies ist auch der Fall, wenn ein lokaler Benutzer vor dem Zuweisen der Lizenz in die Cloud Telefonsystem wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben: 

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Links zu verwandten Themen

[Planen Ihrer Microsoft Teams-Anruflösung](cloud-voice-landing-page.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
