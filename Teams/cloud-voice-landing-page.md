---
title: Planen Sie Ihre Sprachlösung in Microsoft Teams
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
description: Erfahren Sie mehr über Microsoft Teams Cloud-Sprachfeatures und die Bereitstellungsentscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 391b8e2f30aa5e64fcb4b9e418af49341c2b9042
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901932"
---
# <a name="plan-your-teams-voice-solution"></a>Planen Ihrer Teams-Sprachlösung 

Dieser Artikel hilft Ihnen bei der Entscheidung, welche Microsoft-Sprachlösung für Ihre Organisation die richtige ist. Nachdem Sie sich entschieden haben, enthält dieser Artikel eine Roadmap für Inhalte, mit deren Unterstützung Sie die ausgewählte Lösung implementieren können.

> [!NOTE]
> Anleitungen zum Planen einer Teams-Sprachlösung als Teil Ihres Gesamtplans für das Upgrade von Skype for Business Server auf Teams finden Sie unter Überlegungen zum PSTN für das Upgrade von der lokalen Skype for Business auf Teams [PSTN.](upgrade-to-teams-on-prem-pstn-considerations.md)

Die einfachste Lösung finden Sie, &mdash; wenn Telefonsystem Anrufplan erstellen möchten. Dies ist die All-in-the-Cloud-Lösung von Microsoft, die PBX-Funktionen (Private Branch Exchange) und Anrufe an das Public Switched Telephone Network (PSTN) bietet, wie in der folgenden Abbildung dargestellt. Mit dieser Lösung ist Microsoft Ihr PSTN-Netzbetreiber.

![Diagramm 1 zeigt Telefonsystem mit Anrufplan](media/voice-solutions-simple.png)

Wenn Sie mit Ja antworten, ist Telefonsystem Anrufplan die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht beibehalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Möglicherweise ist Ihre Situation jedoch komplexer. So könnten Sie beispielsweise Niederlassungen an Standorten haben, an denen kein Anrufplan verfügbar ist. Oder Sie benötigen eine Kombinationslösung, die eine komplexe, multinationale Bereitstellung mit unterschiedlichen Anforderungen für unterschiedliche geografische Standorte unterstützt. Microsoft unterstützt eine Kombination von Lösungen: 

- Telefonsystem mit Anrufplan
- Telefonsystem bei Ihrem eigenen Netzbetreiber mit Netzbetreiber Verbinden (derzeit nur in **der öffentlichen Vorschau verfügbar)**
- Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber mit Direct Routing
- Eine Kombinationslösung, die Telefonsystem Anrufplan, Telefonsystem mit Operator Verbinden und/oder Telefonsystem mit Direct-Routing verwendet


## <a name="what-do-you-need-to-read"></a>Was müssen Sie lesen?

**Erforderlich für alle.** Einige der Abschnitte in diesem Artikel betreffen alle Organisationen. So sollte sich beispielsweise jeder über die Informationen Telefonsystem und die Optionen für die Verbindung zum öffentlichen Telefonnetz (PSTN) verstehen. 


