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
description: Mer informasjon über die Cloud-VoIP-Features von Microsoft Teams und die Bereitstellungsentscheidungen, die Sie für Ihre Organisation treffen werden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40f2a4f56b9d1c174696265300226263eb41a9de
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606064"
---
# <a name="plan-your-teams-voice-solution"></a>Planen Ihrer Microsoft Teams-Anruflösung

Dieser Artikel hilft Ihnen bei der Entscheidung, welche Microsoft-Voice-Lösung für Ihr Unternehmen am besten geeignet ist. Nachdem Sie sich entschieden haben, können Sie die im Artikel enthaltenen Verweise zu Inhalten nutzen, um die ausgewählte Lösung zu implementieren.

Möglicherweise möchten Sie die einfachste Lösung verwenden, das &mdash;Telefonsystem mit Anrufplan. Diese Option ist die All-in-the-Cloud-Lösung von Microsoft, die PbX-Funktionen (Private Branch Exchange) und Anrufe an das Telefonfestnetz (Public Switched Telephone Network, PSTN) bereitstellt, wie im folgenden Diagramm dargestellt. Bei dieser Lösung ist Microsoft Ihr Festnetzbetreiber.

![In Abbildung 1 ist das Microsoft-Telefonsystems mit Anrufplan dargestellt.](media/voice-solutions-simple.png)

Wenn Sie die folgenden Punkte mit "Ja" beantworten können, ist "Telefonsystem mit Anrufplan" die richtige Lösung für Sie:

- PSTN-Anrufe sind in Ihrem Land oder Ihrer Region nicht verfügbar.
- Sie müssen Ihren aktuellen PSTN-Netzbetreiber nicht aufbewahren.
- Sie möchten von Microsoft verwalteten Zugriff auf das Telefonfestnetz nutzen.

Ihre Situation könnte jedoch komplexer sein. So könnten Sie beispielsweise Geschäftsstellen an Standorten haben, an denen keine Microsoft-Anrufpläne verfügbar sind. Oder Sie benötigen eine Kombilösung, die für eine komplexe, multinationale Bereitstellung mit unterschiedlichen Anforderungen an unterschiedlichen geografischen Standorten geeignet ist. Microsoft ermöglicht Kombilösungen:

- Telefonsystem mit Anrufplan
- Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber mit Operator Connect
- Telefonsystem mit Ihrem eigenen Festnetz-Mobilfunkanbieter mit Telefonieanbieter mit Mobil (Public Preview Release)
- Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber mit Direct Routing
- Eine Kombilösung aus Telefonsystem mit Anrufplan, Telefonsystem mit Telefonieanbieter und/oder Telefonsystem mit Direct Routing

Eine visuelle Zusammenfassung aller Optionen für VoIP-Lösungen finden Sie auf dem Poster "VoIP-Lösungen".

