---
title: Planen Ihrer Sprachlösung in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
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
description: Erfahren Sie mehr über die Microsoft Teams-Cloud-Sprachfeatures und die Bereitstellungsentscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d77e0b1ec6277bfeffd85d6657d14fe810aae96
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102571"
---
# <a name="plan-your-teams-voice-solution"></a>Planen Ihrer Teams-Sprachlösung 

In diesem Artikel können Sie entscheiden, welche Microsoft-Sprachlösung für Ihre Organisation richtig ist. Nachdem Sie sich entschieden haben, enthält der Artikel eine Roadmap für Inhalte, mit der Sie ihre ausgewählte Lösung implementieren können.

> [!NOTE]
> Anleitungen zum Planen einer Teams-Sprachlösung als Teil Ihres gesamtplans für ein Upgrade von Skype for Business Server auf Teams finden Sie unter PstN-Überlegungen zum Upgrade von Skype for Business lokal auf [Teams.](upgrade-to-teams-on-prem-pstn-considerations.md)

Möglicherweise möchten Sie die einfachste Lösung &mdash; Telefonsystem mit Anrufplan. Dies ist die all-in-cloud-Lösung von Microsoft, die Funktionen von Private Branch Exchange (PBX) und Anrufe an das Public Switched Telephone Network (PSTN) bietet, wie in der folgenden Abbildung dargestellt. Mit dieser Lösung ist Microsoft Ihr PSTN-Netzbetreiber.

![Abbildung 1: Telefonsystem mit Anrufplan](media/voice-solutions-simple.png)

Wenn Sie auf Folgendes mit Ja antworten, ist Telefonsystem mit Anrufplan die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht behalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Möglicherweise ist Ihre Situation jedoch komplexer. Sie können beispielsweise Niederlassungen an Orten haben, an denen kein Anrufplan verfügbar ist. Oder Sie benötigen eine Kombinationslösung, die eine komplexe, multinationale Bereitstellung mit unterschiedlichen Anforderungen für unterschiedliche geografische Standorte unterstützt. Microsoft unterstützt eine Kombination von Lösungen: 

- Telefonsystem mit Anrufplan
- Telefonsystem mit ihrem eigenen PSTN-Netzbetreiber mit Direct Routing
- Eine Kombinationslösung, die sowohl Telefonsystem mit Anrufplan als auch Telefonsystem mit Direct Routing verwendet

## <a name="what-do-you-need-to-read"></a>Was müssen Sie lesen?

**Erforderlich für alle.** Einige der Abschnitte in diesem Artikel betreffen alle Organisationen. So sollte beispielsweise jeder mehr über Telefonsystem lesen und die Optionen für die Verbindung mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) kennen. 


