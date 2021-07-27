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
description: Erfahren Sie mehr Teams Optionen für Anrufe über das Festnetz und die Entscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 57327c408331acb3deb4d2269d87a2a30de13a75
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486255"
---
# <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Microsoft stellt für Ihre Exchange (Private Branch Exchange, PBX) umfassende Funktionen über Telefonsystem. Um Benutzern das Anrufen außerhalb Ihrer Organisation zu ermöglichen, müssen Sie Telefonsystem das Public Switched Telephone Network (PSTN) verbinden.

Dieser Artikel befasst sich mit den PstN-Konnektivitätsoptionen. Weitere Informationen zu Microsoft-Sprachlösungen und Details zu den Telefonsystem finden Sie unter Planen ihrer [Teams-Sprachlösung.](cloud-voice-landing-page.md)

Um eine Telefonsystem mit dem PSTN herzustellen, können Sie unter den folgenden Optionen wählen:

- [**Anrufplan.**](#phone-system-with-calling-plan) Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Netzbetreiber.

- [**Operator Verbinden**](#phone-system-with-operator-connect), die derzeit nur in der öffentlichen **Vorschau verfügbar ist.**  Wenn Ihr Verbinden teilnehmer am Microsoft Operator Verbinden-Programm ist, können mit operator Verbinden PSTN-Anrufe und Session Border Controller (SBCs) verwaltet werden. 

- [**Direct Routing**](#phone-system-with-direct-routing), mit dem Sie Ihren eigenen PSTN-Netzbetreiber verwenden können, indem Sie Ihre Session Border Controller (SBC) mit Telefonsystem.


Sie können auch eine Kombination von Optionen auswählen, die es Ihnen ermöglicht, eine Lösung für eine komplexe Umgebung zu entwerfen oder eine mehrstufige Migration zu verwalten.

Beachten Sie, dass sich die von Ihnen ausgewählten Optionen darauf auswirken, wie Telefonsystem Features konfiguriert werden. Weitere Informationen finden Sie unter [Überlegungen zur Konfiguration](#configuration-considerations) weiter unten in diesem Artikel.


## <a name="phone-system-with-calling-plan"></a>Telefonsystem mit Anrufplan 

Telefonsystem Anrufplan ist die In-der-Cloud-Sprachlösung von Microsoft für Teams Benutzer. Dies ist die einfachste Option, mit der eine Verbindung Telefonsystem PSTN hergestellt wird. Mit dieser Option fungiert Microsoft als Ihr PSTN-Netzbetreiber, wie in der folgenden Abbildung dargestellt:

![Diagramm 1 zeigt Telefonsystem mit Anrufplan](media/voice-solutions-simple.png)

Wenn Sie mit Ja antworten, ist Telefonsystem Anrufplan die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht beibehalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Mit dieser Option: 

- Sie erhalten Microsoft-Telefon-System mit zusätzlichen Inlands- oder Auslands anrufplänen, die Anrufe an Telefone auf der ganzen Welt ermöglichen (abhängig von der Art des lizenzierten Diensts).

- Die Bereitstellung oder Wartung einer lokalen Bereitstellung ist nicht erforderlich, da der Anrufplan nicht &mdash; mehr Microsoft 365.

- Hinweis: Bei Bedarf können Sie sich entscheiden, einen unterstützten Session Border Controller (SBC) über Direct Routing für die Interoperabilität mit Drittanbieter-PBXs, Analoggeräten und anderen von SBC unterstützten Telefoniegeräten von Drittanbietern zu verbinden.

Für diese Option ist eine unterbrechungsfreie Verbindung mit Microsoft 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Einrichten eines Anrufplans](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>Telefonsystem mit Operator Verbinden

Wenn Ihr bestehender Netzbetreiber Verbinden am Microsoft Operator Verbinden-Programm teilt, kann er den Dienst verwalten, mit dem PSTN-Anrufe an den Benutzer gesendet Teams. Ihr Netzbetreiber verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und bei der Verwaltung von Hardware sparen können.

Operatoren Verbinden die richtige Lösung für Ihre Organisation, wenn:

- Microsoft-Anrufplan ist in Ihrem geografischen Standort nicht verfügbar.
- Ihr bevorzugter Netzbetreiber ist ein Teilnehmer am Microsoft Operator Verbinden-Programm.
- Sie möchten einen neuen Netzbetreiber suchen, um Anrufe in Der Teams.

Informationen zu den Vorteilen und Anforderungen von Operator Verbinden und eine Liste der an diesem Programm teilnehmenden Netzbetreiber finden Sie unter [Planoperator Verbinden.](operator-connect-plan.md) Informationen zum Konfigurieren von Operatoroperator-Verbinden Sie unter [Konfigurieren von Operatoren Verbinden.](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>Telefonsystem mit Direct Routing

Diese Option stellt eine Telefonsystem mit Ihrem Telefonienetzwerk mithilfe von Direct Routing fest, wie in der folgenden Abbildung dargestellt: 

![Diagramm 5 zeigt die Telefonsystem mit Direct Routing.](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten, Telefonsystem Direct-Routing die richtige Lösung für Sie:

- Sie möchten die Teams mit Telefonsystem.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber beibehalten.
- Sie möchten das Routing vermischen. Einige Anrufe gehen über den Anrufplan, einige über Ihren Netzbetreiber.
- Sie müssen mit PbXs und/oder Geräten von Drittanbietern (z. B. Overheadseiten, analoge Geräte und so weiter) zusammenarbeiten.

Mit dieser Option:

- Sie verbinden Ihre eigenen unterstützten Session Border Controller (SBC)-Daten mit Telefonsystem ohne dass zusätzliche lokale Software benötigt wird.

- Sie können praktisch jeden Telefoniebetreiber mit ihrem Telefonsystem.

- Sie können diese Option konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (Fragen Sie, ob Ihr Netzbetreiber oder Partner diese Option bietet).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten wie einer &mdash; Drittanbieter-PBX und analogen Geräten &mdash; Telefonsystem.

Für diese Option ist Folgendes erforderlich:

- Unterbrechungsfreie Verbindung mit Microsoft 365.

- Bereitstellen und Verwalten eines unterstützten SBC

- Ein Vertrag mit einem Drittanbieter.
  (Es sei denn, die Bereitstellung als Option zum Bereitstellen einer Verbindung mit Drittanbieter-PBX, analogen Geräten oder anderen Telefoniegeräten für Benutzer, die mit Telefonsystem Anrufplan verbunden sind.)

Weitere Informationen zu Direct-Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwalten von Voice Routing-Richtlinien für die Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Überlegungen zur Konfiguration

Die Telefonsystem sind unabhängig von der von Ihnen aktivierten PSTN-Konnektivitätsoption identisch. So stehen beispielsweise Einstellungen für nicht beantwortete Anrufe und Weiterleitungen, Anrufübertragung, benutzerdefinierte Musik im Warteschleifen, Parken von Anrufen, freigegebene Leitungen und Sprach-Apps zur Verfügung. Eine vollständige Liste der Telefonsystem-Features finden Sie unter Dies ist das, was Sie [von ihrer Telefonsystem.](here-s-what-you-get-with-phone-system.md)

Es gibt jedoch einige Funktionsunterschiede, die sich auf die Konfiguration bestimmter Features Telefonsystem auswirken. Beispielsweise sind für das direkte Routing zusätzliche Schritte zum Konfigurieren des Anrufroutings erforderlich. Als weiteres Beispiel stellt Direct Routing location-based-Routing (LBR) zur Verfügung, sodass Sie die gebührenpflichtige Umgehung an bestimmten geografischen Standorten einschränken können, an denen sie nicht zulässig ist. 

In der folgenden Tabelle sind die wichtigsten Konfigurationsunterschiede aufgeführt. Die Abschnitte, die auf die Tabelle folgen, enthalten Links zu weiteren Informationen und Details.

| Option | Beschreibung | Telefonnummernverwaltung | Anrufweiterleitung | Verfügbarkeit von Notrufen |
| :------------| :-------| :-------| :-------| :-------| 
| Anrufpläne | -Microsoft fungiert als PstN-Netzbetreiber.<br>– Sie müssen SBCs nicht kaufen oder verwalten.| Erworben über Microsoft.| -Verwaltet von Microsoft. <br> – Der Administrator konfiguriert Benutzerwählpläne für die Übersetzung von Nummern. | -Aktiviert von Microsoft. <br> -Admin registriert Adressen. <br> -Dynamische Aufrufe werden unterstützt. |
| Operatoren Verbinden | – Der Netzbetreiber verwaltet die PSTN-Konnektivität und SBCs. <br> – Sie müssen SBCs nicht kaufen oder verwalten. | -Wurde über den Netzbetreiber erhalten. <br> – Nummern, die Notfalladressen zugeordnet sind, die vom Netzbetreiber verwaltet werden.  | -Verwaltet vom Netzbetreiber. <br>– Der Administrator konfiguriert Benutzerwählpläne für die Übersetzung von Nummern. | -Vom Netzbetreiber aktiviert. <br> -Admin registriert Adressen. <br> -Dynamische Aufrufe werden unterstützt. |
| Direktes Routing | – Erfordert einen zertifizierten SBC,der bei einem Drittanbieter erworben wurde.<br>-Verbinden SBC auf Telefonsystem.<br> – Verwenden Sie Ihren vorhandenen PSTN-Netzbetreiber. | Über den Netzbetreiber erhalten. | – Erfordert eine zusätzliche Konfiguration durch den Administrator.<br>– Der Administrator konfiguriert Trunkwählpläne für die Nummernübersetzung. <br>-LBR verfügbar, um die gebührenpflichtige Umgehung einzuschränken. | – Erfordert eine zusätzliche Konfiguration durch den Administrator. <br>-Registrierte Adressen werden nicht unterstützt. <br>-Dynamisches Aufrufen wird unterstützt, erfordert aber eine zusätzliche Konfiguration. |
|||||


### <a name="phone-number-management"></a>Telefonnummernverwaltung

Microsoft verfügt über zwei Arten von Telefonnummern: Telefonnummern für Abonnenten (Benutzer), die Benutzern in Ihrer Organisation zugewiesen werden können, und Servicenummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind. Leistungsnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonkonferenzen oder Anrufwarteschleifen zugewiesen werden.

Sie müssen sich entscheiden:

- An welchen Benutzerstandorten benötigen Sie neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) brauche ich?
- Wie portiert ich vorhandene Telefonnummern zu Teams?

Die Art und Weise, wie Sie Telefonnummern erwerben und verwalten, hängt von der PstN-Verbindungsoption ab.

- Informationen zum Verwalten von Telefonnummern für Anrufplan finden Sie unter [Verwalten von Telefonnummern für Ihre Organisation.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Informationen zum Verwalten von Telefonnummern mit Operatoren Verbinden Sie unter Einrichten von [Telefonnummern mit der Verbinden.](operator-connect-configure.md#set-up-phone-numbers)

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter Konfigurieren der Telefonnummer [und Aktivieren von Enterprise-Voicemail und -Voicemail.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>Anrufrouting und Wählpläne

Wie Sie die Anrufrouting konfigurieren, hängt von der PstN-Verbindungsoption ab.  

- Bei Anrufplänen erfolgt der Großteil des Anrufroutings durch die Infrastruktur des Microsoft-Anrufplans. Sie konfigurieren Benutzerwählpläne für die Nummernübersetzung für die Anrufautorisierung und Anrufrouting. Weitere Informationen finden Sie unter [Was sind Wählpläne?.](what-are-dial-plans.md)

- Für die Verbinden wird der Großteil des Anrufroutings vom Netzbetreiber verwaltet.  Sie konfigurieren Benutzerwählpläne für die Nummernübersetzung für die Anrufautorisierung und Anrufrouting. Weitere Informationen finden Sie unter [Was sind Wählpläne?.](what-are-dial-plans.md)

- Für Direct Routing müssen Sie das Anrufrouting konfigurieren, indem Sie die Sprachrouten angeben und Benutzern Richtlinien für das Voice routing zuweisen. Sie können Wählpläne für Nummernübersetzungen auf Trunkebene konfigurieren, um eine Interoperabilität mit Session Border Controller (SBCs) sicherzustellen. Weitere Informationen finden Sie unter [Konfigurieren von Voice Routing für Direct Routing](direct-routing-voice-routing.md), Verwalten von Voice [Routing-Richtlinien](manage-voice-routing-policies.md) und [Übersetzen von Telefonnummern.](direct-routing-translate-numbers.md) 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based Routing für Direct Routing

In einigen Ländern und Regionen ist es ungesetzlich, den PSTN-Netzbetreiber zu umgehen, um die Kosten für Fernrufe zu senken. Location-Based Routing (LBR) für Direct-Routing ermöglicht ihnen, die gebührenpflichtige Umgehung für Teams basierend auf ihrem geografischen Standort einzuschränken. Weitere Informationen zum Planen und Konfigurieren von LBR finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen Contoso das Routing Location-Based Organisation implementiert.


### <a name="emergency-calling"></a>Notrufe

Wie Sie Notrufe konfigurieren, hängt von der jeweiligen PSTN-Konnektivitätsoption ab.

- Bei einem Anrufplan wird jeder Benutzer automatisch für Notrufe aktiviert und muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist. Dynamische Notrufe (basierend auf dem Standort des Teams Clients) werden unterstützt.  

- Bei Operator Verbinden wird jeder Benutzer automatisch für Notrufe aktiviert und muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist, kann aber nur vom Netzbetreiberpartner festgelegt werden. Dynamische Notrufe (basierend auf dem Standort des Teams Clients) werden unterstützt.

- Für Direct Routing müssen Sie Richtlinien für Notrufe für Benutzer definieren, indem Sie eine Richtlinie für das Routing von Teams-Notrufen (TeamsEmergencyCallRoutingPolicy) verwenden, um Notrufnummern und das zugeordnete Routingziel zu definieren. Registrierte Notfallstandorte werden für Direct Routing-Benutzer nicht unterstützt. Für dynamische Notrufe ist eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für die Partnerkonnektivität erforderlich.

Weitere Informationen zu Konzepten und Terminologie für Notrufe sowie zum Konfigurieren von Notrufen und dynamischen Notrufen finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Richtlinien für das Routing von Notrufen für Direct Routing](manage-emergency-call-routing-policies.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen Contoso Notrufe für ihre Organisation implementiert hat.


### <a name="network-topology-for-voice-features"></a>Netzwerktopologie für Sprachfeatures

Wenn Sie dynamische Notrufe oder Location-Based-Routing für Direct-Routing bereitstellen, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkstandorte, Netzwerk-Subnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Sie Ihre Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams](manage-your-network-topology.md)



