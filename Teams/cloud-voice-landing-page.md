---
title: Planen Ihrer Voice-Lösung in Microsoft Teams
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
description: Erfahren Sie mehr über die Microsoft Teams Cloud Voice-Features und die Entscheidungen, die für die Bereitstellung in Ihrer Organisation zu treffen sind.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d463034109e39920254e3f230546efe7f336af1
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766448"
---
# <a name="plan-your-teams-voice-solution"></a>Planen Ihrer Microsoft Teams-Anruflösung

Dieser Artikel hilft Ihnen bei der Entscheidung, welche Microsoft-Voice-Lösung für Ihr Unternehmen am besten geeignet ist. Nachdem Sie sich entschieden haben, können Sie die im Artikel enthaltenen Verweise zu Inhalten nutzen, um die ausgewählte Lösung zu implementieren.

Die einfachste Lösung finden Sie, &mdash; wenn Teams Telefon Anrufplan erstellen möchten. Dies ist die gänzlich cloudbasierte Lösung von Microsoft, die Funktionen von Nebenstellenanlagen sowie Anrufe in das öffentliche Festnetz bietet, wie in der folgenden Abbildung dargestellt. Bei dieser Lösung ist Microsoft Ihr Festnetzbetreiber.

![Diagramm 1 zeigt Teams Telefon mit Anrufplan.](media/voice-solutions-simple.png)

Wenn Sie auf Folgendes mit "Ja" antworten, Teams Telefon Anrufplan zu erstellen, die richtige Lösung für Sie:

- PSTN-Anrufe sind in Ihrem Land oder Ihrer Region nicht verfügbar.
- Sie müssen nicht bei Ihrem aktuellen Festnetzbetreiber bleiben.
- Sie möchten von Microsoft verwalteten Zugriff auf das Telefonfestnetz nutzen.

Ihre Situation könnte jedoch komplexer sein. So könnten Sie beispielsweise Geschäftsstellen an Standorten haben, an denen keine Microsoft-Anrufpläne verfügbar sind. Oder Sie benötigen eine Kombilösung, die für eine komplexe, multinationale Bereitstellung mit unterschiedlichen Anforderungen an unterschiedlichen geografischen Standorten geeignet ist. Microsoft ermöglicht Kombilösungen:

- Teams Telefon mit Anrufplan
- Teams Telefon bei Ihrem eigenen Netzbetreiber mit Netzbetreiber Verbinden
- Teams Telefon mit Ihrem eigenen PSTN-Netzbetreiber mit Direct-Routing
- Eine Kombinationslösung, die Teams Telefon Anrufplan, Teams Telefon mit Operator Verbinden und/oder Teams Telefon Direct-Routing verwendet

>[!NOTE]
>Wenn Sie ein kleines bis mittleres Unternehmen (300 oder weniger Personen) sind, bündelt Microsoft Telefonsystem mit einem Plan für Inlandsrufe. Weitere Informationen finden Sie [Teams Telefon Anleitungen](/microsoftteams/business-voice/whats-business-voice) für kleine und mittelständische Unternehmen, die Ihnen beim Planen, Einrichten und Verwalten Ihrer Sprachlösung helfen sollen.

## <a name="what-do-you-need-to-read"></a>Was müssen Sie lesen?

**Für alle erforderlich.** Einige Abschnitte in diesem Artikel betreffen alle Organisationen. So sollte sich beispielsweise jeder über die Informationen Teams Telefon und die Optionen für die Verbindung zum öffentlichen Telefonnetz (PSTN) verstehen.