| Erforderlich für alle | Beschreibung |
| :------------|:-------|
| [**Telefonsystem**](#phone-system) | Die Microsoft-Technologie zum Aktivieren von Anrufsteuerung und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365 Mit Microsoft Teams. |
| [**PstN-Konnektivitätsoptionen (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Sie können zwischen der Verwendung von Microsoft als Netzbetreiber oder der Verbindung Ihres eigenen Telefonieanbieters mit Microsoft Teams über Direct Routing oder Operator Verbinden. In Kombination Telefonsystem Konnektivitätsoptionen für das Festnetz ermöglichen es Ihren Benutzern, weltweit Telefonanrufe zu telefonieren.|

**Je nach Ihren Anforderungen.** Einige der Abschnitte in diesem Artikel sind abhängig von Ihrer vorhandenen Bereitstellung und den anforderungen relevant. Beispielsweise ist Location-Based Routing nur für Direct Routing-Kunden an geografischen Standorten erforderlich, die keine gebührenpflichtige Umgehung zulassen.

Überlegen Sie, welche dieser zusätzlichen Konfigurationen Sie möglicherweise benötigen:

![Diagramm 2 zeigt zusätzliche Sprachkomponenten, z. B. Telefon-Nummern von Microsoft, Wählpläne und Anrufrouting und so weiter.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefon von Microsoft**](#phone-numbers-from-microsoft) | Hier erfahren Sie, wie Sie Telefonnummern von Microsoft erhalten und verwalten und wie Sie vorhandene Nummern an Microsoft übertragen. Lesen Sie dies, wenn Sie Telefonnummern für den Microsoft-Anrufplan erhalten, vorhandene Nummern übertragen, Servicenummern beziehen müssen und so weiter. |
| [**Wählpläne und Anrufrouting**](#dial-plans-and-call-routing) | Konfigurieren und Verwalten von Wählplänen, mit deren Hilfe gewählte Telefonnummern in ein alternatives Format (normalerweise E.164-Format) für die Anrufautorisierung und die Anrufrouting übersetzt werden. Lesen Sie dies, wenn Sie wissen müssen, was Wählpläne sind und ob Sie Wählpläne für Ihre Organisation angeben müssen.|
| [**Notrufe**](#emergency-calling) | Verwalten und Konfigurieren von Notrufen &mdash; je nach Ihrer PSTN-Konnektivitätsoption Lesen Sie diesen Abschnitt, wenn Sie einen Microsoft-Anrufplan oder Direct Routing verwenden und wissen möchten, wie Sie Notrufe für Ihre Organisation verwalten können. |
| [**Standortbasiertes Routing für direktes Routing**](#location-based-routing-for-direct-routing) |Informationen zur Verwendung Location-Based Routing (LBR) zum Einschränken der Microsoft Teams Umgehung für Benutzer anhand ihres geografischen Standorts. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direct-Routing an einem Ort verwendet, an dem keine gebührenpflichtige Umgehung zulässig ist.
| [**Netzwerktopologie für Cloud-Sprachfeatures**](#network-topology-for-voice-features) | Wenn Ihre Organisation Location-Based Routing (LBR) für Direct Routing oder dynamische Notrufe implementiert, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams. Lesen Sie diesen Abschnitt, wenn Sie LBR für Direct-Routing implementieren, oder wenn Sie dynamische Notrufe mit Anrufplan oder Direct Routing implementieren. |
| [**Migrieren Ihrer vorhandenen Sprachlösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie bei der Migration Ihrer Sprachlösung zu Ihren Sprachlösungen denken müssen, Teams.  Lesen Sie diesen Abschnitt, wenn Sie von einer vorhandenen Sprachlösung zu einem Teams. 



> [!Important]
> Dieser Artikel konzentriert sich auf Sprachlösungen mit Microsoft Teams. Auch wenn Lösungen mit Skype for Business Online weiterhin verfügbar sind (wie in [den Telefonielösungen](/SkypeForBusiness/hybrid/msft-telephony-solutions)von Microsoft beschrieben), ist es wichtig zu wissen, dass Skype for Business Online am 31. Juli 2021 eingestellt wird.  Nach diesem Datum kann auf Skype for Business Onlinedienst nicht mehr zugegriffen werden. Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung – unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online – &mdash; &mdash; nicht mehr unterstützt. In diesem Artikel werden die Teams und erläutert, wie Sie bei Bedarf Ihr lokales Telefonienetzwerk mithilfe von Direct Routing oder Operator Teams mit Verbinden.


## <a name="phone-system"></a>Telefonsystem

Telefonsystem microsoft-Technologie zum Aktivieren von Anrufsteuerungs- und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365- oder Office 365-Cloud mit Microsoft Teams.

Telefonsystem kann mit Teams oder Skype for Business-Clients und zertifizierten Geräten verwendet werden. Telefonsystem können Sie Ihr vorhandenes PBX-System durch eine Reihe von Funktionen ersetzen, die direkt von Ihrem Microsoft 365 oder ihrem Office 365. 

Anrufe zwischen Benutzern in Ihrer Organisation werden intern innerhalb Telefonsystem abgewickelt und niemals an das Public Switched Telephone Network (PSTN) umgestellt. Dies gilt für Anrufe zwischen Benutzern in Ihrer Organisation, die sich in unterschiedlichen geographischen Regionen befinden, wodurch Kosten für Ferngespräche für diese internen Anrufe entfallen.

In diesem Artikel werden die Telefonsystem wichtigsten Features und Funktionen sowie die Bereitstellungsentscheidungen beschrieben, die Sie berücksichtigen müssen:

- [Automatische Telefonzentralen und Anrufwarteschleifen](#auto-attendants-and-call-queues)
- [Cloudvoicemail](#cloud-voicemail)
- [Aufrufen der Identität](#calling-identity)

![Diagramm 3 zeigt, Telefon System automatische Telefonkonferenzen und Anrufabfragen, Cloud-Voicemail und Anrufidentität enthält.](media/phone-system-contains.png)

Informationen zu allen Features Telefonsystem und zum Einrichten von Telefonsystem finden Sie in den folgenden Artikeln:

- [Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)
- [Einrichten des Telefonsystems in Ihrer Organisation](setting-up-your-phone-system.md)<br>
  Beschreibt, wie Sie Lizenzen Telefonsystem und zuweisen, Telefonnummern verwalten und Guthaben für Kommunikationen für gebührenfreie Nummern einrichten. 

Informationen zum Verwalten unterstützter Geräte finden Sie unter [Verwalten von Geräten in Microsoft Teams](devices/device-management.md) und Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Automatische Telefonkonferenzen und Anrufwarteschleifen

Mit automatischen Telefonkonferenzen können Sie Menüoptionen einrichten, um Anrufe basierend auf der Anrufereingabe weiterzurouten. Anrufwarteschleifen sind Wartebereiche für Anrufer. Bei der gemeinsamen Verwendung können automatische Telefonkonferenzen und Anrufwarteschleifen Anrufer problemlos an die entsprechende Person oder Abteilung in Ihrer Organisation routen.

Informationen zu automatischen Telefonkonferenzen und Anrufwarteschleifen finden Sie in den folgenden Artikeln:

- [Planen der Teams von automatischen Telefonkonferenzen und Anrufwarteschleifen](plan-auto-attendant-call-queue.md)
- [Einrichten einer automatischen Attendant](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md) 
- [Contoso-Fallstudie: Automatische Telefonkonferenzen und Anrufwarteschleifen](voice-case-study-call-queues.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen Contoso automatische Telefonkonferenzen und Anrufwarteschleifen für die Sprachlösung implementiert.

### <a name="cloud-voicemail"></a>Cloudvoicemail

Cloud-Voicemail, unterstützt von Azure Voicemail-Diensten, Voicemailguthaben nur für Exchange Postfächer. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. 

Cloud-Voicemail umfasst die Voicemail-Transkription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Ihre geschäftlichen Anforderungen erfordern möglicherweise, dass Sie die Transkription für bestimmte Benutzer oder alle Benutzer in der Organisation deaktivieren.

Nur für Onlinebenutzer wird Cloud-Voicemail automatisch eingerichtet und für Benutzer bereitgestellt, nachdem ihnen eine Lizenz zugewiesen Telefonsystem wurde. Für Telefonsystem mit einem Exchange-Postfach müssen Sie zusätzliche Konfigurationsschritte ausführen. 

Weitere Informationen zu den Cloud-Voicemail und deren Konfiguration finden Sie in den folgenden Artikeln:

- [Einrichten von Cloudvoicemail](set-up-phone-system-voicemail.md)
- [Festlegen von Voicemailrichtlinien in Ihrer Organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Aufrufen der Identität

Standardmäßig wird für alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anrufidentität (Anrufer-ID) verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. Informationen zum Konfigurieren der Anrufer-ID oder zum Ändern oder Blockieren der Anrufer-ID finden Sie unter Festlegen der [Anrufer-ID für einen Benutzer.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Konnektivitätsoptionen für das Public Switched Telephone Network

Telefonsystem stellt umfassende PBX-Funktionen für Ihre Organisation bereit. Um Benutzern das Anrufen außerhalb Ihrer Organisation zu ermöglichen, müssen Sie Telefonsystem das Public Switched Telephone Network (PSTN) verbinden. Wenn Sie Telefonsystem PSTN verbinden möchten, können Sie eine der folgenden Optionen auswählen:

- [**Telefonsystem mit Anrufplan .**](#phone-system-with-calling-plan) Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Netzbetreiber.

- [**Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber,**](#phone-system-with-own-pstn-carrier-with-direct-routing) indem Sie Direct Routing verwenden, um Ihre lokale Umgebung mit ihrem Teams.

- [**Telefonsystem mit Ihrem eigenen NETZBETREIBER**](operator-connect-plan.md)mithilfe des Operator Verbinden , der derzeit nur in der **öffentlichen Vorschau zur Verfügung steht.**  Wenn Ihr Verbinden Teilnehmer am Microsoft Operator Verbinden-Programm ist, kann er den Dienst verwalten, um PSTN-Anrufe an Teams. Informationen zu den Vorteilen und Anforderungen von Operatoren Verbinden und eine Liste der am Programm teilnehmenden Operatoren finden Sie unter [Planoperator Verbinden.](operator-connect-plan.md)

Sie können auch eine Kombination von Optionen auswählen, die es Ihnen ermöglicht, eine Lösung für eine komplexe Umgebung zu entwerfen oder eine Mehrschrittmigration zu verwalten (weitere Informationen zur späteren Migration).

### <a name="phone-system-with-calling-plan"></a>Telefonsystem mit Anrufplan 

Wie weiter oben in diesem Artikel beschrieben, ist Telefonsystem Anrufplans die All-in-Cloud-Sprachlösung von Microsoft für Teams Benutzer. Dies ist die einfachste Option, mit der das Microsoft-Telefon-System mit dem öffentlichen Telefonnetz (PSTN) verbunden wird, um Anrufe an Festnetztelefone und Mobiltelefone weltweit zu ermöglichen. Mit dieser Option stellt Microsoft PBX-Funktionen (Private Branch Exchange) für Ihre Organisation bereit und fungiert als Ihr PSTN-Netzbetreiber, wie in der folgenden Abbildung dargestellt:

![Diagramm 4 zeigt Telefonsystem mit automatischen Telefonnetzen, Anrufwarteschleifen, Anrufer-ID und mehr sowie Microsoft als Netzbetreiber](media/voice-solution-microsoft-complete.png)

Wenn Sie mit Ja antworten, ist Telefonsystem Anrufplan die richtige Lösung für Sie:

- Anrufplan ist in Ihrer Region verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht beibehalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Mit dieser Option: 

- Sie erhalten Microsoft-Telefon-System mit zusätzlichen Inlands- oder Auslands anrufplänen, die Anrufe an Telefone auf der ganzen Welt ermöglichen (abhängig von der Art des lizenzierten Diensts).

- Sie benötigen keine Bereitstellung oder Wartung einer lokalen Bereitstellung, da der Anrufplan nicht mehr Microsoft 365 &mdash; oder Office 365.

- Hinweis: Bei Bedarf können Sie sich entscheiden, einen unterstützten Session Border Controller (SBC) über Direct Routing für die Interoperabilität mit Drittanbieter-PBXs, Analoggeräten und anderen von SBC unterstützten Telefoniegeräten von Drittanbietern zu verbinden.

Diese Option erfordert eine unterbrechungsfreie Verbindung mit Microsoft 365 oder Office 365.

Weitere Informationen zum Anrufplan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Einrichten eines Anrufplans](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Telefonsystem mit eigenem PstN-Netzbetreiber mit Direct Routing

Diese Option verbindet Microsoft-Telefon-System mithilfe von Direct Routing mit Ihrem Telefonienetzwerk, wie in der folgenden Abbildung dargestellt: 

![Diagramm 5 zeigt die Telefonsystem mit Direct Routing.](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten, Telefonsystem Direct-Routing die richtige Lösung für Sie:

- Sie möchten die Teams mit Telefonsystem.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber beibehalten.
- Sie möchten das Routing vermischen. Einige Anrufe gehen über den Anrufplan, einige über Ihren Netzbetreiber.
- Sie müssen mit PbXs und/oder Geräten von Drittanbietern (z. B. Overheadseiten, analoge Geräte und so weiter) zusammenarbeiten.

Mit dieser Option:

- Sie verbinden Ihre eigenen unterstützten SBC mit Microsoft-Telefon System, ohne dass zusätzliche lokale Software benötigt wird.

- Sie können praktisch jeden Telefonieanbieter mit Ihrem Microsoft-Telefon verwenden.

- Sie können diese Option konfigurieren und verwalten, oder sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (Fragen Sie, ob Ihr Netzbetreiber oder Partner diese Option bietet).

- Sie können die Interoperabilität zwischen Ihren Telefoniegeräten wie einer Drittanbieter-PBX und analogen Geräten und Microsoft-Telefon &mdash; &mdash; konfigurieren.


Für diese Option ist Folgendes erforderlich:

- Unterbrechungsfreie Verbindung mit Microsoft 365 oder Office 365.

- Bereitstellen und Verwalten eines unterstützten SBC

- Ein Vertrag mit einem Drittanbieter.
  (Es sei denn, die Bereitstellung als Option zum Bereitstellen einer Verbindung mit Drittanbieter-PBX, analogen Geräten oder anderen Telefoniegeräten für Benutzer, die mit Telefonsystem Anrufplan verbunden sind.)

Weitere Informationen zu Direct-Routing finden Sie in den folgenden Artikeln:

- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwalten von Voice Routing-Richtlinien für die Verwendung mit Direct Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Telefon von Microsoft

Microsoft verfügt über zwei Arten von Telefonnummern: Telefonnummern für Abonnenten (Benutzer),  die Benutzern in Ihrer Organisation zugewiesen werden können, und Servicenummern, die als gebührenpflichtige und gebührenfreie Servicenummern verfügbar sind.  Leistungsnummern haben eine höhere Kapazität für gleichzeitige Anrufe als Abonnentennummern und können Diensten wie Audiokonferenzen, automatischen Telefonkonferenzen oder Anrufwarteschleifen zugewiesen werden.

Sie müssen sich entscheiden:

- An welchen Benutzerstandorten benötigen Sie neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) brauche ich? 
- Wie portiert ich vorhandene Telefonnummern zu Teams?

Weitere Informationen zum Verwalten von Telefonnummern in Ihrer Organisation, einschließlich des Abrufens neuer Nummern oder übertragen von Ausgangsnummern, finden Sie in den folgenden Artikeln:

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Verschiedene Arten von Telefonnummern, die für Anrufplan verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md)
- [Übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Wählpläne und Anrufrouting

Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, mit der gewählte Telefonnummern in ein alternatives Format (normalerweise im E.164-Format) für die Anrufautorisierung und die Anrufrouting übersetzt werden.

Sie müssen sich für Folgendes entscheiden: 

- Benötigt meine Organisation einen angepassten Wählplan?
- Welche Benutzer benötigen einen angepassten Wählplan?
- Welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?

Weitere Informationen finden Sie in den folgenden Artikeln: 

- [Was sind Wählpläne?](what-are-dial-plans.md)
- [Planen von Mandantenwählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Notrufe

Die Konfiguration von Notrufen unterscheidet sich je nach ihrer PSTN-Konnektivitätsoption: Microsoft-Anrufplan oder Direct-Routing. Dynamische Notrufe für Microsoft Calling Plan und Telefonsystem Direct Routing bieten die Möglichkeit, Notrufe zu konfigurieren und zu weiterleiten sowie Sicherheitsmitarbeiter basierend auf dem aktuellen Standort des Teams-Clients zu benachrichtigen. Weitere Informationen zu Konzepten und Terminologie für Notrufe sowie zum Konfigurieren dynamischer Notrufe finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen Contoso Notrufe für ihre Organisation implementiert hat.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based Routing für Direct Routing

In einigen Ländern und Regionen ist es ungesetzlich, den Anbieter des öffentlichen Telefonnetzwerks (PSTN) zu umgehen, um die Kosten für Anrufe im Ferngespräch zu senken. Location-Based Routing für Direct-Routing ermöglicht Es Ihnen, die gebührenpflichtige Umgehung für Microsoft Teams basierend auf ihrem geografischen Standort einzuschränken. Weitere Informationen zum Planen und Konfigurieren von Location-Based Routing (LBR) finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktives multinationales Unternehmen Contoso das Routing Location-Based Organisation implementiert.

## <a name="network-topology-for-voice-features"></a>Netzwerktopologie für Sprachfeatures

Wenn Sie dynamische Notrufe oder Location-Based-Routing für Direct-Routing bereitstellen, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams. Informationen zum Konfigurieren von Netzwerkeinstellungen für Netzwerkregionen, Netzwerkstandorte, Netzwerk-Subnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Sie Ihre Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Sie Ihre vorhandene Sprachlösung zu Teams

Für eine Organisation, die auf Teams aktualisiert, ist das ultimative Ziel, alle Benutzer in den TeamsOnly-Modus zu verschieben. Die Telefonsystem mit Teams wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet. Wenn Sie grundlegende Informationen zum Upgrade auf eine Teams benötigen, beginnen Sie hier:

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Info zum Upgrade-Framework](upgrade-framework.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md)

Bei der Migration Ihrer Sprachlösung gibt es vier mögliche Anrufszenarien beim Wechsel in den TeamsOnly-Modus:

- [**Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Bei einem Upgrade verfügen diese Benutzer weiterhin über einen Microsoft-Anrufplan.

- Ein Benutzer in Skype for Business Online mit lokalen **[Sprachfunktionen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) über** eine lokale Skype for Business oder Cloud Connector Edition. Das Upgrade des Benutzers auf Teams die Migration des Benutzers zu Direct-Routing muss koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionen verfügt.

- Ein Benutzer in Skype for Business lokalen Netzwerk mit Enterprise-VoIP, der zu online gehen und die lokale **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)PSTN-Anbindung wiederherstellen wird.** Die Migration dieses Benutzers zu Teams erfordert das Verschieben des lokalen Skype for Business-Kontos des Benutzers in die Cloud und die Koordinierung dieses Wechsels mit der Migration des Benutzers zu Direct Routing. 

- **[Ein Benutzer in Skype for Business mit dem](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)Enterprise-VoIP,** der zu online und einen Microsoft Calling Plan verwendet.  Die Migration dieses Benutzers zu Teams setzt voraus, dass das lokale Skype for Business-Konto des Benutzers in die Cloud migriert und der Wechsel mit A) der Portierung der Telefonnummer des Benutzers zu einem Microsoft-Anrufplan oder B) die Zuweisung einer neuen Abonnentennummer aus verfügbaren Regionen koordiniert wird.

Weitere Informationen zum Implementieren der Sprachmigration für jedes dieser Szenarien, einschließlich Informationen dazu, wann Sie Hybridkonnektivität einrichten müssen und wie Sie Benutzer mit lokalen Sprachfunktionen zu Direct Routing migrieren, finden Sie in den folgenden &mdash; &mdash; Artikeln:

- [Überlegungen zum PSTN beim Upgrade auf Teams – für IT-Administratoren](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Fallstudie zur Contoso-Sprachmigration](voice-case-study-overview.md)<br>
  In der Fallstudie wird beschrieben, wie ein fiktives multinationales Unternehmen Contoso eine Teams-Sprachlösung für ihre Organisation implementiert hat. Sie enthält die folgenden Artikel:

  - [Teams Upgradeplans](voice-case-study-migration-plan.md)
  - [Telefonsystem und PSTN-Konnektivitätsoptionen](voice-case-study-phone-system.md)
  - [Implementierung des standortbasierten Routings](voice-case-study-location-based-routing.md)
  - [Notrufe](voice-case-study-emergency-calling.md)
  - [Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)
  - [Audiokonferenzen](voice-case-study-audio-conferencing.md)
