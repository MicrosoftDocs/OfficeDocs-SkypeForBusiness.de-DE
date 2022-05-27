---
title: Überlegungen zum PSTN beim Upgrade auf Teams von Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: VoIP-Überlegungen für das Upgrade von Skype for Business auf Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681346"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>PSTN-Überlegungen für das Upgrade von Skype for Business lokal auf Teams

In diesem Artikel werden Überlegungen zum PSTN (Public Switched Telephone Network) beim Upgrade auf Teams beschrieben.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

In den folgenden Artikeln werden wichtige Upgradekonzepte und Koexistenzverhalten beschrieben:

- [Koexistenz von Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Koexistenzmodi – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - Die Verwendung Telefonsystem mit Teams wird nur unterstützt, wenn dem Konto des Benutzers eine Teams Upgraderichtlinie mit Teams Modus "Nur" zugewiesen ist.
> - Die Verwendung von Telefonsystem mit Skype for Business wird nur unterstützt, wenn dem Konto des Benutzers eine Teams Upgraderichtlinie mit einem SfB-Modus zugewiesen ist.
> - Telefonsystem wird nicht unterstützt, wenn dem Konto des Benutzers eine Teams-Upgraderichtlinie mit dem Inselmodus zugewiesen wird.
> - Alle Einstellungen für Anrufweiterleitung, Teamanrufgruppe und Delegierung von Skype for Business werden nicht migriert und müssen für Teams neu erstellt werden.
> - Eine allgemeine Übersicht über Microsoft Teams Cloud Voice-Features und Hilfe bei der Entscheidung, welche Microsoft-VoIP-Lösung für Ihre Organisation geeignet ist, finden Sie unter [Planen Ihrer Teams Voice-Lösung](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>PSTN-Anrufszenarien

Es gibt vier mögliche Anrufszenarien beim Wechsel in den TeamsOnly-Modus:

- [Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan](#from-skype-for-business-online-with-microsoft-calling-plans): Nach dem Upgrade verfügt dieser Benutzer weiterhin über einen Microsoft-Anrufplan.

- [Ein Benutzer in Skype for Business Online mit lokaler Sprachfunktion](#from-skype-for-business-online-with-on-premises-voice) über Skype for Business lokale oder Cloud Connector Edition. Um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt, müssen Sie das Upgrade des Benutzers auf Teams mit der Migration des Benutzers zu Direct Routing koordinieren.

- [Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), der online ist und die lokale PSTN-Konnektivität beibehalten wird.  Um diesen Benutzer zu Teams zu migrieren, müssen Sie das lokale Skype for Business Konto des Benutzers in die Cloud verschieben und diese Verschiebung mit der Migration des Benutzers zu Direct Routing koordinieren.

- [Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), der online ist und einen Microsoft-Anrufplan verwendet.  Um diesen Benutzer zu Teams zu migrieren, müssen Sie das lokale Skype for Business Konto des Benutzers in die Cloud verschieben. Sie müssen die Verschiebung entweder mit A) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder mit B) koordinieren, der eine neue Teilnehmernummer aus verfügbaren Regionen zuweist.

Dieser Artikel bietet nur eine allgemeine Übersicht. Weitere Informationen finden Sie [unter Telefonsystem Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen

Dieses Szenario ist das einfachste Upgradeszenario mit VoIP.

1. Stellen Sie sicher, dass Benutzern eine Teams-Lizenz zugewiesen wurde. Wenn Sie eine Microsoft 365- oder Office 365-Lizenz zuweisen, ist Teams standardmäßig aktiviert. Sofern Sie die Teams Lizenz nicht zuvor deaktiviert haben, sollte keine Aktion erforderlich sein.

2. Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, besteht die einzige erforderliche Änderung darin, dem Benutzer den TeamsOnly-Modus in TeamsUpgradePolicy zuzuweisen. Vor dem Zuweisen des TeamsOnly-Modus landen eingehende PSTN-Anrufe im Skype for Business Client des Benutzers. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Teams-Client des Benutzers angezeigt.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit lokaler Sprachausgabe

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online. Die PSTN-Konnektivität des Benutzers ist lokal, entweder mit Skype for Business Server im Hybridmodus oder Cloud Connector Edition. Um diese Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität zu migrieren, müssen Sie die Benutzer für Direct Routing aktivieren. Mit Direct Routing verbinden sich PSTN-Trunks direkt mit dem Direct Routing-Dienst über Ihren lokalen Session Border Controller (SBC).

Die grundlegenden Schritte sind unten aufgeführt.  Die Schritte 1 bis 4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können jedoch in beliebiger Reihenfolge ausgeführt werden. Diese Schritte sollten vor Schritt 5 abgeschlossen werden.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business Modi festlegen, stellen Sie sicher, dass Sie alle vorhandenen Inselbenutzer durch explizites Zuweisen des Inselmodus zuweisen, wie zuvor beschrieben.

2. Konfigurieren Sie Ihren Mandanten für Direct Routing. Siehe [Zusammenfassung der Konfiguration von Direct Routing pro Mandant](#summary-of-per-tenant-configuration-of-direct-routing).

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Sie können Poicies jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer auf den TeamsOnly-Modus aktualisiert wird.

4. Vorbereiten ausgewählter Benutzer für die Sprachmigration:
   - Weisen Sie bei Bedarf die Teams Lizenz zu.  Vorausgesetzt, der Benutzer ist bereits in Skype for Business online lokalen VoIP funktionsfähig, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft-Telefon System. Lassen Sie beide Pläne aktiviert, einschließlich der Skype for Business Onlineplan 2-Lizenz.
   - Weisen Sie die gewünschte OnlineVoiceRoutingPolicy zu.

5. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden.

   - Aktualisieren Sie in Microsoft 365 oder Office 365 den Benutzer in den TeamsOnly-Modus (Grant-CsTeamsUpgradePolicy).
   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu ermöglichen, indem Sie Anrufe an Direct Routing anstatt an den lokalen Vermittlungsserver senden.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zum Direct Routing

In diesem Szenario wird der Benutzer weiterhin in Skype for Business lokal verwaltet. Die PSTN-Konnektivität des Benutzers ist ebenfalls lokal. Um diesen Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität zu migrieren, müssen Sie den Benutzer für Direct Routing aktivieren und den Benutzer dann in die Cloud verschieben.

Die grundlegenden Schritte sind unten aufgeführt. Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können jedoch in beliebiger Reihenfolge ausgeführt werden. Sie müssen die Schritte 1 bis 5 vor Schritt 6 ausführen.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business Modi festlegen, stellen Sie sicher, dass Sie vorhandene Inselbenutzer durch explizite Zuweisung des Inselmodus zuweisen, wie zuvor beschrieben.

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie [die Organisation für Skype for Business Hybridbereitstellung](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Konfigurieren Sie Ihren Mandanten für Direct Routing. Siehe [Zusammenfassung der Konfiguration von Direct Routing pro Mandant](#summary-of-per-tenant-configuration-of-direct-routing).

4. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy). Sie können Richtlinien jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer auf TeamsOnly aktualisiert wird.

5. Weisen Sie bei Bedarf die Microsoft 365- oder Office 365-Lizenzen zu.  Der Benutzer sollte sowohl über Teams als auch über Skype for Business Onlineplan 2 und Telefonsystem verfügen. Wenn der Skype for Business Onlineplan 2 deaktiviert ist, aktivieren Sie ihn erneut.

6. Upgrade des Benutzers: Diese Schritte sollten koordiniert werden.

   - Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser mit dem Switch "-MoveToTeams" aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den Switch -MoveToTeams nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus im Mandanten-Remote-PowerShell oder Teams Admin Konsole zu.

   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu ermöglichen, indem Sie Anrufe an Direct Routing anstatt an den lokalen Vermittlungsserver senden.

   - In Microsoft 365 oder Office 365: Weisen Sie die relevante OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu aktivieren.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zum Microsoft-Anrufplan

In diesem Szenario wird der Benutzer weiterhin in Skype for Business lokal verwaltet. Die PSTN-Konnektivität des Benutzers ist ebenfalls lokal. Um diesen Benutzer in den TeamsOnly-Modus mit PSTN-Funktionen zu migrieren, müssen Sie den Benutzer in die Cloud verschieben und entweder seine Nummer vom alten Netzbetreiber zu einem Microsoft-Anrufplan portieren oder dem Benutzer eine neue Nummer zuweisen.

Die grundlegenden Schritte sind unten aufgeführt. Die Schritte 1 bis 5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können jedoch in beliebiger Reihenfolge ausgeführt werden. Sie müssen die Schritte 1 bis 5 vor Schritt 6 ausführen.

1. Wenn Sie die mandantenweite Richtlinie auf einen der Skype for Business Modi festlegen, stellen Sie sicher, dass Sie vorhandene Inselbenutzer durch explizite Zuweisung des Inselmodus zuweisen, wie zuvor beschrieben.

2. Wenn dies noch nicht geschehen ist, konfigurieren Sie [die Organisation für Skype for Business Hybridbereitstellung](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Konfigurieren Sie bei Bedarf verschiedene Teams Richtlinien für diese Benutzer (z. B. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Sie können Richtlinien jederzeit konfigurieren. Wenn Sie jedoch sicherstellen möchten, dass Benutzer beim Upgrade über die richtige Konfiguration verfügen, konfigurieren Sie diese Richtlinien, bevor der Benutzer auf TeamsOnly aktualisiert wird.

4. Weisen Sie bei Bedarf die Microsoft 365- oder Office 365-Lizenzen zu. Der Benutzer sollte sowohl über Teams als auch über Skype for Business Onlineplan 2 und Telefonsystem verfügen. Wenn der Skype for Business Onlineplan 2 deaktiviert ist, aktivieren Sie ihn erneut.

5. Rufen Sie Telefonnummern für Ihre Benutzer ab. (Ausführliche Informationen finden [Sie unter Verwalten von Telefonnummern für Ihre Organisation](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)

   - Wenn Sie die Nummern wiederverwenden, senden Sie eine Portierungsanforderung an Ihren Netzbetreiber.
   - Alternativ können Sie neue Nummern direkt bei Microsoft erwerben.

6. Aktualisieren Sie den Benutzer, und weisen Sie bei Bedarf LineUri zu. Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser mit der Option -MoveToTeams aus.

    - Wenn Sie Nummern zu Microsoft portieren, sollten Sie den Zeitpunkt dieses Vorgangs koordinieren, der beim Portieren ausgeführt wird.

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie den LineUri für den Benutzer ändern, nachdem der Benutzer online verschoben wurde, indem Sie Set-CsPhoneNumberAssignment verwenden.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration von Direct Routing pro Mandant

1. Überprüfen Sie [diese Liste](direct-routing-border-controllers.md), um sicherzustellen, dass Ihr Session Border Controller (SBC) mit Direct Routing unterstützt wird. Stellen Sie außerdem sicher, dass Sie über die richtige Firmwareversion verfügen.

2. Koppeln Sie Ihren lokalen SBC mit dem Teams Direct Routing-Dienst. Ausführliche Informationen finden [Sie unter Koppeln des SBC mit dem Direct Routing-Dienst von Telefonsystem](direct-routing-configure.md).

3. Diese Konfiguration ist im Wesentlichen ein Spiegel der lokalen Konfiguration. Die Onlinekonfiguration besteht aus:
   - OnlineVoiceRoutingPolicy (basierend auf der lokalen VoiceRoutingPolicy, wenn Benutzer von Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer aus der lokalen Umgebung mit Enterprise-VoIP migrieren).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Verwendung).
   - OnlineVoiceRoute-Objekte (basierend auf der lokalen VoiceRoute).

Weitere Informationen finden [Sie unter Konfigurieren von Direct Routing](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration

Unabhängig davon, ob Direct Routing oder ein Microsoft-Anrufplan verwendet wird, muss ein Benutzer über EnterpriseVoiceEnabled=true in Azure AD verfügen, damit der Benutzer über PSTN-Funktionen verfügt.  EnterpriseVoiceEnabled ("EV-enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist das, was für Teams wichtig ist.  Die genaue Logik, wie EV-aktiviert auf "true" festgelegt wird, hängt vom folgenden Szenario ab:

- Wenn der Benutzer in lokalen Skype for Business Server ev-fähig ist und dem Benutzer vor dem Verschieben des Benutzers in die Cloud mit Move-CsUser eine Telefonsystem Lizenz zugewiesen wird, wird dem Onlinebenutzer EV-enabled=true bereitgestellt.

- Wenn einem vorhandenen TeamsOnly- oder Skype for Business Online-Benutzer eine Telefonsystem-Lizenz zugewiesen ist, ist EV-aktiviert nicht standardmäßig auf "true" festgelegt. Dies ist auch der Fall, wenn ein lokaler Benutzer vor dem Zuweisen der Telefonsystem Lizenz in die Cloud verschoben wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben:

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>Verwandte Links

[Planen Ihrer Microsoft Teams-Anruflösung](cloud-voice-landing-page.md)

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Konfigurieren der Hybridverbindung zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
