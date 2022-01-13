---
title: PSTN-Konnektivitätsoptionen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Erfahren Sie mehr über die Optionen für Teams-Anrufe (PSTN-Konnektivität) und die Entscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49c836687d7652c18b5932bd662d8ee935638d8a
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015275"
---
# <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Microsoft stellt für Ihre Organisation Exchange(PBX)-Funktionen (Private Branch Teams Telefon) Teams Telefon. Um Benutzern das Anrufen außerhalb Ihrer Organisation zu ermöglichen, müssen Sie Teams Telefon das Public Switched Telephone Network (PSTN) verbinden.

Dieser Artikel konzentriert sich auf PSTN-Konnektivitätsoptionen. Weitere Informationen zu Microsoft-Sprachlösungen, einschließlich Details zu Teams Telefon-Features, finden Sie unter Planen [Teams Sprachlösung.](cloud-voice-landing-page.md)

Um eine Teams Telefon mit dem PSTN herzustellen, können Sie unter den folgenden Optionen wählen:

- [**Anrufplan**](#teams-phone-with-calling-plan). Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Anbieter.

- [**Operator Verbinden**](#teams-phone-with-operator-connect). Mit Telefonieanbieter kann Ihr bestehender Netzbetreiber, wenn er am Microsoft Telefonieanbieter-Programm teilnimmt, PSTN-Anrufe und Session Border Controller (SBCs) verwalten. 

- [**Direct Routing**](#teams-phone-with-direct-routing), mit dem Sie Ihren eigenen PSTN-Netzbetreiber verwenden können, indem Sie Ihre Session Border Controller (SBC) mit Teams Telefon.


Sie können auch eine Kombination von Optionen wählen, mit der Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine mehrstufige Migration verwalten können.

Beachten Sie, dass sich die von Ihnen ausgewählten Optionen darauf auswirken, wie Teams Telefon Features konfiguriert werden. Weitere Informationen finden Sie weiter unten in diesem Artikel unter [ Überlegungen zur Konfiguration ](#configuration-considerations).


## <a name="teams-phone-with-calling-plan"></a>Teams Telefon mit Anrufplan 

Teams Telefon Anrufplan ist die Cloud-basierten Sprachlösung von Microsoft für Teams Benutzer. Dies ist die einfachste Option, mit der eine Verbindung Teams Telefon PSTN hergestellt wird. Bei dieser Option fungiert Microsoft als Ihr PSTN-Netzbetreiber, wie im folgenden Diagramm dargestellt:

![In Abbildung 1 ist das Microsoft-Telefonsystems mit Anrufplan dargestellt.](media/voice-solutions-simple.png)

Wenn Sie auf Folgendes mit "Ja" antworten, ist Teams Telefon Anrufplan die richtige Lösung für Sie:

- PSTN-Anrufe sind in Ihrem Land oder Ihrer Region nicht verfügbar.
- Sie müssen nicht bei Ihrem aktuellen Festnetzbetreiber bleiben.
- Sie möchten von Microsoft verwalteten Zugriff auf das Telefonfestnetz nutzen.

Mit dieser Option geschieht Folgendes: 

- Sie erhalten Teams Telefon mit zusätzlichen Inlands- oder Auslands anrufplänen, die Anrufe an Telefone auf der ganzen Welt ermöglichen (abhängig von der Stufe des lizenzierten Diensts).

- Sie benötigen keine Bereitstellung oder Wartung einer lokalen Bereitstellung&mdash;, da der Anrufplan von Microsoft 365 aus ausgeführt wird.

- Hinweis: Bei Bedarf können Sie einen unterstützten Session Border Controller (SBC) über Direct Routing für die Interoperabilität mit Festnetztelefonanlagen von Drittanbietern, analogen Geräten und anderer Telefonieausrüstung von Drittanbietern verbinden, die vom SBC unterstützt werden.

Diese Option erfordert eine ständige Verbindung mit Microsoft 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Anrufplan einrichten](set-up-calling-plans.md)


## <a name="teams-phone-with-operator-connect"></a>Teams Telefon mit Operator Verbinden

Mit Telefonieanbieter, das sich derzeit in der öffentlichen Vorschau befindet, kann Ihr bestehender Netzbetreiber, wenn er am Microsoft Telefonieanbieter-Programm teilnimmt, den Dienst verwalten, um PSTN-Anrufe an Teams zu übertragen. Ihr Netzbetreiber verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und der Verwaltung von Hardware sparen können.

Telefonieanbieter könnte die richtige Lösung für Ihr Unternehmen sein, wenn:

- Der Microsoft-Anrufplan an Ihrem geografischen Standort nicht verfügbar ist.
- Ihr bevorzugter Netzbetreiber Teilnehmer am Microsoft Telefonieanbieter-Programm ist.
- Sie einen neuen Netzbetreiber finden möchten, um Anrufe in Teams zu ermöglichen.

Informationen zu den Vorteilen und Anforderungen von Telefonieanbieter sowie eine Liste der an diesem Programm teilnehmenden Netzbetreiber finden Sie unter [Plan Telefonieanbieter](operator-connect-plan.md). Informationen zum Konfigurieren von Telefonieanbieter finden Sie unter [Telefonieanbieter konfigurieren](operator-connect-configure.md).


## <a name="teams-phone-with-direct-routing"></a>Teams Telefon mit Direct Routing

Diese Option stellt eine Teams Telefon mit Ihrem Telefonienetzwerk mithilfe von Direct Routing fest, wie in der folgenden Abbildung dargestellt: 

![Abbildung 5 zeigt ein Telefonsystem mit Direct Routing.](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten, Teams Telefon Direct-Routing die richtige Lösung für Sie:

- Sie möchten die Teams mit Teams Telefon.
- Sie müssen bei Ihrem aktuellen Festnetzbetreiber bleiben.
- Sie möchten verschiedene Routing-Formen nutzen, einige Anrufe laufen über den Anrufplan und andere über Ihren Netzbetreiber.
- Sie müssen mit PbXs und/oder Geräten von Drittanbietern zusammenarbeiten, z. B. Overheadseiten, analoge Geräte und so weiter.

Mit dieser Option geschieht Folgendes:

- Sie verbinden Ihre eigenen unterstützten Session Border Controller (SBC)-Daten mit Teams Telefon ohne dass zusätzliche lokale Software benötigt wird.

- Sie können praktisch jeden Telefonieanbieter mit Ihrem Teams Telefon.

- Sie können diese Option selbst konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (fragen Sie Ihren Netzbetreiber oder Partner, ob diese Option zur Auswahl steht).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten wie einer Drittanbieter-PBX und analogen Geräten und Geräten &mdash; &mdash; Teams Telefon.

Diese Option setzt Folgendes voraus:

- Ständige Verbindung mit Microsoft 365

- Bereitstellen und Verwalten eines unterstützten SBC

- Einen Vertrag mit einem externen Netzbetreiber
  (Es sei denn, die Bereitstellung als Option zum Bereitstellen einer Verbindung mit Drittanbieter-PBX, analogen Geräten oder anderen Telefoniegeräten für Benutzer, die mit Anrufplan Teams Telefon sind.)

Weitere Informationen zum direkten Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwaltung von Voice-Routing-Richtlinien zur Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Überlegungen zur Konfiguration

Die Teams Telefon sind unabhängig von der von Ihnen aktivierten PSTN-Konnektivitätsoption identisch. Beispielsweise stehen Einstellungen für unbeantwortete Anrufe und Weiterleitung, Anrufweiterleitung, benutzerdefinierte Wartemusik, Anrufparken, gemeinsame Leitung und Sprach-Apps zur Verfügung. Eine vollständige Liste der Teams Telefon finden Sie unter Dies ist das, was Sie [von ihrer Teams Telefon.](here-s-what-you-get-with-phone-system.md)

Es gibt jedoch einige Funktionsunterschiede, die sich auf die Konfiguration bestimmter Features Teams Telefon auswirken. Direktes Routing erfordert beispielsweise zusätzliche Schritte zum Konfigurieren des Anrufroutings. Als weiteres Beispiel bietet Direct Routing Location-Based-Routing (LBR) – damit Sie die Gebührenumgehung an bestimmten geografischen Standorten einschränken können, an denen dies nicht zulässig ist. 

In der folgenden Tabelle werden die primären Konfigurationsunterschiede hervorgehoben. Die Abschnitte, die der Tabelle folgen, enthalten Links zu weiteren Informationen und Details.

| Option | Beschreibung | Telefonnummernverwaltung | Anrufweiterleitung | Verfügbarkeit von Notrufen |
| :------------| :-------| :-------| :-------| :-------| 
| Anrufpläne | -Microsoft fungiert als PSTN-Träger.<br>-Sie müssen keine SBCs kaufen oder verwalten.| Von Microsoft bezogen.| -Verwaltet von Microsoft. <br> -Admin konfiguriert Benutzerwählpläne für die Nummernübersetzung. | -Aktiviert von Microsoft. <br> -Admin registriert Adressen. <br> -Dynamische Anrufe werden unterstützt. |
| Telefonieanbieter | -Netzbetreiber verwaltet PSTN-Konnektivität und SBCs. <br> -Sie müssen keine SBCs kaufen oder verwalten. | -Erhalten durch den Netzbetreiber. <br> - Nummern, die mit Notrufadressen verbunden sind, die vom Netzbetreiber verwaltet werden.  | -Vom Netzbetreiber verwaltet. <br>-Admin konfiguriert Benutzerwählpläne für die Nummernübersetzung. | -Aktiviert durch den Netzbetreiber. <br> -Admin registriert Adressen. <br> -Dynamische Anrufe werden unterstützt. |
| Direct Routing | -Erfordert zertifizierten SBC, der von einem Drittanbieter erworben wurde.<br>-Verbinden SBC auf Teams Telefon.<br> -Verwenden Sie Ihren bestehenden PSTN-Anbieter. | Über den Netzbetreiber bezogen. | -Erfordert zusätzliche Konfiguration durch den Administrator.<br>-Admin konfiguriert Amtswahlpläne für die Nummernübersetzung. <br>-LBR verfügbar, um die Gebührenumgehung einzuschränken. | -Erfordert zusätzliche Konfiguration durch den Administrator. <br>-Registrierte Adressen werden nicht unterstützt. <br>-Registrierte Adressen werden nicht unterstützt. |
|||||


### <a name="phone-number-management"></a>Telefonnummernverwaltung

Microsoft bietet zwei Arten von Telefonnummern: Abonnentennummern (Benutzernummern), die Benutzern in Ihrer Organisation zugewiesen werden können, und Dienstnummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind. Dienstnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.

Sie müssen die folgenden Schritte ausführen:

- Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnenten oder Dienst) benötige ich?
- Wie übertrage ich vorhandene Telefonnummern zu Teams?

Wie Sie Telefonnummern erwerben und verwalten, hängt von Ihrer PSTN-Konnektivitätsoption ab.

- Informationen zum Verwalten von Telefonnummern für den Anrufplan finden Sie unter [Telefonnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Informationen zum Verwalten von Telefonnummern mit Telefonieanbieter finden Sie unter [Telefonnummern mit Telefonieanbieter einrichten](operator-connect-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter [Konfigurieren der Telefonnummer und Aktivieren von Enterprise-Voice und -Voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).


### <a name="call-routing-and-dial-plans"></a>Anrufweiterleitung und Wählpläne

Wie Sie die Anrufweiterleitung konfigurieren, hängt von Ihrer PSTN-Konnektivitätsoption ab.  

- Bei Anrufplänen wird der Großteil der Anrufweiterleitung von der Microsoft-Anrufplaninfrastruktur abgewickelt. Sie konfigurieren Benutzerwählpläne zum Zwecke der Nummernübersetzung für die Anrufberechtigung und Anrufweiterleitung. Weitere Informationen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

- Bei Telefonieanbieter wird der Großteil der Anrufweiterleitung vom Netzbetreiber verwaltet.  Sie konfigurieren Benutzerwählpläne zum Zwecke der Nummernübersetzung für die Anrufberechtigung und Anrufweiterleitung. Weitere Informationen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

- Für direktes Routing müssen Sie das Anrufrouting konfigurieren, indem Sie die VoIP-Routen angeben und den Benutzern VoIP-Routing-Richtlinien zuweisen. Sie können Wählpläne für die Nummernübersetzung auf Amtsleitungsebene konfigurieren, um die Interoperabilität mit Session Border Controllers (SBCs) sicherzustellen. Weitere Informationen finden Sie unter [Voice-Routing für Direct Routing konfigurieren ](direct-routing-voice-routing.md), [Voice-Routing-Richtlinien verwalten ](manage-voice-routing-policies.md) und [ Telefonnummern übersetzen](direct-routing-translate-numbers.md). 


### <a name="location-based-routing-for-direct-routing"></a>Standortbasiertes Routing für Direct Routing

In einigen Ländern und Regionen ist es illegal, den PSTN-Anbieter zu umgehen, um die Kosten für Ferngespräche zu senken. Standortbasiertes Routing (Location-Based Routing, LBR) für direktes Routing ermöglicht es Ihnen, die Gebührenumgehung für Teams-Benutzer basierend auf ihrem geografischen Standort einzuschränken. Weitere Informationen zum Planen und Konfigurieren von LBR finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Standortbasiertes Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, standortbasiertes Routing für seine Organisation implementiert hat.


### <a name="emergency-calling"></a>Notrufe

Wie Sie Notrufe konfigurieren, hängt von Ihrer PSTN-Konnektivitätsoption ab.

- Für den Anrufplan wird jeder Benutzer automatisch für Notrufe aktiviert und muss eine registrierte Notrufadresse haben, die mit der zugewiesenen Telefonnummer verknüpft ist. Dynamische Notrufe (basierend auf dem Standort des Teams-Clients) werden unterstützt.  

- Bei Telefonieanbieter wird jeder Benutzer automatisch für Notrufe aktiviert und muss eine registrierte Notrufadresse haben, die mit seiner zugewiesenen Telefonnummer verknüpft ist, die jedoch nur vom Netzbetreiber festgelegt werden kann. Dynamische Notrufe (basierend auf dem Standort des Teams-Clients) werden unterstützt.

- Für das direkte Routing müssen Sie Notrufrichtlinien für Benutzer definieren, indem Sie eine Teams-Notruf-Routing-Richtlinien (TeamsEmergencyCallRoutingPolicy) verwenden, um Notrufnummern und das zugehörige Routingziel zu definieren. Registrierte Notfallstandorte werden für Direct Routing-Benutzer nicht unterstützt. Für dynamische Notrufe ist eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für die Partnerkonnektivität erforderlich.

Weitere Informationen zu Notrufkonzepten und -terminologie sowie zum Konfigurieren von Notrufen und dynamischen Notrufen finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Notruf-Routing-Richtlinien für Direct Routing](manage-emergency-call-routing-policies.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, Notrufe für seine Organisation implementiert hat.


### <a name="network-topology-for-voice-features"></a>Netzwerkeinstellungen für Cloud Voice-Features

Wenn Sie dynamische Notrufe oder standortbasiertes Routing für direktes Routing bereitstellen, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkstandorte, Netzwerksubnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features in Microsoft Teams](manage-your-network-topology.md)



