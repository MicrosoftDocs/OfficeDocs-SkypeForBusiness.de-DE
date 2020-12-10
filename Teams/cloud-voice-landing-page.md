---
title: Stimme in Microsoft Teams
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
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Weitere Informationen zu den Microsoft Teams Cloud-Sprachfeatures und den Bereitstellungsentscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c392e9a1e2944c573ddfa63da3aa27f56b2380d7
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611719"
---
# <a name="plan-your-teams-voice-solution"></a>Planen der VoIP-Lösung für Teams 

Dieser Artikel hilft Ihnen bei der Entscheidung, welche Microsoft Voice-Lösung für Ihre Organisation richtig ist. Nachdem Sie sich entschieden haben, finden Sie in dem Artikel eine Übersicht über die Inhalte, mit denen Sie die von Ihnen gewählte Lösung implementieren können. 

Vielleicht möchten Sie das einfachste Lösung &mdash; Telefon System mit Anrufplan. Hierbei handelt es sich um die Komplettlösung von Microsoft, die eine PBX-Funktionalität (Private Branch Exchange) und Anrufe an das öffentlich geschaltete Telefonnetz (PSTN) bereitstellt, wie in der nachstehenden Abbildung zu sehen ist. Mit dieser Lösung ist Microsoft Ihr PSTN-Netzbetreiber.

![Diagramm 1 zeigt das Telefon System mit Anrufplan](media/voice-solutions-simple.png)

Wenn Sie mit "Ja" zur folgenden Frage Antworten, ist das Telefon System mit Anrufplan die richtige Lösung für Sie:

- Der Anrufplan steht in Ihrer Region zur Verfügung.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht behalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Allerdings kann Ihre Situation komplexer sein. So können Sie beispielsweise Niederlassungen an Orten haben, an denen der Anrufplan nicht verfügbar ist. Oder Sie benötigen eine Kombinationslösung, die eine komplexe, multinationale Bereitstellung unterstützt, mit unterschiedlichen Anforderungen für verschiedene geografische Standorte. Microsoft unterstützt eine Kombination von Lösungen: 

- Telefon System mit Anrufplan
- Telefon System mit eigenem PSTN-Netzbetreiber mit direktem Routing
- Eine Kombinationslösung, die sowohl das Telefonsystem mit Anrufplan als auch das Telefonsystem mit direktem Routing verwendet

## <a name="what-do-you-need-to-read"></a>Was müssen Sie lesen?

**Für alle erforderlich.** Einige Abschnitte in diesem Artikel beziehen sich auf alle Organisationen. So sollte beispielsweise jeder über das Telefon System lesen und die Optionen für die Verbindung mit dem öffentlichen Telefonnetz (PSTN) kennen. 


