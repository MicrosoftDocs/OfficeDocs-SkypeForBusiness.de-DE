---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940648"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>PSTN-Überlegungen beim Upgrade auf Teams &mdash; für IT-Administratoren

In diesem Artikel werden die Überlegungen zum öffentlichen Switched Telephone Network (PSTN) beim Upgrade auf Teams beschrieben. Dieser Artikel ist der sechste von mehreren, die Upgrade-Konzepte und Implementierung für IT-Administratoren beschreiben.  

- [Übersicht](upgrade-to-teams-on-prem-overview.md)
- [Upgrade-Methoden](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Tools zum Verwalten des Upgrades](upgrade-to-teams-on-prem-tools.md)
- [Weitere Überlegungen für Organisationen mit Skype for Business lokal](upgrade-to-teams-on-prem-considerations.md)
- [Implementieren des Upgrades](upgrade-to-teams-on-prem-implement.md)
- **Überlegungen zum öffentlichen Switched Telephone Network (** dieser Artikel)

Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:

- [Koexistenz von Teams und Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Koexistenzmodus – Referenz](migration-interop-guidance-for-teams-with-skype.md)
- [Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > Die Verwendung von Telefonsystemen mit Teams wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet.  Wenn sich der Benutzer im Modus "Inseln" befindet, wird das Telefon System nur von Skype for Business unterstützt. 


## <a name="pstn-calling-scenarios"></a>Szenarien für PSTN-Anrufe

Beim Umstieg auf den TeamsOnly-Modus gibt es vier mögliche Anrufszenarien:

- [Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan](#from-skype-for-business-online-with-microsoft-calling-plans). Nach dem Upgrade wird dieser Benutzer weiterhin über einen Microsoft-Anrufplan verfügen.

- [Ein Benutzer in Skype for Business Online mit lokalen Sprachfunktionen](#from-skype-for-business-online-with-on-premises-voice) über Skype for Business lokal oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers an Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionalität verfügt.

- [Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), der zu Online wechseln und die lokale PSTN-Konnektivität aufrecht erhalten soll.  Wenn Sie diesen Benutzer zu Teams migrieren, muss das lokale Skype for Business-Konto des Benutzers in die Cloud verschoben und koordiniert werden, um die Migration des Benutzers zur direkten Weiterleitung zu koordinieren. 

- [Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), der in den Online-und mit einem Microsoft-Anrufplan umziehen wird.  Wenn Sie diesen Benutzer zu Teams migrieren, müssen Sie das lokale Skype for Business-Konto des Benutzers in die Cloud verschieben und diesen Schritt entweder mit a) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B durch stellen, um eine neue Teilnehmernummer aus verfügbaren Regionen zuzuweisen.

Dieser Artikel enthält nur eine allgemeine Übersicht. Weitere Informationen finden Sie unter [direkte Routing](direct-routing-landing-page.md) -und [Anrufpläne](calling-plan-landing-page.md)für Telefonsysteme. 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Von Skype for Business Online mit Microsoft-Anrufplänen 

Hierbei handelt es sich um das einfachste Upgrade-Szenario mit Sprachausgabe. 

1. Stellen Sie sicher, dass Benutzern eine Teams-Lizenz zugewiesen wurde. Wenn Sie eine Microsoft 365-oder Office 365-Lizenz zuweisen, werden die Teams standardmäßig aktiviert, es sei denn, Sie haben zuvor die Teams-Lizenz deaktiviert, sollte keine Aktion erforderlich sein.

2.  Wenn Benutzer bereits über einen Microsoft-Anrufplan mit einer Telefonnummer verfügen, besteht die einzige erforderliche Änderung darin, den Benutzer TeamsOnly-Modus in TeamsUpgradePolicy zuzuweisen.  Vor dem Zuweisen des TeamsOnly-Modus werden eingehende PSTN-Anrufe im Skype for Business-Client des Benutzers landen. Nach dem Upgrade auf den TeamsOnly-Modus werden eingehende PSTN-Anrufe im Team-Client des Benutzers landen.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Von Skype for Business Online mit Lokalsprache

In diesem Szenario befindet sich der Benutzer bereits in Skype for Business Online, seine PSTN-Konnektivität ist aber lokal, entweder mit Skype for Business Server im Hybrid Modus oder mit Cloud Connector Edition. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass Sie für das direkte Routing aktiviert werden können, in dem PSTN-Trunks über Ihren lokalen Session Border Controller (SBC) direkt mit dem Direct Routing-Dienst in der Cloud verbunden sind.

Die grundlegenden Schritte sind im folgenden aufgeführt.  Die Schritte 1-4 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 5 abgeschlossen sein sollten.

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass Sie alle vorhandenen Inseln-Benutzer übernehmen, indem Sie Ihnen, wie zuvor beschrieben, explizit den Inseln-Modus zuweisen.

2. Konfigurieren Sie Ihren Mandanten für die direkte Weiterleitung. Siehe [Zusammenfassung der Konfiguration des direkten Routings pro Mandanten](#summary-of-per-tenant-configuration-of-direct-routing).

3. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (beispielsweise TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer in den TeamsOnly-Modus wechselt.

4. Vorbereiten der Auswahl von Benutzern für die Sprach Migration: 
   - Falls erforderlich, weisen Sie die Teams-Lizenz zu.  Vorausgesetzt, dass der Benutzer bereits in der lokalen Skype for Business Online-Sprachausgabe funktionsfähig ist, verfügt der Benutzer bereits über Skype for Business Plan 2 und Microsoft Phone System. Belasse beide Pläne aktiviert, einschließlich der Lizenz für Skype for Business Online Plan 2.  
   - Weisen Sie den gewünschten OnlineVoiceRoutingPolicy zu. 

5. Aktualisieren des Benutzers: diese Schritte sollten koordiniert werden. 

   - Aktualisieren Sie in Microsoft 365 oder Office 365 den Benutzer in den TeamsOnly-Modus (Grant-CsTeamsUpgradePolicy).
   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu aktivieren, indem Sie Anrufe an das direkte Routing statt an den lokalen Vermittlungs Server senden.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zur direkten Weiterleitung

In diesem Szenario ist der Benutzer weiterhin in Skype for Business lokal beheimatet, und seine PSTN-Konnektivität ist auch lokal. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, dass Sie für direktes Routing und anschließendes Verschieben des Benutzers in die Cloud aktiviert werden können. 
 
Die grundlegenden Schritte sind im folgenden aufgeführt.  Die Schritte 1-5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 6 abgeschlossen sein sollten.

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass die Benutzer von bestehenden Inseln auf dem Stand sind, indem Sie den Inseln-Modus explizit zuweisen (wie zuvor beschrieben).

2. Wenn Sie dies noch nicht getan haben, [Konfigurieren Sie die Organisation für Skype for Business-Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Konfigurieren Sie Ihren Mandanten für die direkte Weiterleitung. Siehe [Zusammenfassung der Konfiguration des direkten Routings pro Mandanten](#summary-of-per-tenant-configuration-of-direct-routing).

4. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (z. b. TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer auf TeamsOnly aktualisiert wird.

5. Weisen Sie bei Bedarf die Microsoft 365-oder Office 365-Lizenzen zu.  Der Benutzer sollte sowohl über Teams als auch über Skype for Business Online Plan 2 sowie über das Telefon System verfügen. Wenn Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

6. Aktualisieren des Benutzers: diese Schritte sollten koordiniert werden. 

   - Führen Sie mit den lokalen Skype for Business-Tools Move-CsUser mit-MoveToTeams-Switch aus. Wenn Sie eine Version von Skype for Business Server verwenden, die den-MoveToTeams-Schalter nicht unterstützt, führen Sie zuerst Move-CsUser aus, und weisen Sie dann den TeamsOnly-Modus in der Mandanten-Remote-PowerShell oder der Team-Admin-Konsole zu.

   - Konfigurieren Sie auf dem SBC das VoIP-Routing, um eingehende Anrufe zu aktivieren, indem Sie Anrufe an das direkte Routing statt an den lokalen Vermittlungs Server senden. 

   - In Microsoft 365 oder Office 365: weisen Sie die relevanten OnlineVoiceRoutingPolicy zu, um ausgehende Anrufe zu ermöglichen. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Von Skype for Business Server lokal mit Enterprise-VoIP zu Microsoft-Anrufplan

In diesem Szenario ist der Benutzer weiterhin in Skype for Business lokal beheimatet, und seine PSTN-Konnektivität ist auch lokal. Das Migrieren dieser Benutzer in den TeamsOnly-Modus mit PSTN-Funktionalität bedeutet, den Benutzer in die Cloud zu verschieben und entweder seine Nummer vom alten Netzbetreiber zu einem Microsoft-Anrufplan zu portieren oder dem Benutzer eine neue Nummer zuzuweisen. 

Die grundlegenden Schritte sind im folgenden aufgeführt.Die Schritte 1-5 sind in der vorgeschlagenen Reihenfolge aufgeführt, können aber in beliebiger Reihenfolge ausgeführt werden. Der Schlüssel besteht darin, dass alle diese Schritte vor Schritt 6 abgeschlossen sein sollten. 

1. Wenn Sie die Mandantenweite Richtlinie auf einen der Skype for Business-Modi festlegen, sollten Sie sicherstellen, dass die Benutzer von bestehenden Inseln auf dem Stand sind, indem Sie den Inseln-Modus explizit zuweisen (wie zuvor beschrieben). 

2. Wenn Sie dies noch nicht getan haben, [Konfigurieren Sie die Organisation für Skype for Business-Hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Konfigurieren Sie bei Bedarf verschiedene Teamrichtlinien für diese Benutzer (beispielsweise TeamsMessagingPolicy, TeamsMeetingPolicy usw.). Dies kann jederzeit erfolgen, doch wenn Sie sicherstellen möchten, dass Benutzer beim Upgrade die richtige Konfiguration haben, empfiehlt es sich, dies zu tun, bevor der Benutzer auf TeamsOnly aktualisiert wird. 

4. Weisen Sie bei Bedarf die Microsoft 365-oder Office 365-Lizenzen zu.Der Benutzer sollte sowohl über Teams als auch über Skype for Business Online Plan 2 sowie über das Telefon System verfügen. Wenn Skype for Business Online Plan 2 deaktiviert ist, aktivieren Sie es erneut.  

5. Holen Sie sich Telefonnummern für Ihre Benutzer. (Einzelheiten finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Wenn Sie die Nummern wieder verwenden werden, senden Sie eine Portierungs Anfrage an Ihren Netzbetreiber.  
   - Alternativ können Sie neue Nummern direkt von Microsoft erwerben. 

6. Aktualisieren Sie den Benutzer, und weisen Sie lineURI zu, falls erforderlich. Führen Sie mithilfe der lokalen Skype for Business-Tools Move-CsUser mit dem-MoveToTeams-Schalter aus.  

    - Wenn Sie Nummern an Microsoft portieren, sollten Sie die Anzeigedauer dieses Vorgangs koordinieren, damit diese beim Auftreten des Ports erfolgen kann. 

    - Wenn Sie neue Nummern von Microsoft verwenden, müssen Sie die LineUri für den Benutzer ändern. Dies muss erfolgen, nachdem der Benutzer mithilfe von "CsOnlineVoiceUser" Online verschoben wurde.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Zusammenfassung der Konfiguration des direkten Routings pro Mandanten 

1. Überprüfen Sie [Diese Liste](direct-routing-border-controllers.md), um sicherzustellen, dass Ihr Session Border Controller (SBC) beim direkten Routing unterstützt wird. Sie müssen auch sicherstellen, dass Sie über die richtige Firmware-Version verfügen.  

2. Koppeln Sie Ihren lokalen SBC mit dem Direct Routing-Dienst von Teams. Ausführliche Informationen finden Sie unter [Koppeln des SBC mit dem Direct Routing-Dienst des Telefonsystems](direct-routing-configure.md). 

3. Diese Konfiguration ist im Grunde eine Spiegelung der lokalen Konfiguration. Die Online-Konfiguration besteht aus: 
   - OnlineVoiceRoutingPolicy (basierend auf dem lokalen VoiceRoutingPolicy, wenn Benutzer von Skype for Business Online migriert werden, und basierend auf VoicePolicy, wenn Benutzer von lokal mit Enterprise-VoIP migriert werden).
   - OnlinePSTNUsage-Objekte (basierend auf der lokalen PSTN-Nutzung). 
   - OnlineVoiceRoute-Objekte (basierend auf lokalen VoiceRoute) 

Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Verwalten der EnterpriseVoiceEnabled-Eigenschaft während der Migration 

Unabhängig davon, ob Sie das direkte Routing oder einen Microsoft-Anrufplan verwenden, muss ein Benutzer EnterpriseVoiceEnabled = true in Azure AD besitzen, damit der Benutzer PSTN-Funktionalität hat.  EnterpriseVoiceEnabled ("EV-Enabled") ist eine Eigenschaft (keine Richtlinie), die sowohl in einem lokalen Verzeichnis als auch in der Cloud vorhanden ist. Der Wert in der Cloud ist wichtig für Teams.  Die genaue Logik, wie EV-Enabled auf true festgelegt wird, hängt vom folgenden Szenario ab: 

- Wenn der Benutzer in lokalen Skype for Business-Servern EV-fähig ist und dem Benutzer eine Telefon System Lizenz zugewiesen ist, bevor der Benutzer mit Move-CsUser in die Cloud verschoben wird, wird der Online-Benutzer mit EV-Enabled = true bereitgestellt. 

- Wenn einem vorhandenen TeamsOnly-oder Skype for Business Online-Benutzer eine Telefon System Lizenz zugewiesen ist, ist EV-Enabled standardmäßig nicht auf "true" festgelegt.  Dies ist auch der Fall, wenn ein lokales Benutzer vor dem Zuweisen der Telefon System Lizenz in die Cloud verschoben wird. In beiden Fällen muss der Administrator das folgende Cmdlet angeben: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungs Migrations Diensts (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

