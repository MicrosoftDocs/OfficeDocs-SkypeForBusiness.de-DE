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
description: Erfahren Sie mehr über Teams Anrufoptionen (PSTN-Konnektivität) und die Entscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285941"
---
# <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Microsoft bietet vollständige Nebenstellenanlagenfunktionen (Private Branch Exchange) für Ihre Organisation über Telefonsystem. Damit Benutzer jedoch Anrufe außerhalb Ihrer Organisation tätigen können, müssen Sie Telefonsystem mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) verbinden.

Dieser Artikel befasst sich mit PSTN-Konnektivitätsoptionen. Weitere Informationen zu Microsoft-Sprachlösungen und Ausführliche Informationen zu Telefonsystem Features finden Sie unter [Planen Ihrer Teams VoIP-Lösung.](cloud-voice-landing-page.md)

Um Telefonsystem mit dem PSTN zu verbinden, können Sie aus den folgenden Optionen auswählen:

- [**Anrufplan**](#phone-system-with-calling-plan). Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem FESTNETZ-Netzbetreiber.

- [**Operator Verbinden**](#phone-system-with-operator-connect), der derzeit nur in der öffentlichen Vorschau verfügbar **ist.**  Wenn Ihr vorhandener Netzbetreiber teilnehmer am Microsoft Operator Verbinden-Programm ist, können sie mit operator Verbinden PSTN-Anrufe und Session Border Controller (SBCs) verwalten. 

- [**Direct Routing**](#phone-system-with-direct-routing), mit dem Sie Ihren eigenen PSTN-Netzbetreiber verwenden können, indem Sie Ihre Session Border Controller (SBC) mit Telefonsystem verbinden.


Sie können auch eine Kombination von Optionen auswählen, mit denen Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine Migration mit mehreren Schritten verwalten können.

Beachten Sie, dass sich die von Ihnen gewählten Optionen auf die Konfiguration einiger Telefonsystem Features auswirken. Weitere Informationen finden Sie unter [Konfigurationsüberlegungen](#configuration-considerations) weiter unten in diesem Artikel.


## <a name="phone-system-with-calling-plan"></a>Telefonsystem mit Anrufplan 

Telefonsystem mit Anrufplan ist die All-in-the-Cloud-VoIP-Lösung von Microsoft für Teams Benutzer. Dies ist die einfachste Option, die Telefonsystem mit dem PSTN verbindet. Mit dieser Option fungiert Microsoft als Ihr PSTN-Netzbetreiber, wie im folgenden Diagramm dargestellt:

![Diagramm 1 zeigt Telefonsystem mit Anrufplan](media/voice-solutions-simple.png)

Wenn Sie mit "Ja" antworten, ist Telefonsystem mit Anrufplan die richtige Lösung für Sie:

- Der Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht aufbewahren.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Merkmale dieser Option: 

- Sie erhalten das Microsoft-Telefonsystem mit zusätzlichen nationalen oder internationalen Anrufplänen, die Telefonanrufe in die ganze Welt ermöglichen (je nach lizenzierter Serviceebene).

- Sie benötigen keine Bereitstellung oder Wartung einer lokalen &mdash; Bereitstellung, da der Anrufplan außerhalb Microsoft 365 ausgeführt wird.

- Hinweis: Bei Bedarf können Sie einen unterstützten Session Border Controller (SBC) über Direct Routing verbinden, um Interoperabilität mit Nebenstellenanlagen von Drittanbietern, analogen Geräten und anderen Telefoniegeräten von Drittanbietern herzustellen, die vom SBC unterstützt werden.

Diese Option erfordert eine ständige Verbindung mit Microsoft 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Verfügbarkeit von Land und Region für Anrufpläne](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Einrichten des Anrufplans](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>Telefonsystem mit Operator-Verbinden

Wenn sich der Betreiber Verbinden derzeit in der öffentlichen Vorschau befindet und Ihr vorhandener Netzbetreiber ein Teilnehmer am Microsoft Operator Verbinden-Programm ist, kann er den Dienst verwalten, um PSTN-Anrufe an Teams zu übermitteln. Ihr Netzbetreiber verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und der Verwaltung von Hardware sparen können.

Operator Verbinden ist möglicherweise die richtige Lösung für Ihre Organisation, wenn:

- Der Microsoft-Anrufplan ist an Ihrem geografischen Standort nicht verfügbar.
- Ihr bevorzugter Netzbetreiber ist ein Teilnehmer am Microsoft Operator Verbinden-Programm.
- Sie möchten einen neuen Netzbetreiber finden, um Anrufe in Teams zu ermöglichen.

Informationen zu den Vorteilen und Anforderungen von Operator Verbinden und eine Liste der Netzbetreiber, die an diesem Programm teilnehmen, finden Sie unter [Plan Operator Verbinden.](operator-connect-plan.md) Informationen zum Konfigurieren von Operator-Verbinden finden Sie unter ["Operator konfigurieren" Verbinden.](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>Telefonsystem mit Direct Routing

Diese Option verbindet Telefonsystem über Direct Routing mit Ihrem Telefonienetzwerk, wie im folgenden Diagramm dargestellt: 

![Diagramm 5 zeigt Telefonsystem mit Direct Routing](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten können, ist "Telefonsystem mit Direct Routing" die richtige Lösung für Sie:

- Sie möchten Microsoft Teams mit "Telefonsystem" verwenden.
- Sie müssen bei Ihrem aktuellen Festnetzbetreiber bleiben.
- Sie möchten verschiedene Routing-Formen nutzen, einige Anrufe laufen über den Anrufplan und andere über Ihren Netzbetreiber.
- Sie müssen mit Nebenstellenanlagen von Drittanbietern und/oder Geräten wie z. B. Overhead-Pagern, analogen Geräten usw. zusammenarbeiten.

Merkmale dieser Option:

- Sie verbinden Ihren eigenen unterstützten Session Border Controller (SBC) mit Telefonsystem, ohne dass zusätzliche lokale Software erforderlich ist.

- Sie können praktisch jeden Telefonieanbieter mit Telefonsystem verwenden.

- Sie können diese Option selbst konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (fragen Sie Ihren Netzbetreiber oder Partner, ob diese Option zur Auswahl steht).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten &mdash; wie einer Nebenstellenanlage eines Drittanbieters und analogen Geräten &mdash; und Telefonsystem konfigurieren.

Diese Option setzt Folgendes voraus:

- Ständige Verbindung mit Microsoft 365

- Bereitstellen und Verwalten eines unterstützten SBC

- Ein Vertrag mit einem Drittanbietern-Netzbetreiber. (Außer wenn sie als Option bereitgestellt wird, um eine Verbindung mit Nebenstellenanlagen, Analoggeräten oder anderen Telefoniegeräten von Drittanbietern für Benutzer zu ermöglichen, die sich in einem Telefonsystem mit Anrufplänen befinden.)

Weitere Informationen zu Direct Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwalten von VoIP-Routingrichtlinien für die Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für Direct Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Überlegungen zur Konfiguration

Die meisten Telefonsystem Features sind unabhängig von der gewählten PSTN-Verbindungsoption identisch. Beispielsweise sind Einstellungen für nicht beantwortete Anrufe und Weiterleitungen, Anrufübertragung, benutzerdefinierte Wartemusik, Parken von Anrufen, gemeinsame Leitung und Sprach-Apps verfügbar. Eine vollständige Liste der Telefonsystem Features finden Sie hier, [was Sie mit Telefonsystem erhalten.](here-s-what-you-get-with-phone-system.md)

Es gibt jedoch einige Unterschiede bei der Funktionalität, die sich auf die Konfiguration bestimmter Telefonsystem-Features auswirken. Direct Routing erfordert beispielsweise zusätzliche Schritte zum Konfigurieren des Anrufroutings. Als weiteres Beispiel stellt Direct Routing standortbasiertes Routing (Location-Based-Routing, LBR) bereit, sodass Sie die Gebührenumgehung an bestimmten geografischen Standorten einschränken können, an denen sie nicht zulässig ist. 

In der folgenden Tabelle werden die wichtigsten Konfigurationsunterschiede hervorgehoben. Die Abschnitte, die auf die Tabelle folgen, enthalten Links zu weiteren Informationen und Details.

| Option | Beschreibung | Telefon Nummernverwaltung | Anrufweiterleitung | Verfügbarkeit von Notrufen |
| :------------| :-------| :-------| :-------| :-------| 
| Anrufpläne | -Microsoft fungiert als PSTN-Netzbetreiber.<br>- Sie müssen keine SBCs kaufen oder verwalten.| Über Microsoft abgerufen.| -Verwaltet von Microsoft. <br> -Administrator konfiguriert Benutzerwählpläne für die Übersetzung von Nummern. | -Aktiviert von Microsoft. <br> -Admin registriert Adressen. <br> –Dynamische Aufrufe werden unterstützt. |
| Operator Connect | -Carrier verwaltet PSTN-Konnektivität und SBCs. <br> - Sie müssen keine SBCs kaufen oder verwalten. | -Über Netzbetreiber abgerufen. <br> – Nummern, die notfalladressen zugeordnet sind, die vom Netzbetreiber verwaltet werden.  | -Verwaltet vom Netzbetreiber. <br>-Administrator konfiguriert Benutzerwählpläne für die Übersetzung von Nummern. | -Aktiviert nach Netzbetreiber. <br> -Admin registriert Adressen. <br> –Dynamische Aufrufe werden unterstützt. |
| Direct Routing | – Erfordert einen zertifizierten SBC, der von einem Drittanbieter erworben wurde.<br>-Verbinden Ihren SBC an Telefonsystem.<br> – Verwenden Sie Ihren vorhandenen PSTN-Netzbetreiber. | Über Netzbetreiber abgerufen. | –Erfordert eine zusätzliche Konfiguration durch den Administrator.<br>-Admin konfiguriert Trunkwählpläne für die Übersetzung von Nummern. <br>-LBR verfügbar, um die Gebührenumgehung einzuschränken. | –Erfordert eine zusätzliche Konfiguration durch den Administrator. <br>-Registrierte Adressen werden nicht unterstützt. <br>–Dynamisches Aufrufen wird unterstützt, erfordert jedoch eine zusätzliche Konfiguration. |
|||||


### <a name="phone-number-management"></a>Telefon Nummernverwaltung

Microsoft verfügt über zwei Arten von Telefonnummern: Telefonnummern für Abonnenten (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können, und Servicenummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind. Dienstnummern verfügen über eine höhere gleichzeitige Anrufkapazität als Teilnehmernummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschleifen zugewiesen werden.

Sie müssen entscheiden:

- Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) benöte ich?
- Wie portiere ich vorhandene Telefonnummern zu Teams?

Die Art und Weise, wie Sie Telefonnummern erwerben und verwalten, unterscheidet sich je nach Ihrer PSTN-Verbindungsoption.

- Informationen zum Verwalten von Telefonnummern für Anrufpläne finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Informationen zum Verwalten von Telefonnummern mit operator Verbinden finden Sie unter Einrichten von [Telefonnummern mit Operator Verbinden](operator-connect-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter [Konfigurieren der Telefonnummer und Aktivieren von Enterprise-VoIP und Voicemail.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>Anrufweiterleitung und Wählpläne

Die Konfiguration des Anrufroutings unterscheidet sich je nach PsTN-Verbindungsoption.  

- Bei Anrufplänen wird der Großteil des Anrufroutings von der Microsoft-Anrufplaninfrastruktur verarbeitet. Sie konfigurieren Benutzerwählpläne für die Nummernübersetzung für die Anrufautorisierung und anrufweiterleitung. Weitere Informationen finden Sie unter ["Was sind Wählpläne?".](what-are-dial-plans.md)

- Für operator Verbinden wird der Großteil der Anrufweiterleitung vom Netzbetreiber verwaltet.  Sie konfigurieren Benutzerwählpläne für die Nummernübersetzung für die Anrufautorisierung und anrufweiterleitung. Weitere Informationen finden Sie unter ["Was sind Wählpläne?".](what-are-dial-plans.md)

- Für Direct Routing müssen Sie das Anrufrouting konfigurieren, indem Sie die VoIP-Routen angeben und Benutzern VoIP-Routingrichtlinien zuweisen. Sie können Wählpläne für die Nummernübersetzung auf Trunkebene konfigurieren, um die Interoperabilität mit Session Border Controllern (SBCs) sicherzustellen. Weitere Informationen finden Sie unter [Konfigurieren des VoIP-Routings für Direct Routing,](direct-routing-voice-routing.md) [Verwalten von VoIP-Routingrichtlinien](manage-voice-routing-policies.md) und [Übersetzen von Telefonnummern.](direct-routing-translate-numbers.md) 


### <a name="location-based-routing-for-direct-routing"></a>Standortbasiertes Routing für Direct Routing

In einigen Ländern und Regionen ist es unzulässig, den Festnetzanbieter zu umgehen, um die Kosten für Ferngespräche zu senken. mit Location-Based Routing (LBR) für Direct Routing können Sie die Gebührenumgehung für Teams Benutzer basierend auf ihrem geografischen Standort einschränken. Weitere Informationen zum Planen und Konfigurieren von LBR finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, Location-Based Routing für seine Organisation implementiert hat.


### <a name="emergency-calling"></a>Notrufe

Die Konfiguration von Notrufen unterscheidet sich je nach PsTN-Verbindungsoption.

- Bei Anrufplänen wird jeder Benutzer automatisch für Notrufe aktiviert und benötigt eine registrierte Notfalladresse, die der zugewiesenen Telefonnummer zugeordnet ist. Dynamische Notrufe (basierend auf dem Standort des Teams Clients) werden unterstützt.  

- Für operator Verbinden wird jeder Benutzer automatisch für Notrufe aktiviert und benötigt eine registrierte Notfalladresse, die der zugewiesenen Telefonnummer zugeordnet ist, kann aber nur vom Netzbetreiberpartner festgelegt werden. Dynamische Notrufe (basierend auf dem Standort des Teams Clients) werden unterstützt.

- Für direct Routing müssen Sie Notrufrichtlinien für Benutzer definieren, indem Sie eine Teams Richtlinie für die Notrufweiterleitung (TeamsEmergencyCallRoutingPolicy) verwenden, um Notrufnummern und das zugeordnete Routingziel zu definieren. Registrierte Notfallstandorte werden für Direct Routing-Benutzer nicht unterstützt. Für dynamische Notrufe ist eine zusätzliche Konfiguration für die Weiterleitung von Notrufen und möglicherweise für partnerkonnektivität erforderlich.

Weitere Informationen zu Konzepten und Terminologie für Notrufe und zum Konfigurieren von Notrufen und dynamischen Notrufen finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren der dynamischen Notruffunktion](configure-dynamic-emergency-calling.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Notfall-Anrufweiterleitungsrichtlinien für Direct Routing](manage-emergency-call-routing-policies.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, Notrufe für seine Organisation implementiert hat.


### <a name="network-topology-for-voice-features"></a>Netzwerktopologie für VoIP-Funktionen

Wenn Sie dynamische Notrufe oder Location-Based Routing für Direct Routing bereitstellen, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkstandorte, Netzwerksubnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud voice-Features in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features in Microsoft Teams](manage-your-network-topology.md)