[![Poster "Microsoft Voice Solutions".](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [PDF](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>Wenn Sie ein kleines bis mittleres Unternehmen (300 oder weniger Personen) sind, bündelt Microsoft jetzt das Telefonsystem mit einem Anrufplan für Inland. Weitere Informationen finden Sie in den [Telefonsystemanleitungen für kleine und mittelständische Unternehmen](/microsoftteams/business-voice/whats-business-voice) , die Ihnen bei der Planung, Einrichtung und Verwaltung Ihrer VoIP-Lösung helfen.

## <a name="what-do-you-need-to-read"></a>Was müssen Sie lesen?

**Für alle erforderlich.** Einige Abschnitte in diesem Artikel betreffen alle Organisationen. Alle sollten sich beispielsweise mit dem Telefonsystem vertraut machen und die Optionen zum Herstellen einer Verbindung mit dem öffentlichen Telefonfestnetz verstehen.


| Für alle erforderlich | Beschreibung |
| :------------|:-------|
| [**Telefonsystem**](#phone-system) | Microsoft-Technologie, die mit Microsoft Teams Anrufsteuerung und Funktionen von Nebenstellenanlagen in der Microsoft 365-Cloud ermöglicht. |
| [**Optionen für die Verbindung mit dem Telefonfestnetz**](#public-switched-telephone-network-connectivity-options) | Wählen Sie Microsoft als Telefonieanbieter aus, oder verbinden Sie Ihren eigenen Telefonieanbieter mit Microsoft Teams mithilfe von Operator Connect oder Direct Routing. In Kombination mit dem Microsoft-Telefonsystem ermöglichen die Festnetzanbindungsoptionen Ihren Benutzern das Telefonieren auf der ganzen Welt.|

**Je nach Ihren Anforderungen.** Einige Abschnitte in diesem und verwandten Artikeln sind je nach Ihren vorhandenen Bereitstellung und Ihren Anforderungen für Sie relevant. Beispielsweise ist standortbasiertes Routing nur für Direct Routing-Kunden an geografischen Standorten erforderlich, die das Umgehen von Gebühren nicht erlauben.

Überlegen Sie, welche dieser anderen Konfigurationen Sie möglicherweise benötigen:

![Diagramm 2 zeigt andere VoIP-Komponenten, z. B. Telefonnummern von Microsoft, Wählpläne und Anrufweiterleitung usw.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefonnummernverwaltung**](pstn-connectivity.md#phone-number-management) | Wie Telefonnummern bezogen und verwaltet werden, hängt von Ihrer Festnetzanbindungsoption ab. Lesen Sie diesen Abschnitt, wenn Sie Telefonnummern benötigen, vorhandene Nummern übertragen müssen, Dienstnummern benötigen und so weiter. |
| [**Anrufweiterleitung und Wählpläne**](pstn-connectivity.md#call-routing-and-dial-plans) | Informationen zur Einrichtung und Verwaltung von Wählplänen, bei denen gewählte Telefonnummern für die Anrufautorisierung und die Anrufweiterleitung in ein anderes Format (in der Regel das E.164-Format) übersetzen. Lesen Sie diesen Abschnitt, wenn Sie wissen möchten, was Wählpläne sind und ob Sie welche für Ihre Organisation festlegen müssen.|
| [**Notrufe**](pstn-connectivity.md#emergency-calling) | Wie Notrufe verwaltet und konfiguriert werden, hängt von Ihrer Festnetzanbindungsoption ab. Lesen Sie diesen Abschnitt, wenn Sie Informationen zur Verwaltung von Notrufen in Ihrer Organisation benötigen. |
| [**Standortbasiertes Routing für Direct Routing**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Informationen zur Verwendung des standortbasierten Routings zum Einschränken der Gebührenumgehung für Microsoft Teams-Benutzer anhand ihres geografischen Standorts. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direct Routing an einem Ort verwendet, der keine gebührenpflichtige Umgehung zulässt.
| [**Netzwerktopologie für Cloud Voice-Funktionen**](pstn-connectivity.md#network-topology-for-voice-features) | Wenn Ihre Organisation Location-Based Routing (LBR) für Direct Routing oder dynamische Notrufe bereitstellt, müssen Sie Netzwerkeinstellungen für diese Features in Microsoft Teams konfigurieren. Lesen Sie diesen Abschnitt, wenn Sie LBR für Direct Routing implementieren oder dynamische Notrufe mit Anrufplan oder Direct Routing implementieren. |
| [**Migrieren Ihrer bestehenden Anruflösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie bei der Migration Ihrer Anruflösung zu Microsoft Teams bedenken müssen.  Lesen Sie diesen Abschnitt, wenn Sie von einer vorhandenen VoIP-Lösung zu Teams migrieren. 

> [!Important]
> Den Schwerpunkt dieses Artikels bilden Anruflösungen mit Microsoft Teams. Aufgrund der Einstellung von Skype for Business Online am 31. Juli 2021 wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung&mdash;über Skype for Business Server oder Cloud Connector Edition&mdash;und Skype for Business Online nicht mehr unterstützt. In diesem Artikel werden Teams-VoIP-Lösungen vorgestellt und erläutert, wie Sie Ihr lokales Telefonienetzwerk ggf. mithilfe von Telefonieanbieter oder Direct Routing mit Teams verbinden können.


## <a name="phone-system"></a>Telefonsystem

"Telefonsystem" ist die Technologie von Microsoft, die Anrufsteuerung und Funktionen von Nebenstellenanlagen in der Microsoft 365-Cloud mit Microsoft Teams bereitstellt.

Das Telefonsystem funktioniert mit Teams-Clients und zertifizierten Geräten. Mit dem Telefonsystem können Sie Ihr bestehendes Nebenstellensystem durch eine Reihe von Funktionen ersetzen, die direkt über Microsoft 365 bereitgestellt werden. 

Anrufe zwischen Benutzern in Ihrer Organisation – unabhängig vom geografischen Bereich – werden intern innerhalb des Telefonsystems verarbeitet. Diese internen Anrufe gehen niemals an das Telefonfestnetz (Public Switched Telephone Network, PSTN), daher vermeidet Ihr Unternehmen Ferngespräche.

In diesem Artikel werden die folgenden wichtigsten Features und Funktionen von "Telefonsystem" sowie die Entscheidungen hinsichtlich einer Bereitstellung erläutert, die Sie berücksichtigen müssen:

- [Automatische Telefonzentralen und Anrufwarteschleifen](#auto-attendants-and-call-queues)
- [Cloud-Voicemail](#cloud-voicemail)
- [Anrufer-ID](#calling-identity)

![Abbildung 3 zeigt, dass das Telefonsystem automatische Telefonzentralen und Anrufwarteschleifen, Cloud-Voicemail und Anrufer-ID umfasst.](media/phone-system-contains.png)

Informationen zu allen Telefonsystemfunktionen und zum Einrichten des Telefonsystems finden Sie in den folgenden Artikeln:

- [Erfahren Sie, was Ihnen das Telefonsystem bietet](here-s-what-you-get-with-phone-system.md)
- [Einrichten des Telefonsystems in Ihrer Organisation](setting-up-your-phone-system.md)<br>
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

Cloud-Voicemail wird automatisch für Teams-Benutzer eingerichtet und bereitgestellt.  

Weitere Informationen zu Cloud-Voicemail und dessen Konfiguration finden Sie in den folgenden Artikeln:

- [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md)
- [Festlegen von Voicemail-Richtlinien in Ihrer Organisation](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte. Informationen zum Konfigurieren, Ändern oder Blockieren einer Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Optionen für die Verbindung mit dem Telefonfestnetz

Das Telefonsystem bietet vollständige Nebenstellenanlagenfunktionen für Ihre Organisation. Damit Benutzer jedoch Anrufe außerhalb Ihrer Organisation tätigen können, müssen Sie das Telefonsystem mit dem öffentlichen Telefonfestnetz verbinden. Zum Herstellen einer Verbindung zwischen Microsoft-Telefonsystem und Telefonfestnetz können Sie eine der folgenden Optionen auswählen:

- [**Telefonsystem mit Anrufplan**](pstn-connectivity.md#phone-system-with-calling-plan): Eine gänzlich cloudbasierte Lösung, bei der Microsoft Ihr Festnetzbetreiber ist.

- [**Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber mithilfe von Operator Connect**](operator-connect-plan.md). Wenn Ihr vorhandener Betreiber am Microsoft Operator Connect-Programm teilnimmt, kann er mitHilfe von Operator Connect den Dienst verwalten, um PSTN-Anrufe an Teams zu übertragen. 

- [**Telefonsystem mit Ihrem eigenen Festnetz-Mobilfunkanbieter mithilfe Telefonieanbieter mit Mobil**](operator-connect-mobile-plan.md) **öffentlichen Überprüfungsversion**. Mit Telefonieanbieter mit Mobil kann Ihr bestehender Anbieter, der am Microsoft Telefonieanbieter mit Mobil-Programm teilnimmt, den Dienst für die Verwendung von SIM-fähigen Mobiltelefonnummern mit Teams verwalten. 

- [**Telefonsystem mit Ihrem eigenen Festnetzbetreiber unter Verwendung von Direct Routing**](pstn-connectivity.md#phone-system-with-direct-routing) um Ihre lokale Umgebung mit Microsoft Teams zu verbinden.


Sie können eine Kombination aus Optionen auswählen, mit der Sie eine Lösung für eine komplexe Umgebung entwerfen oder eine Migration in mehreren Schritten verwalten können. Weitere Informationen zur Migration finden Sie später.

Die meisten Funktionen des Microsoft-Telefonsystems sind unabhängig von der gewählten Festnetzanbindungsoption identisch. Es gibt jedoch einige Unterschiede in der Funktionalität, was sich auf die Konfiguration bestimmter Telefonsystemfunktionen auswirkt, z. B. Anrufweiterleitung und Notrufe. Weitere Informationen zu PSTN-Konnektivitätsoptionen und Konfigurationsüberlegungen finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Ihrer bestehenden Anruflösung zu Microsoft Teams

> [!NOTE]
> Anleitungen zum Planen einer Microsoft Teams-Anruflösung als Teil Ihres Vorhabens eines Upgrades auf Microsoft Teams von Skype for Business Server finden Sie unter [Überlegungen zur Festnetzanbindung für das Upgrade von lokalem Skype for Business auf Microsoft Teams](upgrade-to-teams-on-prem-pstn-considerations.md).

Für eine Organisation, die ein Upgrade auf Microsoft Teams vorhat, besteht das Hauptziel darin, alle Benutzer in den TeamsOnly-Modus zu versetzen. Die Verwendung des Telefonsystems wird nur unterstützt, wenn sich der Benutzer im TeamsOnly-Modus befindet. Grundlegende Informationen zum Upgrade auf Microsoft Teams finden Sie in den folgenden Artikeln:

- [Erste Schritte beim Upgrade auf Microsoft Teams](upgrade-start-here.md)
- [Infos zum Upgrade-Framework](upgrade-framework.md)
- [Upgradestrategien für IT-Administratoren](upgrade-to-teams-on-prem-implement.md)

Beim Migrieren einer Anruflösung gibt es vier mögliche Anrufszenarien, wenn ein Wechsel zum TeamsOnly-Modus erfolgt:

- [**Ein Benutzer in Skype for Business Online mit einem Microsoft-Anrufplan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans): Nach dem Upgrade verfügt dieser Benutzer weiterhin über einen Microsoft-Anrufplan.

- **[Ein Benutzer in Skype for Business Online mit lokalen Anruffunktionen](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) über lokales Skype for Business oder Cloud Connector Edition**: Das Upgrade des Benutzers auf Microsoft Teams muss mit seinem Wechsel zu Direct Routing koordiniert werden, um sicherzustellen, dass dem TeamsOnly-Benutzer Festnetzfunktionen zur Verfügung stehen.

- **[Ein Benutzer in lokalem Skype for Business mit Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), der in den Onlinemodus wechselt und die lokale Festnetzanbindung beibehält**: Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit dem Übergang des Benutzers zu Direct Routing. 

- **[Ein Benutzer in lokalem Skype for Business mit Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), der in den Onlinemodus wechselt und einen Microsoft-Anrufplan verwendet**:  Die Migration dieses Benutzers zu Microsoft Teams erfordert das Verlegen seines lokalen Skype for Business-Kontos in die Cloud und die Koordination dieser Verlegung mit entweder A) dem Portieren der Telefonnummer dieses Benutzers in einen Microsoft-Anrufplan oder B) dem Zuweisen einer neuen Abonnentennummer aus verfügbaren Regionen.

Weitere Informationen dazu, wie Sie Ihre VoIP-Migration für jedes dieser Szenarien implementieren, finden Sie in den folgenden Artikeln:

- [Überlegungen zur Festnetzanbindung beim Upgrade auf Microsoft Teams – für IT-Administratoren](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso-Fallstudie: Wechsel zu einer neuen Anruflösung](voice-case-study-overview.md)<br>
  In dieser Fallstudie wird beschrieben, wie das fiktive multinationale Unternehmen Contoso eine Microsoft Teams-Anruflösung implementiert hat. Sie enthält folgende Artikel:

  - [Plan für das Upgrade auf Microsoft Teams](voice-case-study-migration-plan.md)
  - [Optionen für Telefonsystem und Festnetzanbindung](voice-case-study-phone-system.md)
  - [Implementieren von standortbasiertem Routing](voice-case-study-location-based-routing.md)
  - [Notrufe](voice-case-study-emergency-calling.md)
  - [Automatische Telefonzentralen und Anrufwarteschleifen](voice-case-study-call-queues.md)
  - [Audiokonferenzen](voice-case-study-audio-conferencing.md)