| Für alle erforderlich | Beschreibung |
| :------------|:-------|
| [**Teams Telefon**](#teams-phone) | Microsoft-Technologie, die mit Microsoft Teams Anrufsteuerung und Funktionen von Nebenstellenanlagen in der Microsoft 365-Cloud ermöglicht. |
| [**Optionen für die Verbindung mit dem Telefonfestnetz**](#public-switched-telephone-network-connectivity-options) | Die Wahlmöglichkeit zwischen der Verwendung von Microsoft als Telefonieanbieter oder der Verbindung Ihres eigenen Telefonieanbieters mit Microsoft Teams mittels Telefonieanbieter oder Direct Routing. In Kombination Teams Telefon Konnektivitätsoptionen für das Festnetz ermöglichen es Ihren Benutzern, weltweit Telefonanrufe zu telefonieren.|

**Je nach Ihren Anforderungen.** Einige Abschnitte in diesem und verwandten Artikeln sind je nach Ihren vorhandenen Bereitstellung und Ihren Anforderungen für Sie relevant. Beispielsweise ist standortbasiertes Routing nur für Direct Routing-Kunden an geografischen Standorten erforderlich, die das Umgehen von Gebühren nicht erlauben.

Überlegen Sie, welche dieser zusätzlichen Elemente Sie möglicherweise benötigen:

![In Abbildung 2 sind zusätzliche Voice-Komponenten dargestellt, z. B. Telefonnummern von Microsoft, Wählpläne und Anrufweiterleitung usw.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefonnummernverwaltung**](pstn-connectivity.md#phone-number-management) | Wie Telefonnummern bezogen und verwaltet werden, hängt von Ihrer Festnetzanbindungsoption ab. Lesen Sie diesen Abschnitt, wenn Sie Telefonnummern benötigen, vorhandene Nummern übertragen müssen, Dienstnummern benötigen und so weiter. |
| [**Anrufweiterleitung und Wählpläne**](pstn-connectivity.md#call-routing-and-dial-plans) | Informationen zur Einrichtung und Verwaltung von Wählplänen, bei denen gewählte Telefonnummern für die Anrufautorisierung und die Anrufweiterleitung in ein anderes Format (in der Regel das E.164-Format) übersetzen. Lesen Sie diesen Abschnitt, wenn Sie wissen möchten, was Wählpläne sind und ob Sie welche für Ihre Organisation festlegen müssen.|
| [**Notrufe**](pstn-connectivity.md#emergency-calling) | Wie Notrufe verwaltet und konfiguriert werden, hängt von Ihrer Festnetzanbindungsoption ab. Lesen Sie diesen Abschnitt, wenn Sie Informationen zur Verwaltung von Notrufen in Ihrer Organisation benötigen. |
| [**Standortbasiertes Routing für Direct Routing**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Informationen zur Verwendung des standortbasierten Routings zum Einschränken der Gebührenumgehung für Microsoft Teams-Benutzer anhand ihres geografischen Standorts. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direct Routing an einem Standort verwendet, der keine Umgehung von Gebühren erlaubt.
| [**Netzwerktopologie für Cloud Voice-Funktionen**](pstn-connectivity.md#network-topology-for-voice-features) | Wenn in Ihrer Organisation standortbasiertes Routing für Direct Routing oder die dynamische Notruffunktion bereitgestellt werden soll, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams konfigurieren. Lesen Sie diesen Abschnitt, wenn Sie die Implementierung von standortbasiertem Routing für Direct Routing oder der dynamischen Notruffunktion mit Anrufplan oder Direct Routing planen. |
| [**Migrieren Ihrer bestehenden Anruflösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie bei der Migration Ihrer Anruflösung zu Microsoft Teams bedenken müssen.  Lesen Sie diesen Abschnitt, wenn Sie von einer bestehenden Anruflösung zu Microsoft Teams wechseln. 

> [!Important]
> Den Schwerpunkt dieses Artikels bilden Anruflösungen mit Microsoft Teams. Aufgrund der Ende von Skype for Business Online am 31. Juli 2021 wird die PSTN-Anbindung zwischen Ihrer lokalen Umgebung, unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online unterstützt wird, nicht mehr &mdash; &mdash; unterstützt. In diesem Artikel werden Teams Sprachlösungen und erläutert, wie Sie bei Bedarf Ihr lokales Telefonienetzwerk mit Teams mithilfe von Operator Verbinden Direct Routing verbinden können.


## <a name="teams-phone"></a>Teams Telefon

Teams Telefon microsoft-Technologie zum Aktivieren von Anrufsteuerungs- und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365-Cloud Microsoft Teams.

Teams Telefon kann mit Teams und zertifizierten Geräten verwendet werden. Teams Telefon können Sie Ihr vorhandenes PBX-System durch eine Reihe von Funktionen ersetzen, die direkt von Ihrem Pc Microsoft 365. 

Anrufe zwischen Benutzern in Ihrer Organisation werden intern innerhalb Teams Telefon behandelt und niemals an das Public Switched Telephone Network (PSTN) umgestellt. Dies gilt für Anrufe zwischen Benutzern in Ihrer Organisation, die sich in unterschiedlichen geographischen Regionen befinden, wodurch Kosten für Ferngespräche für diese internen Anrufe entfallen.

In diesem Artikel werden die Teams Telefon wichtigsten Features und Funktionen sowie die Bereitstellungsentscheidungen beschrieben, die Sie berücksichtigen müssen:

- [Automatische Telefonzentralen und Anrufwarteschleifen](#auto-attendants-and-call-queues)
- [Cloud-Voicemail](#cloud-voicemail)
- [Anrufer-ID](#calling-identity)

![Abbildung 3 zeigt, dass das Telefonsystem automatische Telefonzentralen und Anrufwarteschleifen, Cloud-Voicemail und Anrufer-ID umfasst.](media/phone-system-contains.png)

Informationen zu allen Features Teams Telefon und zum Einrichten von Teams Telefon finden Sie in den folgenden Artikeln:

- [Dies ist das, was Sie mit ihren Teams Telefon](here-s-what-you-get-with-phone-system.md)
- [Einrichten Teams Telefon in Ihrer Organisation](setting-up-your-phone-system.md)<br>
  Enthält Informationen dazu, wie Sie Telefonsystemlizenzen kaufen und zuweisen, Telefonnummern verwalten und Kommunikationsguthaben für gebührenfreie Nummern einrichten. 

Informationen zum Verwalten unterstützter Geräte finden Sie unter [Verwalten Ihrer Geräte in Microsoft Teams](devices/device-management.md) und [Microsoft Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Automatische Telefonzentralen und Anrufwarteschleifen

Mit automatischen Telefonzentralen können Sie Menüoptionen einrichten, um Anrufe basierend auf der Eingabe des Anrufers weiterzuleiten. Anrufwarteschleifen sind Wartebereiche für Anrufer. Durch die gemeinsame Verwendung von automatischen Telefonzentralen und Anrufwarteschleifen können Anrufe auf einfache Weise an die geeignete Person oder Abteilung in Ihrer Organisation weitergeleitet werden.

Informationen zu automatischen Telefonzentralen und Warteschleifen finden Sie in den folgenden Artikeln:

- [Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams](plan-auto-attendant-call-queue.md)
- [Einrichten einer automatischen Telefonzentrale](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschleife](create-a-phone-system-call-queue.md) 
- [Contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)<br>
  In diesem Artikel wird beschrieben, wie das fiktive multinationale Unternehmen Contoso automatische Telefonzentralen und Anrufwarteschleifen für seine Anruflösung implementiert hat.

### <a name="cloud-voicemail"></a>Cloud-Voicemail

Cloud-Voicemail basiert auf Azure Voicemail-Diensten und unterstützt die Ablage von Voicemails nur in ein Exchange-Postfach. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. 

Cloud-Voicemail umfasst die Voicemail-Transkription. Diese Funktion ist standardmäßig für alle Benutzer in Ihrer Organisation aktiviert. Ihr Unternehmen muss aufgrund geschäftlicher Anforderungen eventuell die Voicemail-Transkription für bestimmte oder alle Benutzer in der gesamten Organisation deaktivieren.

Cloud-Voicemail wird automatisch für alle Benutzer eingerichtet Teams bereitgestellt.  

Weitere Informationen zu Cloud-Voicemail und dessen Konfiguration finden Sie in den folgenden Artikeln:

- [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md)
- [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. Informationen zum Konfigurieren, Ändern oder Blockieren einer Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Optionen für die Verbindung mit dem Telefonfestnetz

Teams Telefon stellt umfassende PBX-Funktionen für Ihre Organisation bereit. Um Benutzern das Anrufen außerhalb Ihrer Organisation zu ermöglichen, müssen Sie Teams Telefon mit dem öffentlichen Telefonnetz (PSTN) verbinden. Wenn Sie Teams Telefon PSTN verbinden möchten, können Sie eine der folgenden Optionen auswählen:

- [**Teams Telefon mit Anrufplan .**](pstn-connectivity.md#teams-phone-with-calling-plan) Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Anbieter.

- [**Teams Telefon mit Ihrem eigenen Netzbetreiber mithilfe des Netzbetreibers Verbinden.**](operator-connect-plan.md) Wenn Ihr bestehender Betreiber am Microsoft Telefonieanbieter-Programm teilnimmt, kann er den Dienst verwalten, um Festnetzanrufe in Microsoft Teams zu ermöglichen. Informationen zu den Vorteilen und Anforderungen von Operatoren Verbinden Sie unter [Planoperator Verbinden.](operator-connect-plan.md)

- [**Teams Telefon mit Ihrem eigenen PSTN-Netzbetreiber,**](pstn-connectivity.md#teams-phone-with-direct-routing) indem Sie Direct Routing verwenden, um Ihre lokale Umgebung mit ihrem Teams.

Sie können auch eine Kombination von Optionen auswählen, die es Ihnen ermöglichen, eine Lösung für eine komplexe Umgebung zu entwerfen oder eine mehrstufige Migration zu verwalten (weitere Informationen zur Migration später).

Die Teams Telefon sind unabhängig von der von Ihnen aktivierten PSTN-Konnektivitätsoption identisch. Es gibt jedoch einige Funktionsunterschiede, die sich auf die Konfiguration bestimmter Features Teams Telefon, z. B. Anrufrouting und Notrufe, auswirken. Weitere Informationen zu Festnetzanbindungsoptionen und diese Überlegungen zur Konfiguration finden Sie unter [Festnetzanbindungsoptionen](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Ihrer bestehenden Anruflösung zu Microsoft Teams

> [!NOTE]
> Anleitungen zum Planen einer Microsoft Teams-Anruflösung als Teil Ihres Vorhabens eines Upgrades auf Microsoft Teams von Skype for Business Server finden Sie unter [Überlegungen zur Festnetzanbindung für das Upgrade von lokalem Skype for Business auf Microsoft Teams](upgrade-to-teams-on-prem-pstn-considerations.md).

Für eine Organisation, die ein Upgrade auf Microsoft Teams vorhat, besteht das Hauptziel darin, alle Benutzer in den TeamsOnly-Modus zu versetzen. Die Teams Telefon wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet. Grundlegende Informationen zum Upgrade auf Microsoft Teams finden Sie in den folgenden Artikeln:

- [Erste Schritte beim Upgrade auf Microsoft Teams](upgrade-start-here.md)
- [Infos zum Upgrade-Framework](upgrade-framework.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md)

Beim Migrieren einer Anruflösung gibt es vier mögliche Anrufszenarien, wenn ein Wechsel zum TeamsOnly-Modus erfolgt:

- [**Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans): Nach dem Upgrade verfügt dieser Benutzer weiterhin über einen Microsoft-Anrufplan.

- **[Ein Benutzer in Skype for Business Online mit lokalen Anruffunktionen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) über lokales Skype for Business oder Cloud Connector Edition**: Das Upgrade des Benutzers auf Microsoft Teams muss mit seinem Wechsel zu Direct Routing koordiniert werden, um sicherzustellen, dass dem TeamsOnly-Benutzer Festnetzfunktionen zur Verfügung stehen.

- **[Ein Benutzer in lokalem Skype for Business mit Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), der in den Onlinemodus wechselt und die lokale Festnetzanbindung beibehält**: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit dem Übergang des Benutzers zu Direct Routing. 

- **[Ein Benutzer in lokalem Skype for Business mit Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), der in den Onlinemodus wechselt und einen Microsoft-Anrufplan verwendet**:  Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit entweder A) dem Portieren der Telefonnummer dieses Benutzers in einen Microsoft-Anrufplan oder B) dem Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen.

Weitere Informationen zum Wechsel zu einer neuen Anruflösung für jedes dieser Szenarien &mdash; einschließlich Informationen dazu, wann eine Hybridverbindung eingerichtet werden muss und wie Sie Benutzer mit lokaler Anruffunktion zu Direct Routing migrieren &mdash; finden Sie in den folgenden Artikeln:

- [Überlegungen zur Festnetzanbindung beim Upgrade auf Microsoft Teams – für IT-Administratoren](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso-Fallstudie: Wechsel zu einer neuen Anruflösung](voice-case-study-overview.md)<br>
  In dieser Fallstudie wird beschrieben, wie das fiktive multinationale Unternehmen Contoso eine Microsoft Teams-Anruflösung implementiert hat. Sie enthält folgende Artikel:

  - [Plan für das Upgrade auf Microsoft Teams](voice-case-study-migration-plan.md)
  - [Teams Telefon und PSTN-Konnektivitätsoptionen](voice-case-study-phone-system.md)
  - [Implementieren von standortbasiertem Routing](voice-case-study-location-based-routing.md)
  - [Notrufe](voice-case-study-emergency-calling.md)
  - [Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)
  - [Audiokonferenzen](voice-case-study-audio-conferencing.md)
