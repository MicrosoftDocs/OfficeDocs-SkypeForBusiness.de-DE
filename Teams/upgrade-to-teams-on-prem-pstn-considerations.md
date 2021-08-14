---
title: Überlegungen zum PSTN beim Upgrade auf Teams von Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Überlegungen zur Verbesserung der Skype for Business zu Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5586b0d366c1e8a237212dde98b4c270f4de02d1830d0885b3f6fdd3b905e36
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330829"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Überlegungen zur PSTN-Teams von Skype for Business lokalen Telefonnetz

In diesem Artikel werden Überlegungen zum öffentlichen Telefonnetz (PSTN) beim Upgrade auf Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Darüber hinaus werden in den folgenden Artikeln wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - Die Telefonsystem mit Teams wird nur unterstützt, wenn dem Konto des Benutzers eine Teams Upgraderichtlinie mit dem Teams zugewiesen wurde.  
 > - Die Telefonsystem mit Skype for Business wird nur unterstützt, wenn dem Konto des Benutzers eine Teams mit einem SfB-Modus zugewiesen wurde. 
 > - Telefonsystem wird nicht unterstützt, wenn dem Konto des Benutzers eine Upgraderichtlinie Teams dem Islands-Modus zugewiesen wurde.
 > - Alle Anruf weiterleitungs-, Teamanrufgruppen- und Delegierungseinstellungen von Skype for Business werden nicht migriert und müssen für andere Benutzer neu Teams.
 > - Einen allgemeinen Überblick über die Microsoft Teams-Sprachfeatures in der Cloud und Hilfe bei der Entscheidung, welche Microsoft-Sprachlösung für Ihre Organisation die richtige ist, finden Sie unter Planen Ihrer [Teams-Sprachlösung.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Szenarien für Anrufe über das Festnetz

Beim Wechsel in den TeamsOnly-Modus gibt es vier mögliche Anrufszenarien:

- [Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan](#from-skype-for-business-online-with-microsoft-calling-plans). Bei einem Upgrade verfügen diese Benutzer weiterhin über einen Microsoft-Anrufplan.

- [Ein Benutzer in Skype for Business Online mit](#from-skype-for-business-online-with-on-premises-voice) lokalen Sprachfunktionen über eine lokale Skype for Business oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams die Migration des Benutzers zu Direct-Routing muss koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.

- [Ein Benutzer in Skype for Business mit](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)der lokalen Enterprise-VoIP, der zu online gehen und die lokale PSTN-Anbindung wiederherstellen wird.  Die Migration dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business-Kontos des Benutzers in die Cloud und die Koordinierung dieses Wechsels mit der Migration des Benutzers zu Direct Routing. 

- [Ein Benutzer in Skype for Business mit](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)der Enterprise-VoIP, der online und mithilfe eines Microsoft-Anrufplans umverteilt wird.  Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud migriert und der Wechsel mit A) der Portierung der Telefonnummer des Benutzers zu einem Microsoft-Anrufplan oder B) die Zuweisung einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.

Dieser Artikel bietet nur eine Übersicht auf einer hohen Ebene. Weitere Informationen finden Sie unter [Telefonsystem von Direct-Routing](direct-routing-landing-page.md) und [Anrufplänen.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen 

Dies ist das einfachste Upgradeszenario mit Sprache. 

1. Stellen Sie sicher, dass Benutzern eine Lizenz Teams wurde. Wenn Sie eine Microsoft 365- oder Office 365-Lizenz zuweisen, ist Teams standardmäßig aktiviert. Wenn Sie die Teams-Lizenz also zuvor deaktiviert haben, ist keine Aktion erforderlich.

2.  Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, ist die einzige erforderliche Änderung das Zuweisen des TeamsOnly-Modus des Benutzers in TeamsUpgradePolicy.  Vor der Zuweisung des TeamsOnly-Modus werden eingehende PSTN-Anrufe im Client des Skype for Business landen. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Client Teams des Benutzers landen.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit lokalem Sprachanruf

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online, aber seine PSTN-Konnektivität ist lokal, entweder mithilfe von Skype for Business Server im Hybridmodus oder Cloud Connector Edition. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet die Aktivierung für Direct-Routing, bei dem PSTN-Trunks über Ihren lokalen Session Border Controller (SBC) eine direkte Verbindung mit dem Direct-Routingdienst in der Cloud herstellen.

Die grundlegenden Schritte sind nachfolgend aufgeführt.  Die Schritte 1 bis 4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Entscheidend ist, dass alle diese Schritte vor Schritt 5 abgeschlossen werden sollten.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, stellen Sie sicher, dass alle vorhandenen Islands-Benutzer durch explizite Zuweisung des Islands-Modus zugewiesen werden, wie zuvor beschrieben.

2. Konfigurieren Sie Ihren Mandanten für Direct-Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct-Routing.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies am besten tun, bevor der Benutzer in den TeamsOnly-Modus aktualisiert wird.

4. Vorbereiten ausgewählter Benutzer für die Sprachmigration: 
   - Weisen Sie bei Bedarf die Teams zu.  Sofern der Benutzer bereits in Skype for Business Online lokal verwendet werden kann, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft-Telefon System. Lassen Sie beide Pläne aktiviert, einschließlich der Skype for Business Online Plan 2-Lizenz.  
   - Weisen Sie die gewünschte OnlineVoiceRoutingPolicy zu. 

5. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Führen Microsoft 365 oder Office 365 für den Benutzer ein Upgrade auf den TeamsOnly-Modus aus (Grant-CsTeamsUpgradePolicy).
   - Konfigurieren Sie auf dem SBC das Sprachrouting so, dass eingehende Anrufe durch Senden von Anrufen an Direct-Routing statt an den lokalen Vermittlungsserver aktiviert werden.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Vom Skype for Business Server lokalen Standort mit Enterprise-VoIP zum Direct-Routing

In diesem Szenario wird der Benutzer weiterhin lokal Skype for Business, und auch die PSTN-Konnektivität ist lokal. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass sie für Direct-Routing aktiviert werden und den Benutzer dann in die Cloud verschieben. 
 
Die grundlegenden Schritte sind nachfolgend aufgeführt.  Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Entscheidend ist, dass alle diese Schritte vor Schritt 6 abgeschlossen werden sollten.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, stellen Sie sicher, dass vorhandene Islands-Benutzer durch explizite Zuweisung des Islands-Modus festgelegt werden, wie zuvor beschrieben.

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie die Organisation für Skype for Business [Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Konfigurieren Sie Ihren Mandanten für Direct-Routing. Weitere [Informationen finden Sie unter Zusammenfassung der Konfiguration pro Mandant von Direct-Routing.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies am besten tun, bevor der Benutzer auf TeamsOnly aktualisiert wird.

5. Weisen Sie die Microsoft 365 oder Office 365 Lizenzen zu, falls erforderlich.  Der Benutzer sollte sowohl über Teams als Skype for Business Online Plan 2 als auch über Telefonsystem. Wenn der Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie ihn erneut.  

6. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden. 

   - Führen Sie mithilfe der lokalen Skype for Business-Tools eine Move-CsUser -MoveToTeams-Option aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den Schalter -MoveToTeams nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus in Der Mandanten-Remote-PowerShell oder Teams Admin Console zu.

   - Konfigurieren Sie auf dem SBC das Sprachrouting so, dass eingehende Anrufe durch Senden von Anrufen an Direct-Routing statt an den lokalen Vermittlungsserver aktiviert werden. 

   - In Microsoft 365 oder Office 365: Weisen Sie die relevante OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu aktivieren. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Vom Skype for Business Server lokalen Standort mit Enterprise-VoIP zum Microsoft-Anrufplan

In diesem Szenario wird der Benutzer weiterhin lokal Skype for Business, und auch die PSTN-Konnektivität ist lokal. Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass der Benutzer in die Cloud wechselt und seine Nummer entweder vom alten Netzbetreiber zu einem Microsoft-Anrufplan portiert oder dem Benutzer eine neue Nummer zugewiesen wird. 

Die grundlegenden Schritte sind nachfolgend aufgeführt.Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in jeder beliebigen Reihenfolge ausgeführt werden. Entscheidend ist, dass alle diese Schritte vor Schritt 6 abgeschlossen werden sollten. 

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, stellen Sie sicher, dass vorhandene Islands-Benutzer durch explizite Zuweisung des Islands-Modus festgelegt werden, wie zuvor beschrieben. 

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie die Organisation für Skype for Business [Hybrid.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit geschehen, aber wenn Sie sicherstellen möchten, dass die Benutzer beim Upgrade über die richtige Konfiguration verfügen, sollten Sie dies am besten tun, bevor der Benutzer auf TeamsOnly aktualisiert wird. 

4. Weisen Sie die Microsoft 365 oder Office 365 Lizenzen zu, falls erforderlich.Der Benutzer sollte sowohl über Teams als Skype for Business Online Plan 2 als auch über Telefonsystem. Wenn der Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie ihn erneut.  

5. Erhalten Sie Telefonnummern für Ihre Benutzer. (Details finden Sie [unter Verwalten von Telefonnummern für Ihre Organisation.)](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Wenn Sie die Nummern wiederver verwenden werden, senden Sie eine Portierungsanforderung an Ihren Netzbetreiber.  
   - Alternativ können Sie neue Nummern direkt von Microsoft erwerben. 

6. Aktualisieren Sie den Benutzer, und weisen Sie bei Bedarf LineUri zu. Führen Sie mithilfe der lokalen Skype for Business-Tools eine Move-CsUser mit dem Schalter -MoveToTeams aus.  

    - Wenn Sie Nummern zu Microsoft portieren, sollten Sie den Zeitpunkt des Portierungsvorgangs koordinieren. 

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie den LineUri für den Benutzer ändern. Dies muss geschehen, nachdem der Benutzer mithilfe von Set-CsOnlineVoiceUser online gezogen ist.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration pro Mandant von Direct Routing 

1. Stellen Sie sicher, dass Ihr Session Border Controller (SBC) mit Direct Routing unterstützt wird, indem Sie [sich diese Liste durcharbeiten.](direct-routing-border-controllers.md) Sie müssen auch sicherstellen, dass Sie über die richtige Firmwareversion verfügen.  

2. Koppeln Sie Ihren lokalen SBC mit dem Teams Direct-Routingdienst. Details finden Sie unter [Koppeln des SBC mit dem Direct-Routingdienst Telefonsystem.](direct-routing-configure.md) 

3. Diese Konfiguration ist im Wesentlichen ein Spiegelbild der lokalen Konfiguration. Die Onlinekonfiguration besteht aus: 
   - OnlineVoiceRoutingPolicy (basierend auf der lokalen VoiceRoutingPolicy, wenn Benutzer von Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer mit Enterprise-VoIP aus der lokalen VoiceRoutingPolicy migriert werden).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Verwendung) 
   - OnlineVoiceRoute-Objekte (basierend auf lokalem VoiceRoute). 

Weitere Informationen finden Sie unter [Konfigurieren von Direct-Routing.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration 

Unabhängig davon, ob Sie Direct Routing oder einen Microsoft Calling-Plan verwenden, muss ein Benutzer EnterpriseVoiceEnabled=true in Azure AD haben, damit der Benutzer über PSTN-Funktionen verfügen kann.  EnterpriseVoiceEnabled ("EV-enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist für Ihre Teams.  Die genaue Logik, wie EV-enabled auf "true" festgelegt wird, hängt vom folgenden Szenario ab: 

- Wenn der Benutzer in lokalem Skype for Business Server für EW aktiviert ist und dem Benutzer vor dem Verschieben des Benutzers mit Move-CsUser in die Cloud eine Telefonsystem-Lizenz zugewiesen wird, wird der Onlinebenutzer mit EV-enabled=true bereitgestellt. 

- Wenn einem vorhandenen TeamsOnly- oder Skype for Business Online-Benutzer eine Telefonsystem-Lizenz zugewiesen ist, ist EV-enabled nicht standardmäßig auf "true" festgelegt.  Dies ist auch der Fall, wenn ein lokaler Benutzer in die Cloud verschoben wird, bevor die Lizenz zugewiesen Telefonsystem wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Links zu verwandten Themen

[Planen Ihrer Teams-Sprachlösung](cloud-voice-landing-page.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