| Erforderlich für alle | Beschreibung |
| :------------|:-------|
| [**Telefonsystem**](#phone-system) | Die Technologie von Microsoft zum Aktivieren von Anrufsteuerung und PbX-Funktionen (Private Branch Exchange) in der Microsoft 365-Cloud mit Microsoft Teams. |
| [**Public Switched Telephone Network (PSTN)-Konnektivitätsoptionen**](#public-switched-telephone-network-connectivity-options) | Sie haben die Wahl zwischen der Verwendung von Microsoft als Telefonieanbieter oder der Verbindung Ihres eigenen Telefonanbieters mit Microsoft Teams mithilfe von Direct Routing. In Kombination mit dem Telefonsystem ermöglichen die PstN-Konnektivitätsoptionen Ihren Benutzern das Telefonieren auf der ganzen Welt.|

**Je nach Ihren Anforderungen.** Einige der Abschnitte in diesem Artikel sind je nach ihrer vorhandenen Bereitstellung und den Anforderungen relevant. Beispielsweise ist Location-Based Routing nur für Direct Routing-Kunden an geografischen Standorten erforderlich, die keine gebührenpflichtige Umgehung zulassen.

Überlegen Sie, welche dieser zusätzlichen Konfigurationen Sie möglicherweise benötigen:

![Diagramm 2 zeigt zusätzliche Sprachkomponenten, z. B. Telefonnummern von Microsoft, Wählpläne und Anrufrouting und so weiter.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefonnummern von Microsoft**](#phone-numbers-from-microsoft) | So erhalten und verwalten Sie Telefonnummern von Microsoft, und wie Sie vorhandene Nummern an Microsoft übertragen. Lesen Sie dies, wenn Sie Telefonnummern für den Microsoft-Anrufplan abrufen, vorhandene Nummern übertragen, Servicenummern abrufen und so weiter. |
| [**Wählpläne und Anrufrouting**](#dial-plans-and-call-routing) | Konfigurieren und Verwalten von Wählplänen, die wählte Telefonnummern in ein alternatives Format (normalerweise E.164-Format) für die Anrufautorisierung und Anrufrouting übersetzen. Lesen Sie dies, wenn Sie wissen müssen, was Wählpläne sind und ob Sie Wählpläne für Ihre Organisation angeben müssen.|
| [**Notrufe**](#emergency-calling) | Verwalten und Konfigurieren von Notrufen &mdash; je nach Ihrer PstN-Konnektivitätsoption. Lesen Sie diesen Abschnitt, wenn Sie Microsoft Calling Plan oder Direct Routing verwenden und verstehen müssen, wie Sie Notrufe für Ihre Organisation verwalten. |
| [**Standortbasiertes Routing für direktes Routing**](#location-based-routing-for-direct-routing) |So wird's Location-Based (LBR) zum Einschränken der Umgehung der Gebühren für Microsoft Teams-Benutzer basierend auf ihrem geografischen Standort verwendet. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direct Routing an einem Ort verwendet, an dem keine gebührenpflichtige Umgehung zulässig ist.
| [**Netzwerktopologie für Cloud-Sprachfeatures**](#network-topology-for-voice-features) | Wenn Ihre Organisation Location-Based Routing (LBR) für Direct Routing oder dynamische Notrufe bereitstellen, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Lesen Sie diesen Abschnitt, wenn Sie LBR für Direct Routing implementieren oder wenn Sie dynamische Notrufe mit Anrufplan oder Direct Routing implementieren. |
| [**Migrieren Ihrer vorhandenen Sprachlösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie bei der Migration Ihrer Sprachlösung zu Teams überlegen müssen.  Lesen Sie diesen Abschnitt, wenn Sie von einer vorhandenen Sprachlösung zu Teams migrieren. 



> [!Important]
> Dieser Artikel befasst sich mit Sprachlösungen mit Microsoft Teams. Obwohl Lösungen mit Skype for Business Online [](/SkypeForBusiness/hybrid/msft-telephony-solutions)weiterhin verfügbar sind (wie in Microsoft-Telefonielösungen beschrieben), ist es wichtig zu verstehen, dass Skype for Business Online am 31. Juli 2021 eingestellt wird.  Nach diesem Datum kann auf den Skype for Business Online-Dienst nicht mehr zugegriffen werden. Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung, ob über Skype for Business Server oder Cloud Connector Edition und &mdash; &mdash; Skype for Business Online, nicht mehr unterstützt. In diesem Artikel werden Die Sprachlösungen von Teams und erläutert, wie Sie Ihr lokales Telefonienetzwerk bei Bedarf mithilfe von Direct Routing mit Teams verbinden können.


## <a name="phone-system"></a>Telefonsystem

Telefonsystem ist die Technologie von Microsoft zum Aktivieren von Anrufsteuerung und PbX-Funktionen (Private Branch Exchange) in der Microsoft 365- oder Office 365-Cloud mit Microsoft Teams.

Telefonsystem funktioniert mit Teams- oder Skype for Business-Clients und zertifizierten Geräten. Mit Telefonsystem können Sie Ihr vorhandenes PBX-System durch eine Reihe von Features ersetzen, die direkt von Microsoft 365 oder Office 365 geliefert werden. 

Anrufe zwischen Benutzern in Ihrer Organisation werden intern innerhalb des Telefonsystems behandelt und gehen nie zum öffentlichen Telefonnetz (PstN). Dies gilt für Anrufe zwischen Benutzern in Ihrer Organisation, die sich in unterschiedlichen geographischen Regionen befinden, wodurch Kosten für Ferngespräche für diese internen Anrufe entfallen.

In diesem Artikel werden die folgenden Wichtigen Features und Funktionen des Telefonsystems sowie die Bereitstellungsentscheidungen beschrieben, die Sie berücksichtigen müssen:

- [Automatische Telefonzentralen und Anrufwarteschleifen](#auto-attendants-and-call-queues)
- [Cloudvoicemail](#cloud-voicemail)
- [Anrufidentität](#calling-identity)

![Abbildung 3 zeigt, dass das Telefonsystem automatische Telefonkonferenzen und Anrufabfragen, Cloud voicemail und Anrufidentität enthält](media/phone-system-contains.png)

Informationen zu allen Telefonsystemfunktionen und zum Einrichten von Telefonsystem finden Sie in den folgenden Artikeln:

- [Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)
- [Einrichten des Telefonsystems in Ihrer Organisation](setting-up-your-phone-system.md)<br>
  Beschreibt, wie Sie Lizenzen für das Telefonsystem kaufen und zuweisen, Telefonnummern verwalten und Guthaben für die Kommunikation für gebührenfreie Nummern einrichten. 

Informationen zum Verwalten unterstützter Geräte finden Sie unter [Verwalten Ihrer Geräte in Microsoft Teams](devices/device-management.md) und Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Automatische Telefonwarteschlangen und Anrufwarteschlangen

Mit automatischen Telefonkonferenzen können Sie Menüoptionen einrichten, um Anrufe basierend auf der Anrufereingabe weiterzurouten. Anrufwarteschlangen sind Wartebereiche für Anrufer. Wenn sie zusammen verwendet werden, können automatische Telefonanrufe und Anrufwarteschlangen Anrufer ganz einfach an die entsprechende Person oder Abteilung in Ihrer Organisation weiterzusenden.

Informationen zu automatischen Telefonkonferenzen und Anrufwarteschlangen finden Sie in den folgenden Artikeln:

- [Planen von automatischen Telefonkonferenzen und Anrufwarteschleifen für Teams](plan-auto-attendant-call-queue.md)
- [Einrichten einer automatischen Attendant](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md) 
- [Contoso-Fallstudie: Automatische Telefonwarteschlangen und Anrufwarteschlangen](voice-case-study-call-queues.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, automatische Telefonkonferenzen und Anrufwarteschlangen für seine Sprachlösung implementiert hat.

### <a name="cloud-voicemail"></a>Cloudvoicemail

Cloud Voicemail, die von Azure Voicemail-Diensten unterstützt wird, unterstützt nur Voicemaileinlagen in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. 

Cloud-Voicemail umfasst die Voicemail-Transkription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Ihre geschäftlichen Anforderungen erfordern möglicherweise, dass Sie die Voicemail-Transkription für bestimmte Benutzer oder alle Benutzer in der gesamten Organisation deaktivieren.

Nur für Onlinebenutzer wird Cloud Voicemail automatisch eingerichtet und für Benutzer bereitgestellt, nachdem ihnen eine Lizenz für das Telefonsystem zugewiesen wurde. Für Telefonsystembenutzer mit einem Exchange-Postfach müssen Sie zusätzliche Konfigurationsschritte ausführen. 

Weitere Informationen zu Cloud Voicemail und deren Konfiguration finden Sie in den folgenden Artikeln:

- [Einrichten von Cloudvoicemail](set-up-phone-system-voicemail.md)
- [Festlegen von Voicemailrichtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Anrufidentität

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anrufidentität (Anrufer-ID). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. Informationen zum Konfigurieren der Anrufer-ID oder zum Ändern oder Blockieren der Anrufer-ID finden Sie unter Festlegen der [Anrufer-ID für einen Benutzer.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Konnektivitätsoptionen für das öffentliche Telefonnetz

Telefonsystem stellt vollständige PBX-Funktionen für Ihre Organisation bereit. Damit Benutzer jedoch Anrufe außerhalb Ihrer Organisation unternehmen können, müssen Sie das Telefonsystem mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) verbinden. Um das Telefonsystem mit dem PSTN zu verbinden, können Sie eine der folgenden Optionen auswählen:

- [**Telefonsystem mit Anrufplan**](#phone-system-with-calling-plan). Eine all-in-the-Cloud-Lösung mit Microsoft als PstN-Netzbetreiber.

- [**Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber**](#phone-system-with-own-pstn-carrier-with-direct-routing) mithilfe von Direct Routing, um Ihre lokale Umgebung mit Teams zu verbinden.

Sie können auch eine Kombination von Optionen auswählen, mit der Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine mehrstufige Migration verwalten können (weitere Informationen zur Migration später).

### <a name="phone-system-with-calling-plan"></a>Telefonsystem mit Anrufplan 

Wie weiter oben in diesem Artikel beschrieben, ist Telefonsystem mit Anrufplan die all-in-cloud-Sprachlösung von Microsoft für Teams-Benutzer. Dies ist die einfachste Option, die Microsoft Phone System mit dem öffentlichen Telefonnetz (PstN) verbindet, um Anrufe an Festnetz- und Mobiltelefone auf der ganzen Welt zu ermöglichen. Mit dieser Option stellt Microsoft Die Funktionalität von Private Branch Exchange (PBX) für Ihre Organisation bereit und fungiert als Ihr PSTN-Netzbetreiber, wie in der folgenden Abbildung dargestellt:

![Abbildung 4: Telefonsystem mit automatischen Telefontelefonen, Anrufwarteschlangen, Anrufer-ID und mehr und Microsoft als NETZBETREIBER](media/voice-solution-microsoft-complete.png)

Wenn Sie auf Folgendes mit Ja antworten, ist Telefonsystem mit Anrufplan die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht behalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Mit dieser Option: 

- Sie erhalten Microsoft Phone System mit hinzugefügten nationalen oder internationalen Anrufplänen, die Anrufe an Telefone auf der ganzen Welt ermöglichen (je nach lizenzierter Dienststufe).

- Sie benötigen keine Bereitstellung oder Wartung einer lokalen Bereitstellung, da der Anrufplan von &mdash; Microsoft 365 oder Office 365 aus funktioniert.

- Hinweis: Bei Bedarf können Sie einen unterstützten Session Border Controller (SBC) über Direct Routing verbinden, um die Interoperabilität mit PbXs, analogen Geräten und anderen von SBC unterstützten Telefoniegeräten von Drittanbietern zu gewährleisten.

Diese Option erfordert eine unterbrechungsfreie Verbindung mit Microsoft 365 oder Office 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Einrichten eines Anrufplans](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Telefonsystem mit eigenem PSTN-Netzbetreiber mit Direct Routing

Diese Option stellt eine Verbindung zwischen Microsoft Phone System und Ihrem Telefonienetzwerk mithilfe von Direct Routing dar, wie in der folgenden Abbildung dargestellt: 

![Diagramm 5 zeigt Telefonsystem mit Direct Routing](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit Ja beantworten, ist Telefonsystem mit Direct Routing die richtige Lösung für Sie:

- Sie möchten Teams mit Telefonsystem verwenden.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber beibehalten.
- Sie möchten das Routing kombinieren, und einige Anrufe werden über den Anrufplan, einige über Ihren Netzbetreiber, verwendet.
- Sie müssen mit PbXs und/oder Geräten von Drittanbietern wie Overhead-Pagern, analogen Geräten und so weiter zusammenarbeiten.

Mit dieser Option:

- Sie verbinden Ihren eigenen unterstützten SBC mit Microsoft Phone System, ohne dass zusätzliche lokale Software benötigt wird.

- Sie können praktisch jeden Telefonanbieter mit Microsoft Phone System verwenden.

- Sie können diese Option konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (fragen Sie, ob Ihr Netzbetreiber oder Partner diese Option bietet).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten konfigurieren, z. B. einer Telefonanlage von Drittanbietern und analogen Geräten &mdash; und Microsoft Phone &mdash; System.


Diese Option erfordert Folgendes:

- Unterbrechungsfreie Verbindung mit Microsoft 365 oder Office 365.

- Bereitstellen und Verwalten eines unterstützten SBC.

- Ein Vertrag mit einem Drittanbieteranbieter.
  (Es sei denn, die Bereitstellung als Option zum Bereitstellen einer Verbindung mit PbX, analogen Geräten oder anderen Telefoniegeräten von Drittanbietern für Benutzer, die sich im Telefonsystem mit Anrufplan befinden.)

Weitere Informationen zu Direct Routing finden Sie in den folgenden Artikeln:

- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwalten von Sprachroutingrichtlinien für die Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Telefonnummern von Microsoft

Microsoft verfügt über zwei Arten von Telefonnummern: Abonnentennummern (Benutzernummern), die  Benutzern in Ihrer Organisation zugewiesen werden können, und Dienstnummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind.  Servicenummern haben eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonkonferenzen oder Anrufwarteschlangen zugewiesen werden.

Sie müssen entscheiden:

- Welche Benutzerstandorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) brauche ich? 
- Wie portiert ich vorhandene Telefonnummern zu Teams?

Weitere Informationen zum Verwalten von Telefonnummern in Ihrer Organisation, einschließlich abrufen neuer Nummern oder Übertragen von Ausgangsnummern, finden Sie in den folgenden Artikeln:

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Unterschiedliche Arten von Telefonnummern, die für den Anrufplan verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md)
- [Übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Wählpläne und Anrufrouting

Ein Wählplan ist eine Reihe von Normalisierungsregeln, die wählte Telefonnummern in ein alternatives Format (normalerweise im E.164-Format) für die Anrufautorisierung und Anrufrouting übersetzen.

Sie müssen Folgendes entscheiden: 

- Benötigt meine Organisation einen angepassten Wählplan?
- Welche Benutzer benötigen einen angepassten Wählplan?
- Welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?

Weitere Informationen finden Sie in den folgenden Artikeln: 

- [Was sind Wählpläne?](what-are-dial-plans.md)
- [Planen von Wählplänen für Mandanten](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Notrufe

Wie Sie Notrufe konfigurieren, hängt von Ihrer PstN-Konnektivitätsoption ab: Microsoft Calling Plan oder Direct Routing. Dynamische Notfallanrufe für Den Microsoft Calling Plan und Das direkte Routing des Telefonsystems bieten die Möglichkeit zum Konfigurieren und Weiterleiten von Notrufen und zum Benachrichtigen von Sicherheitsmitarbeitern basierend auf dem aktuellen Standort des Teams-Clients. Weitere Informationen zu Konzepten und Terminologie von Notrufen sowie zum Konfigurieren dynamischer Notrufe finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen, Contoso, Notrufe für ihre Organisation implementiert hat.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based Routing für Direct Routing

In einigen Ländern und Regionen ist es illegal, den Anbieter des öffentlichen Telefonnetzes (Public Switched Telephone Network, PSTN) zu umgehen, um die Kosten für Ferngespräche zu senken. Location-Based Routing für Direct Routing ermöglicht es Ihnen, die Umgehung der Gebühren für Microsoft Teams-Benutzer basierend auf ihrem geografischen Standort einzuschränken. Weitere Informationen zum Planen und Konfigurieren von Location-Based Routing (LBR) finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen namens Contoso Location-Based Routing für ihre Organisation implementiert.

## <a name="network-topology-for-voice-features"></a>Netzwerktopologie für Sprachfeatures

Wenn Sie dynamische Notrufe bereitstellen oder Location-Based Routing für Direct Routing verwenden, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkwebsites, Netzwerksubnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Ihrer vorhandenen Sprachlösung zu Teams

Für eine Organisation, die ein Upgrade auf Teams vor sich hat, besteht das ultimative Ziel in der Verzug aller Benutzer in den TeamsOnly-Modus. Die Verwendung von Telefonsystem mit Teams wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet. Wenn Sie grundlegende Informationen zum Upgrade auf Teams benötigen, beginnen Sie hier:

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Info zum Upgrade-Framework](upgrade-framework.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md)

Beim Migrieren Ihrer Sprachlösung gibt es vier mögliche Anrufszenarien beim Wechsel in den TeamsOnly-Modus:

- [**Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Nach dem Upgrade hat dieser Benutzer weiterhin einen Microsoft-Anrufplan.

- **[Ein Benutzer in Skype for Business Online mit lokalen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** Sprachfunktionen über Skype for Business lokal oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers zu Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP , der auf online umgeschaltet wird und die lokale **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)PSTN-Konnektivität behält.** Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und dieser Wechsel mit der Migration des Benutzers zu Direct Routing koordiniert wird. 

- Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP , der ins Internet umgeschaltet wird und einen **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)Microsoft-Anrufplan verwendet.**  Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud umgeschaltet und der Wechsel mit A) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B) das Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.

Weitere Informationen zum Implementieren der Sprachmigration für jedes dieser Szenarien, einschließlich Informationen zum Einrichten einer Hybridkonnektivität und zum Migrieren von Benutzern mit lokalen Sprachfunktionen zu Direct Routing, finden Sie in den folgenden &mdash; &mdash; Artikeln:

- [Überlegungen zum PSTN beim Upgrade auf Teams – für IT-Administratoren](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Fallstudie zur Contoso-Sprachmigration](voice-case-study-overview.md)<br>
  In der Fallstudie wird beschrieben, wie ein fiktives multinationales Unternehmen namens Contoso eine Teams-Sprachlösung für ihre Organisation implementiert hat. Sie enthält die folgenden Artikel:

  - [Upgradeplan für Teams](voice-case-study-migration-plan.md)
  - [Optionen für Telefonsystem- und PSTN-Konnektivität](voice-case-study-phone-system.md)
  - [Standortbasierte Routingimplementierung](voice-case-study-location-based-routing.md)
  - [Notrufe](voice-case-study-emergency-calling.md)
  - [Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)
  - [Audiokonferenzen](voice-case-study-audio-conferencing.md)