| Für alle erforderlich | Beschreibung |
| :------------|:-------|
| [**Telefonsystem**](#phone-system) | Die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Microsoft 365-Cloud mit Microsoft Teams. |
| [**PSTN-Verbindungsoptionen (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Eine Wahl zwischen der Verwendung von Microsoft als Telefonnetzbetreiber oder dem Verbinden Ihres eigenen Telefonnetz Betreibers mit Microsoft Teams mithilfe der direkten Weiterleitung. In Kombination mit dem Telefon System ermöglichen PSTN-Verbindungsoptionen Ihren Benutzern, überall auf der Welt Telefonanrufe zu tätigen.|

**Je nach Ihren Anforderungen.** Einige Abschnitte in diesem Artikel sind je nach Ihrer vorhandenen Bereitstellung und Ihren Anforderungen relevant. Beispielsweise ist Location-Based Routing nur für direktes Routing von Kunden an geografischen Standorten erforderlich, die keine Maut Umgehung zulassen.

Bedenken Sie, welche dieser zusätzlichen Konfigurationen Sie möglicherweise benötigen:

![Diagramm 2 zeigt zusätzliche Sprachkomponenten wie Telefonnummern von Microsoft, Wählpläne und Anrufweiterleitung usw.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefonnummern von Microsoft**](#phone-numbers-from-microsoft) | Informationen zum Abrufen und Verwalten von Telefonnummern von Microsoft sowie zum übertragen vorhandener Nummern an Microsoft. Lesen Sie diese Informationen, wenn Sie Telefonnummern für den Microsoft-Anrufplan anfordern, vorhandene Nummern übertragen, Dienstnummern abrufen usw. benötigen. |
| [**Wählpläne und Anrufweiterleitung**](#dial-plans-and-call-routing) | Konfigurieren und Verwalten von Wählplänen, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen. Lesen Sie diese Informationen, wenn Sie wissen möchten, was Wählpläne sind und ob Sie Wählpläne für Ihre Organisation angeben müssen.|
| [**Notrufe**](#emergency-calling) | So verwalten und konfigurieren Sie Notrufe in &mdash; Abhängigkeit von ihrer PSTN-Verbindungsoption. Lesen Sie diesen Abschnitt, wenn Sie Microsoft Calling Plan oder Direct Routing verwenden und wissen müssen, wie Notrufe für Ihre Organisation verwaltet werden. |
| [**Orts basiertes Routing für direktes Routing**](#location-based-routing-for-direct-routing) |Verwenden von Location-Based Routing (LBR), um die Gebühren Umgehung für Microsoft Teams-Benutzer auf der Grundlage ihres geografischen Standorts zu beschränken. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direktes Routing an einem Ort verwendet, der keine Maut Umgehung zulässt.
| [**Netzwerktopologie für Cloud-Sprachfeatures**](#network-topology-for-voice-features) | Wenn Ihre Organisation Location-Based Routing (LBR) für direktes Routing oder dynamische Notrufe bereitstellt, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Lesen Sie diesen Abschnitt, wenn Sie LBR für die direkte Weiterleitung implementieren oder wenn Sie dynamische Notrufe mit Anrufplan oder direktem Routing implementieren. |
| [**Migrieren Ihrer vorhandenen Sprachlösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie beim Migrieren Ihrer Sprachlösung zu Teams berücksichtigen müssen.  Lesen Sie diesen Abschnitt, wenn Sie von einer vorhandenen VoIP-Lösung zu Teams migrieren. 



> [!Important]
> Dieser Artikel befasst sich mit Sprachlösungen mit Microsoft Teams. Während Lösungen mit Skype for Business Online weiterhin verfügbar sind (wie in [Microsoft-Telefonie-Lösungen](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)beschrieben), ist es wichtig zu verstehen, dass Skype for Business Online am 31. Juli 2021 eingestellt wird.  Nach diesem Datum ist der Skype for Business Online-Dienst nicht mehr verfügbar. Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung, &mdash; ob über Skype for Business Server oder Cloud Connector Edition &mdash; und Skype for Business Online, nicht mehr unterstützt. In diesem Artikel werden die VoIP-Lösungen von Teams und die Art und Weise vorgestellt, wie Sie Ihr lokales Telefonie-Netzwerk bei Bedarf mit Teams über direkte Weiterleitung verbinden können.


## <a name="phone-system"></a>Telefonsystem

Telefon System ist die Microsoft-Technologie für die Aktivierung der Anrufsteuerung und der Funktionen für Private Branch Exchange (PBX) in der Microsoft 365-oder Office 365-Cloud mit Microsoft Teams.

Das Telefon System funktioniert mit Teams oder Skype for Business-Clients und zertifizierten Geräten. Mit dem Telefonsystem können Sie Ihr vorhandenes PBX-System durch eine Reihe von Funktionen ersetzen, die direkt von Microsoft 365 oder Office 365 bereitgestellt werden. 

Anrufe zwischen Benutzern in Ihrer Organisation werden intern innerhalb des Telefonsystems gehandhabt und gehen nie in das öffentlich geschaltete Telefonnetz (PSTN). Dies gilt für Anrufe zwischen Benutzern in Ihrer Organisation, die sich in unterschiedlichen geographischen Regionen befinden, wodurch Kosten für Ferngespräche für diese internen Anrufe entfallen.

In diesem Artikel werden die folgenden wichtigen Features und Funktionen für das Telefon System sowie die Bereitstellungsentscheidungen vorgestellt, die Sie in Frage stellen müssen:

- [Automatische Telefonzentralen und Anrufwarteschleifen](#auto-attendants-and-call-queues)
- [Cloudvoicemail](#cloud-voicemail)
- [Identität des Anrufs](#calling-identity)

![Diagramm 3 zeigt das Telefonsystem enthält automatische Telefonzentralen und Anruf Abfragen, Cloud-Voicemail und Anruf Identität.](media/phone-system-contains.png)

Informationen zu allen Telefonsystem Funktionen und zur Einrichtung des Telefonsystems finden Sie in den folgenden Artikeln:

- [Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)
- [Einrichten des Telefonsystems in Ihrer Organisation](setting-up-your-phone-system.md)<br>
  Hier erfahren Sie, wie Sie Telefon System Lizenzen kaufen und zuweisen, Telefonnummern verwalten und Kommunikationsguthaben für gebührenfreie Nummern einrichten. 

Informationen zum Verwalten unterstützter Geräte finden Sie unter [Verwalten von Geräten in Microsoft Teams und auf dem](devices/device-management.md) [Marketplace für Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Automatische Telefonzentralen und Anrufwarteschlangen

Mit automatischen Telefonzentralen können Sie Menü Optionen einrichten, um Anrufe basierend auf der Eingabe durch Anrufer weiterzuleiten. Anrufwarteschlangen sind Wartebereiche für Anrufer. In Verbindung mit automatischen Telefonzentralen und Anrufwarteschlangen können Anrufer problemlos an die entsprechende Person oder Abteilung in Ihrer Organisation weitergeleitet werden.

Informationen zu automatischen Telefonzentralen und Anrufwarteschlangen finden Sie in den folgenden Artikeln:

- [Planen von automatischen Telefonzentralen und Anrufwarteschlangen für Teams](plan-auto-attendant-call-queue.md)
- [Einrichten einer automatischen Telefonzentrale](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschlange](create-a-phone-system-call-queue.md) 
- [Contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschlangen](voice-case-study-call-queues.md)<br>
  Beschreibt, wie eine fiktive Multi-National Corporation, Contoso, automatische Telefonzentralen und Anrufwarteschlangen für Ihre Sprachlösung implementiert hat.

### <a name="cloud-voicemail"></a>Cloudvoicemail

Cloud Voicemail, powered by Azure Voicemail Services, unterstützt nur Voicemail-Einzahlungen in Exchange-Postfächern. Sie unterstützt keine e-Mail-Systeme von Drittanbietern. 

Cloud Voicemail umfasst Voicemail-Transkription, die standardmäßig für alle Benutzer in Ihrer Organisation aktiviert ist. Für Ihre geschäftlichen Anforderungen müssen Sie möglicherweise die Voicemail-Transkription für bestimmte Benutzer oder alle in der Organisation deaktivieren.

Für Benutzer, die nur online sind, wird Cloud Voicemail automatisch eingerichtet und für Benutzer bereitgestellt, nachdem Ihnen eine Telefon System Lizenz zugewiesen wurde. Für Benutzer von Telefonsystemen mit einem Exchange-Postfach müssen Sie zusätzliche Konfigurationsschritte ausführen. 

Weitere Informationen zu Cloud Voicemail und deren Konfiguration finden Sie in den folgenden Artikeln:

- [Einrichten von Cloudvoicemail](set-up-phone-system-voicemail.md)
- [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identität des Anrufs

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. Informationen zum Konfigurieren der Anrufer-ID oder zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Rufnummernanzeige für einen Benutzer](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Verbindungsoptionen für öffentlich geschaltete Telefonnetzwerke

Das Telefon System bietet vollständige PBX-Funktionen für Ihre Organisation. Damit Benutzer jedoch Anrufe außerhalb Ihrer Organisation tätigen können, müssen Sie das Telefon System mit dem öffentlichen Telefonnetz (PSTN) verbinden. Wenn Sie das Telefon System mit dem PSTN verbinden möchten, können Sie eine der folgenden Optionen auswählen:

- [**Telefon System mit Anrufplan**](#phone-system-with-calling-plan). Eine vollständige Cloud-Lösung mit Microsoft als PSTN-Netzbetreiber.

- [**Telefon System mit Ihrem eigenen PSTN-Netzbetreiber**](#phone-system-with-own-pstn-carrier-with-direct-routing) , indem Sie Direktes Routing verwenden, um Ihre lokale Umgebung mit Teams zu verbinden.

Sie können auch eine Kombination von Optionen auswählen, mit der Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine mehrstufige Migration verwalten können (Weitere Informationen zu späterer Migration).

### <a name="phone-system-with-calling-plan"></a>Telefon System mit Anrufplan 

Wie weiter oben in diesem Artikel beschrieben, ist das Telefon System mit Anrufplan die Microsoft-Lösung für die Cloud-VoIP-Lösung für Teams-Benutzer. Dies ist die einfachste Option, mit der das Microsoft Phone System mit dem öffentlichen Telefonnetz (PSTN) verbunden wird, um Anrufe an Festnetztelefone und Handys in der ganzen Welt zu ermöglichen. Mit dieser Option stellt Microsoft eine PBX-Funktion (Private Branch Exchange) für Ihre Organisation bereit und fungiert als Ihr PSTN-Netzbetreiber, wie in der folgenden Abbildung dargestellt:

![Diagramm 4 zeigt das Telefon System mit automatischen Telefonzentralen, Anrufwarteschlangen, Rufnummernanzeige und mehr sowie Microsoft als PSTN-Netzbetreiber.](media/voice-solution-microsoft-complete.png)

Wenn Sie mit "Ja" zur folgenden Frage Antworten, ist das Telefon System mit Anrufplan die richtige Lösung für Sie:

- Der Anrufplan steht in Ihrer Region zur Verfügung.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht behalten.
- Sie möchten den von Microsoft verwalteten Zugriff auf das PSTN verwenden.

Mit dieser Option: 

- Sie erhalten Microsoft Phone System mit zusätzlichen Tarifen für Inlands-und Auslandsanrufe, die das Anrufen an Telefone in der ganzen Welt ermöglichen (je nachdem, welche Dienst Stufe lizenziert wird).

- Sie müssen keine Bereitstellung oder Wartung einer lokalen Bereitstellung vornehmen &mdash; , da der Anrufplan von Microsoft 365 oder Office 365 ausgeführt wird.

- Hinweis: Falls erforderlich, können Sie eine Verbindung mit einem unterstützten Session Border Controller (SBC) über direkte Weiterleitung für die Interoperabilität mit PBX-Anlagen, analogen Geräten und anderen von der SBC unterstützten Telefongeräten von Drittanbietern herstellen.

Für diese Option ist eine unterbrechungsfreie Verbindung mit Microsoft 365 oder Office 365 erforderlich.

Weitere Informationen zum Aufrufen von Plan finden Sie in den folgenden Artikeln:

- [Welcher Anrufplan ist für Sie am besten geeignet?](calling-plan-landing-page.md)
- [So erwerben Sie einen Anrufplan](calling-plans-for-office-365.md)
- [Landes- und Verfügbarkeit für Anrufe planen](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Einrichten eines Anruf Plans](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Telefon System mit eigenem PSTN-Netzbetreiber mit direktem Routing

Mit dieser Option wird Microsoft Phone System mithilfe des direkten Routings mit Ihrem Telefonie-Netzwerk verbunden, wie in der folgenden Abbildung dargestellt: 

![Diagramm 5 zeigt das Telefon System mit direktem Routing](media/voice-solution-with-direct-routing.png)

Wenn Sie die folgenden Fragen mit "Ja" beantworten, ist das Telefon System mit Direct Routing die richtige Lösung für Sie:

- Sie möchten Teams mit dem Telefon System verwenden.
- Sie müssen ihren derzeitigen PSTN-Netzbetreiber behalten.
- Sie möchten das Routing kombinieren, wobei einige Anrufe durch den Anrufplan durchlaufen werden, einige über Ihren Netzbetreiber.
- Sie müssen mit PBX-Anlagen und/oder Geräten von Drittanbietern wie US-Overhead-Pagern, analogen Geräten usw. kooperieren.

Mit dieser Option:

- Sie verbinden ihr eigenes unterstütztes SBC mit Microsoft Phone System, ohne dass eine zusätzliche lokale Software erforderlich ist.

- Sie können praktisch alle Telefonnetzbetreiber mit Microsoft Phone System verwenden.

- Sie haben die Wahl, diese Option zu konfigurieren und zu verwalten, oder Sie kann von Ihrem Netzbetreiber oder Partner konfiguriert und verwaltet werden (Fragen Sie, ob Ihr Netzbetreiber oder Partner diese Option zur Verfügung stellt).

- Sie können die Interoperabilität zwischen ihren Telefongeräten &mdash; wie einer Drittanbieter-Telefonanlage und analogen Geräten &mdash; und einem Microsoft Phone-System konfigurieren.


Für diese Option ist Folgendes erforderlich:

- Ununterbrochene Verbindung zu Microsoft 365 oder Office 365.

- Bereitstellen und Verwalten eines unterstützten SBC

- Einen Vertrag mit einem Drittanbieter.
  (Es sei denn, es wird eine Option bereitgestellt, um eine Verbindung mit einer Telefonanlage von Drittanbietern, analogen Geräten oder anderen Telefongeräten für Benutzer bereitzustellen, die mit einem Anrufplan auf dem Telefon System arbeiten.)

Weitere Informationen zum direkten Routing finden Sie in den folgenden Artikeln:

- [Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)
- [Planen von direktem Routing](direct-routing-plan.md)
- [Konfigurieren von direktem Routing](direct-routing-configure.md)
- [Verwalten von VoIP-Routing Richtlinien für die Verwendung mit direktem Routing](manage-voice-routing-policies.md)
- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Liste der für direktes Routing zertifizierten Session Border Controller](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Telefonnummern von Microsoft

Microsoft hat zwei Arten von Telefonnummern zur Verfügung: *Teilnehmer* (Benutzer) Nummern, die Benutzern in Ihrer Organisation zugewiesen werden können, und *Dienst* Nummern, die als gebührenpflichtige und gebührenfreie Servicenummern zur Verfügung stehen. Dienstnummern weisen eine höhere Kapazität für die gleichzeitige Anrufkapazität als Abonnenten Nummern auf und können Diensten wie Audiokonferenzen, automatischen Telefonzentralen oder Anrufwarteschlangen zugewiesen werden.

Sie müssen sich entscheiden:

- Welche Benutzer Standorte benötigen neue Telefonnummern von Microsoft?
- Welche Art von Telefonnummer (Abonnent oder Dienst) benötige ich? 
- Wie kann ich vorhandene Telefonnummern an Teams portieren?

Weitere Informationen zum Verwalten von Telefonnummern in Ihrer Organisation, einschließlich Abrufen neuer Nummern oder übertragen von exiting Numbers, finden Sie in den folgenden Artikeln:

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Verschiedene Arten von Telefonnummern, die für den Anrufplan verwendet werden](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Abrufen von Telefonnummern für Ihre Benutzer](getting-phone-numbers-for-your-users.md)
- [Übertragen von Telefonnummern an Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Wählpläne und Anrufweiterleitung

Bei einem Wählplan handelt es sich um eine Reihe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise E. 164-Format) für die Anruf Autorisierung und das Anrufrouting übersetzen.

Sie müssen Folgendes entscheiden: 

- Benötigt meine Organisation einen angepassten Wählplan?
- Für welche Benutzer ist ein benutzerdefinierter Wählplan erforderlich?
- Welcher Mandanten-Wählplan sollte jedem Benutzer zugewiesen werden?

Weitere Informationen finden Sie in den folgenden Artikeln: 

- [Was sind Wählpläne?](what-are-dial-plans.md)
- [Planen von Mandanten Wählplänen](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Notrufe

Wie Sie Notrufe konfigurieren, hängt von ihrer PSTN-Verbindungsoption ab: Microsoft Calling Plan oder Direct Routing. Dynamische Notrufe für Microsoft-Anrufplan und Telefon System Direktes Routing bietet die Möglichkeit, Notrufe zu konfigurieren und zu leiten sowie Sicherheitspersonal entsprechend dem aktuellen Standort des Teams-Clients zu benachrichtigen. Weitere Informationen zu Konzepten und Terminologie für Notrufe und zur Konfiguration dynamischer Notrufe finden Sie in den folgenden Artikeln:

- [Verwalten von Notrufen](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planen und Konfigurieren dynamischer Notrufe](configure-dynamic-emergency-calling.md)
- [Contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md)<br>
  Beschreibt, wie ein fiktiver multinationaler Konzern, Contoso, Notfallanrufe für Ihre Organisation implementiert hat.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based Routing für direktes Routing

In einigen Ländern und Regionen ist es illegal, den PSTN-Anbieter (Public Switched Telephone Network) zu umgehen, um die Kosten für Ferngespräche zu verringern. Location-Based Routing für das direkte Routing können Sie die Gebühren Umgehung für Microsoft Teams-Benutzer auf der Grundlage ihres geografischen Standorts einschränken. Weitere Informationen zum Planen und Konfigurieren von Location-Based Routing (LBR) finden Sie in den folgenden Artikeln:

- [Planen des standortbasierten Routings für direktes Routing](location-based-routing-plan.md)
- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Contoso-Fallstudie: Location-Based-Routing](voice-case-study-location-based-routing.md)<br>
  Beschreibt, wie ein fiktiver multinationaler Konzern, Contoso, Location-Based-Routing für seine Organisation implementiert hat.

## <a name="network-topology-for-voice-features"></a>Netzwerktopologie für Sprachfeatures

Wenn Sie ein dynamisches Notruf-oder Location-Based Routing für das direkte Routing bereitstellen, müssen Sie die Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Informationen zum Konfigurieren von Netzwerkeinstellungen für netzwerkregionen, Netzwerk Websites, Netzwerk-Subnetze und vertrauenswürdige IP-Adressen finden Sie in den folgenden Artikeln:

- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Microsoft Teams – Konzepte und Terminologie](cloud-voice-network-settings.md)
- [Verwalten Ihrer Netzwerktopologie für Cloud-Sprachfeatures in Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Ihrer vorhandenen VoIP-Lösung zu Teams

Für eine Organisation, die ein Upgrade auf Teams durch stellt, besteht das ultimative Ziel darin, alle Benutzer in den TeamsOnly-Modus zu verschieben. Die Verwendung von Telefonsystemen mit Teams wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet. Wenn Sie grundlegende Informationen zum Upgrade auf Teams benötigen, beginnen Sie hier:

- [Erste Schritte mit dem Upgrade von Microsoft Teams](upgrade-start-here.md)
- [Info zum Upgrade-Framework](upgrade-framework.md)
- [Upgrade von Skype for Business auf Teams – für IT-Administratoren](upgrade-to-teams-on-prem-overview.md)

Wenn Sie Ihre Sprachlösung migrieren, gibt es vier mögliche Anrufszenarien beim Umstieg auf den TeamsOnly-Modus:

- [**Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Nach dem Upgrade wird dieser Benutzer weiterhin über einen Microsoft-Anrufplan verfügen.

- **[Ein Benutzer in Skype for Business Online mit lokalen Sprachfunktionen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) über Skype for Business lokal oder Cloud Connector Edition**. Das Upgrade des Benutzers auf Teams muss mit der Migration des Benutzers an Direct Routing koordiniert werden, um sicherzustellen, dass der TeamsOnly-Benutzer über PSTN-Funktionalität verfügt.

- **[Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), der zu Online wechseln und die lokale PSTN-Konnektivität** aufrecht erhalten soll. Wenn Sie diesen Benutzer zu Teams migrieren, muss das lokale Skype for Business-Konto des Benutzers in die Cloud verschoben und koordiniert werden, um die Migration des Benutzers zur direkten Weiterleitung zu koordinieren. 

- **[Ein Benutzer in Skype for Business lokal mit Enterprise-VoIP](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), der in den Online-und mit einem Microsoft-Anrufplan umziehen wird**.  Wenn Sie diesen Benutzer zu Teams migrieren, müssen Sie das lokale Skype for Business-Konto des Benutzers in die Cloud verschieben und diesen Schritt entweder mit a) dem Port der Telefonnummer dieses Benutzers zu einem Microsoft-Anrufplan oder B durch stellen, um eine neue Teilnehmernummer aus verfügbaren Regionen zuzuweisen.

Weitere Informationen dazu, wie Sie Ihre VoIP-Migration für jedes dieser Szenarien implementieren, &mdash; einschließlich Informationen dazu, wann Sie eine hybridverbindung einrichten müssen, und wie Sie Benutzer mit lokalen Sprachfunktionen zum direkten Routing migrieren können, &mdash; finden Sie in den folgenden Artikeln:

- [Überlegungen zum PSTN beim Upgrade auf Teams – für IT-Administratoren](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Fallstudie zu Contoso-VoIP-Migration](voice-case-study-overview.md)<br>
  In der Fallstudie wird beschrieben, wie ein fiktiver multinationaler Konzern, Contoso, eine Teams-Sprachlösung für Ihre Organisation implementiert hat. Es enthält die folgenden Artikel:

  - [Upgradeplan für Teams](voice-case-study-migration-plan.md)
  - [Optionen für Telefon System und PSTN-Konnektivität](voice-case-study-phone-system.md)
  - [Standortbasierte Routing Implementierung](voice-case-study-location-based-routing.md)
  - [Notrufe](voice-case-study-emergency-calling.md)
  - [Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)
  - [Audiokonferenz](voice-case-study-audio-conferencing.md)












