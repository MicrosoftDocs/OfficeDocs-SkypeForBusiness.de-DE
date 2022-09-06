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
description: Mer informasjon zu Optionen für Teams-Anrufe (PSTN-Konnektivität) und den Entscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d30bc6b35f7f5e145e48b9dbf2793d5caa5d12c
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606584"
---
# <a name="pstn-connectivity-options"></a>PSTN-Konnektivitätsoptionen

Microsoft bietet Ihrem Unternehmen über das Telefonsystem umfassende Funktionen für private Nebenstellenanlagen (PBX). Damit Benutzer jedoch Anrufe außerhalb Ihres Unternehmens tätigen können, müssen Sie das Telefonsystem mit dem öffentlichen Telefonnetz (PSTN) verbinden.

Dieser Artikel konzentriert sich auf PSTN-Konnektivitätsoptionen. Weitere Informationen zu Microsoft-VoIP-Lösungen, einschließlich Details zu Telefonsystemfeatures, finden Sie unter ["Planen Ihrer Teams-VoIP-Lösung](cloud-voice-landing-page.md)".

Um das Telefonsystem mit dem PSTN zu verbinden, können Sie aus den folgenden Optionen wählen:

- [**Anrufplan**](#phone-system-with-calling-plan). Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Anbieter.

- [**Operator Connect**](#phone-system-with-operator-connect). Wenn Ihr bestehender Netzbetreiber am Microsoft Operator Connect-Programm teilnimmt, kann er mit Operator Connect PSTN-Anrufe und Session Border Controller (SBCs) verwalten.

- [**Telefonieanbieter mit Mobil**](#phone-system-with-operator-connect-mobile). Bei Telefonieanbieter mit Mobil ist die SIM-fähige Telefonnummer eines Benutzers auch die Microsoft Teams-Telefonnummer. Wenn Ihr vorhandener Netzbetreiber am Microsoft Telefonieanbieter mit Mobil-Programm teilnimmt, kann er den Dienst für die Bereitstellung von PSTN-Anrufen an Teams verwalten.  **Telefonieanbieter mit Mobil ist eine öffentliche Vorschauversion.**

- [**Direktes Routing**](#phone-system-with-direct-routing), mit dem Sie Ihren eigenen PSTN-Anbieter verwenden können, indem Sie Ihre Session Border Controller(s) (SBC) mit dem Telefonsystem verbinden.

Sie können auch eine Kombination von Optionen wählen, mit der Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine mehrstufige Migration verwalten können.

Die von Ihnen ausgewählten Optionen wirken sich auf die Konfiguration einiger Telefonsystemfeatures aus. Weitere Informationen finden Sie weiter unten in diesem Artikel unter [ Überlegungen zur Konfiguration ](#configuration-considerations).

## <a name="phone-system-with-calling-plan"></a>Telefonsystem mit Anrufplan

Telefonsystem mit Anrufplan ist die All-in-the-Cloud-Sprachlösung von Microsoft für Teams-Benutzer. Diese Lösung ist die einfachste Option, die das Telefonsystem mit dem PSTN verbindet. Bei dieser Option fungiert Microsoft als Ihr PSTN-Netzbetreiber, wie im folgenden Diagramm dargestellt:

![In Abbildung 1 ist das Microsoft-Telefonsystems mit Anrufplan dargestellt.](media/voice-solutions-simple.png)

Wenn Sie die folgenden Punkte mit "Ja" beantworten können, ist "Telefonsystem mit Anrufplan" die richtige Lösung für Sie:

- PSTN-Anrufe sind in Ihrem Land oder Ihrer Region nicht verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht aufbewahren.
- Sie möchten von Microsoft verwalteten Zugriff auf das Telefonfestnetz nutzen.

Mit dieser Option geschieht Folgendes:

- Sie erhalten das Telefonsystem mit hinzugefügten Inlands- oder Auslandsanrufplänen, die Anrufe an Telefone auf der ganzen Welt ermöglichen (je nach lizenziertem Dienstgrad).

- Sie benötigen keine Bereitstellung oder Wartung einer lokalen Bereitstellung&mdash;, da der Anrufplan außerhalb von Microsoft 365 ausgeführt wird.

- Hinweis: Sie können einen unterstützten Session Border Controller (SBC) über Direct Routing für die Interoperabilität mit Nebenstellenanlagen von Drittanbietern, analogen Geräten und anderen Telefoniegeräten verbinden, die vom SBC unterstützt werden.

Diese Option erfordert eine ständige Verbindung mit Microsoft 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Anrufplan einrichten](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>Telefonsystem mit Telefonieanbieter

Wenn Ihr bestehender Netzbetreiber mit Operator Connect am Microsoft Operator Connect-Programm teilnimmt, kann er den Dienst für die Bereitstellung von PSTN-Anrufen an Teams verwalten. Ihr Netzbetreiber verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und der Verwaltung von Hardware sparen können.

Telefonieanbieter könnte die richtige Lösung für Ihr Unternehmen sein, wenn:

- Der Microsoft-Anrufplan an Ihrem geografischen Standort nicht verfügbar ist.
- Ihr bevorzugter Netzbetreiber Teilnehmer am Microsoft Telefonieanbieter-Programm ist.
- Sie einen neuen Netzbetreiber finden möchten, um Anrufe in Teams zu ermöglichen.

Informationen zu den Vorteilen und Anforderungen von Telefonieanbieter sowie eine Liste der an diesem Programm teilnehmenden Netzbetreiber finden Sie unter [Plan Telefonieanbieter](operator-connect-plan.md). Informationen zum Konfigurieren von Telefonieanbieter finden Sie unter [Telefonieanbieter konfigurieren](operator-connect-configure.md).

## <a name="phone-system-with-operator-connect-mobile"></a>Telefonsystem mit Telefonieanbieter mit Mobil

**Telefonieanbieter mit Mobil ist eine öffentliche Vorschauversion.**

Wenn Ihr vorhandener Netzbetreiber am Microsoft Telefonieanbieter mit Mobil-Programm teilnimmt, kann er den Dienst für die Bereitstellung von PSTN-Anrufen an Teams verwalten. Bei Telefonieanbieter mit Mobil ist die SIM-fähige Telefonnummer eines Benutzers auch die Microsoft Teams-Telefonnummer.  Benutzer können eine einzelne Telefonnummer in Microsoft Teams sowohl über ihren mobilen Dienst als auch über schreibtischleitungen verwenden.  

Sie können eine Kombination von Diensten in Betracht ziehen. Sie können z. B. Telefonieanbieter mit Mobil für Ihre Vertriebs- und Außendienstorganisationen auswählen, die mobilen Support benötigen, aber eine weitere Lösung für Ihre Organisation vor Ort, die auf Telefonapparaten basiert. 

Telefonieanbieter mit Mobil ist möglicherweise die richtige Lösung für Ihre Organisation, wenn:

- Sie möchten eine primäre unternehmenseigene, SIM-fähige Mobiltelefonnummer für Teams Phone als Lösung für einzelne Nummern verwenden.
- Ihr bevorzugter Betreiber ist ein Teilnehmer am Microsoft Telefonieanbieter mit Mobil-Programm.
- Sie möchten einen neuen Operator finden, um Anrufe in Teams zu ermöglichen.

Informationen zu den Vorteilen und Anforderungen von Telefonieanbieter mit Mobil sowie Links zu Netzbetreibern, die an diesem Programm teilnehmen, finden Sie unter [Plan Telefonieanbieter mit Mobil](operator-connect-mobile-plan.md). Informationen zum Konfigurieren von Telefonieanbieter mit Mobil finden [Sie unter Konfigurieren von Telefonieanbieter mit Mobil](operator-connect-mobile-configure.md).

## <a name="phone-system-with-direct-routing"></a>Direktes Routing für Telefonsysteme

Diese Option verbindet das Telefonsystem mithilfe von Direct Routing mit Ihrem Telefonnetzwerk, wie in der folgenden Abbildung gezeigt: 

![Abbildung 5 zeigt ein Telefonsystem mit Direct Routing.](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten können, ist "Telefonsystem mit Direct Routing" die richtige Lösung für Sie:

- Sie möchten Microsoft Teams mit "Telefonsystem" verwenden.
- Sie müssen bei Ihrem aktuellen Festnetzbetreiber bleiben.
- Sie möchten verschiedene Routing-Formen nutzen, einige Anrufe laufen über den Anrufplan und andere über Ihren Netzbetreiber.
- Sie müssen mit Nebenstellenanlagen von Drittanbietern und/oder Geräten wie Overhead-Pagern, analogen Geräten usw. zusammenarbeiten.

Mit dieser Option geschieht Folgendes:

- Sie verbinden Ihren eigenen unterstützten Session Border Controller (SBC) mit dem Telefonsystem, ohne dass zusätzliche lokale Software erforderlich ist.

- Sie können praktisch jeden Telefonanbieter mit Phone System verwenden.

- Sie können diese Option konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (fragen Sie, ob Ihr Netzbetreiber oder Partner diese Option bereitstellt).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten &mdash;wie einer Nebenstellenanlage eines Drittanbieters und analogen Geräten&mdash; und dem Telefonsystem konfigurieren.

Diese Option setzt Folgendes voraus:

- Ständige Verbindung mit Microsoft 365

- Bereitstellen und Verwalten eines unterstützten SBC

- Einen Vertrag mit einem externen Netzbetreiber
  (Außer wenn sie als Option bereitgestellt wird, um eine Verbindung mit Nebenstellenanlagen, Analoggeräten oder anderen Telefoniegeräten von Drittanbietern für Benutzer zu ermöglichen, die sich in einem Telefonsystem mit Anrufplänen befinden.)

Weitere Informationen zum direkten Routing finden Sie in den folgenden Artikeln:

- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwaltung von Voice-Routing-Richtlinien zur Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>Überlegungen zur Konfiguration

Die meisten Funktionen des Microsoft-Telefonsystems sind unabhängig von der gewählten Festnetzanbindungsoption identisch. Beispielsweise stehen Einstellungen für unbeantwortete Anrufe und Weiterleitung, Anrufweiterleitung, benutzerdefinierte Wartemusik, Anrufparken, gemeinsame Leitung und Sprach-Apps zur Verfügung. Eine vollständige Liste der Telefonsystemfunktionen finden Sie unter [Das bietet Ihnen das Telefonsystem](here-s-what-you-get-with-phone-system.md).

Es gibt jedoch einige Funktionsunterschiede, die sich auf die Konfiguration bestimmter Telefonsystemfunktionen auswirken. Direktes Routing erfordert beispielsweise zusätzliche Schritte zum Konfigurieren des Anrufroutings. Als weiteres Beispiel bietet Direct Routing Lbr (Location-Based-Routing). Mit LBR können Sie die Gebührenumgehung an bestimmten geografischen Standorten einschränken, an denen sie nicht zulässig ist. 

In der folgenden Tabelle werden die primären Konfigurationsunterschiede hervorgehoben. Die Abschnitte, die der Tabelle folgen, enthalten Links zu weiteren Informationen und Details.

| Option | Beschreibung | Telefonnummernverwaltung | Anrufweiterleitung | Verfügbarkeit von Notrufen |
| :------------| :-------| :-------| :-------| :-------| 
| Anrufpläne | -Microsoft fungiert als PSTN-Träger.<br>- Sie müssen keine SBCs kaufen oder verwalten.| Von Microsoft bezogen.| -Verwaltet von Microsoft. <br> -Admin konfiguriert Benutzerwählpläne für die Nummernübersetzung. | -Aktiviert von Microsoft. <br> -Admin registriert Adressen. <br> -Dynamische Anrufe werden unterstützt. |
| Telefonieanbieter | -Netzbetreiber verwaltet PSTN-Konnektivität und SBCs. <br> - Sie müssen keine SBCs kaufen oder verwalten. | -Erhalten durch den Netzbetreiber. <br> - Nummern, die mit Notrufadressen verbunden sind, die vom Netzbetreiber verwaltet werden. | -Vom Netzbetreiber verwaltet. <br>-Admin konfiguriert Benutzerwählpläne für die Nummernübersetzung. | -Aktiviert durch den Netzbetreiber. <br> -Admin registriert Adressen. <br> -Dynamische Anrufe werden unterstützt. |
| Telefonieanbieter mit Mobil | – Netzbetreiber verwaltet SIM-Enabled Mobiltelefonnummer, PSTN-Konnektivität und SBCs. <br> - Sie müssen keine SBCs kaufen oder verwalten. | -Erhalten durch den Netzbetreiber. <br> - Nummern, die Notfalladressen zugeordnet sind, die vom Netzbetreiber verwaltet werden. | -Vom Netzbetreiber verwaltet. <br> Admin konfiguriert Benutzerwählpläne für die Nummernübersetzung. |– Vom Netzbetreiber aktiviert. <br> - Admin registriert Adressen. <br> – Dynamische Anrufe werden unterstützt. <br> – Netzbetreiber unterstützt systemeigene Dialer-Notrufe. |
| Direct Routing | -Erfordert zertifizierten SBC, der von einem Drittanbieter erworben wurde.<br>-Verbinden Sie Ihren SBC mit dem Telefonsystem.<br> -Verwenden Sie Ihren bestehenden PSTN-Anbieter. | Über den Netzbetreiber bezogen. | -Erfordert zusätzliche Konfiguration durch den Administrator.<br>-Admin konfiguriert Amtswahlpläne für die Nummernübersetzung. <br>-LBR verfügbar, um die Gebührenumgehung einzuschränken. | -Erfordert zusätzliche Konfiguration durch den Administrator. <br>-Registrierte Adressen werden nicht unterstützt. <br>-Registrierte Adressen werden nicht unterstützt. |


### <a name="phone-number-management"></a>Telefonnummernverwaltung

Microsoft bietet zwei Arten von Telefonnummern: Abonnentennummern (Benutzernummern), die Benutzern in Ihrer Organisation zugewiesen werden können, und Dienstnummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind. Dienstnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.

Sie müssen Folgendes entscheiden:

- Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnenten oder Dienst) benötige ich?
- Wie übertrage ich vorhandene Telefonnummern zu Teams?

Wie Sie Telefonnummern erwerben und verwalten, hängt von Ihrer PSTN-Konnektivitätsoption ab.

- Informationen zum Verwalten von Telefonnummern für den Anrufplan finden [Sie unter "Verwalten von Telefonnummern für Anrufpläne"](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Informationen zum Verwalten von Telefonnummern mit Telefonieanbieter finden Sie unter [Telefonnummern mit Telefonieanbieter einrichten](operator-connect-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern mit Telefonieanbieter mit Mobil finden [Sie unter Einrichten von Telefonnummern mit Telefonieanbieter mit Mobil](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Informationen zum Verwalten von Telefonnummern für Direct Routing finden Sie unter [Konfigurieren der Telefonnummer und Aktivieren von Enterprise-VoIP](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).

### <a name="call-routing-and-dial-plans"></a>Anrufweiterleitung und Wählpläne

Wie Sie die Anrufweiterleitung konfigurieren, hängt von Ihrer PSTN-Konnektivitätsoption ab.  

- Bei Anrufplänen wird der Großteil der Anrufweiterleitung von der Microsoft-Anrufplaninfrastruktur abgewickelt. Sie konfigurieren Benutzerwählpläne zum Zwecke der Nummernübersetzung für die Anrufberechtigung und Anrufweiterleitung. Weitere Informationen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

- Für Operator Connect und Telefonieanbieter mit Mobil wird der Großteil des Anrufroutings vom Netzbetreiber verwaltet. Sie konfigurieren Benutzerwählpläne zum Zwecke der Nummernübersetzung für die Anrufberechtigung und Anrufweiterleitung. Weitere Informationen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

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

- Für den Anrufplan wird jeder Benutzer automatisch für Notrufe aktiviert. Der Benutzer muss über eine registrierte Notfalladresse verfügen, die der zugewiesenen Telefonnummer zugeordnet ist. Dynamische Notrufe (basierend auf dem Standort des Teams-Clients) werden unterstützt. Weitere Informationen finden Sie unter [Überlegungen zu Anrufplänen](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

- Bei Operator Connect wird jeder Benutzer automatisch für Notrufe aktiviert. Dem Benutzer muss eine registrierte Notfalladresse zugeordnet sein, die der zugewiesenen Telefonnummer zugeordnet ist. Dynamische Notrufe (basierend auf dem Standort des Teams-Clients) werden unterstützt. Weitere Informationen finden Sie unter [Überlegungen zu Operator Connect](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect). 

- Für Telefonieanbieter mit Mobil wird jeder Benutzer automatisch für Notrufe aktiviert. Notrufe werden automatisch an den Telefonieanbieter mit Mobil Netzbetreiber für eine bestimmte Nummer weitergeleitet. Dynamische Notrufe (basierend auf dem Standort des Teams-Clients) werden unterstützt. Weitere Informationen finden Sie [unter Überlegungen zu Telefonieanbieter mit Mobil](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect-mobile). 

- Für Direct Routing müssen Sie Notrufrichtlinien für Benutzer definieren, indem Sie eine Teams-Richtlinie für die Notrufweiterleitung (TeamsEmergencyCallRoutingPolicy) verwenden. Die Richtlinie definiert Notrufnummern und deren zugeordnetes Routingziel. Registrierte Notfallstandorte werden für Direct Routing-Benutzer nicht unterstützt. Für dynamische Notrufe ist eine zusätzliche Konfiguration für das Routing von Notrufen und möglicherweise für die Partnerkonnektivität erforderlich. Weitere Informationen finden Sie unter [Überlegungen zum Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).

#### <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zu Notrufkonzepten und -terminologie sowie zum Konfigurieren von Notrufen und dynamischen Notrufen finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Verwalten von Notruf-Richtlinien](manage-emergency-calling-policies.md)
- [Verwalten von Notruf-Routing-Richtlinien für Direct Routing](manage-emergency-call-routing-policies.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, Notrufe für seine Organisation implementiert hat.

### <a name="network-topology-for-voice-features"></a>Netzwerkeinstellungen für Cloud Voice-Features

Wenn Sie dynamische Notrufe oder Location-Based Routing für Direct Routing bereitstellen, müssen Sie Die Netzwerkeinstellungen für diese Features in Microsoft Teams konfigurieren. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkstandorte, Netzwerksubnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud Voice-Features in Microsoft Teams](manage-your-network-topology.md)
