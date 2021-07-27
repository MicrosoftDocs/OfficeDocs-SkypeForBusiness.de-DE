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
ms.openlocfilehash: ad80bbdaa5a51540d8444ca97fa72c087f2f1763
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486125"
---
# <a name="plan-your-teams-voice-solution"></a>Planen Ihrer Teams-Sprachlösung 

Dieser Artikel hilft Ihnen bei der Entscheidung, welche Microsoft-Sprachlösung für Ihre Organisation die richtige ist. Nachdem Sie sich entschieden haben, enthält dieser Artikel eine Roadmap für Inhalte, mit deren Unterstützung Sie die ausgewählte Lösung implementieren können.

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
| [**PstN-Konnektivitätsoptionen (Public Switched Telephone Network)**](#public-switched-telephone-network-connectivity-options) | Sie können zwischen der Verwendung von Microsoft als Netzbetreiber oder der Verbindung Ihres eigenen Telefonieanbieters Microsoft Teams einem Netzbetreiber Verbinden Oder Direct Routing wählen. In Kombination Telefonsystem Konnektivitätsoptionen für das Festnetz ermöglichen es Ihren Benutzern, weltweit Telefonanrufe zu telefonieren.|

**Je nach Ihren Anforderungen.** Einige der Abschnitte in diesem und zugehörigen Artikeln sind abhängig von Ihrer vorhandenen Bereitstellung und den vorhandenen Anforderungen relevant. Beispielsweise ist Location-Based Routing nur für Direct Routing-Kunden an geografischen Standorten erforderlich, die keine gebührenpflichtige Umgehung zulassen.

Überlegen Sie, welche dieser zusätzlichen Konfigurationen Sie möglicherweise benötigen:

![Diagramm 2 zeigt zusätzliche Sprachkomponenten, z. B. Telefon-Nummern von Microsoft, Wählpläne und Anrufrouting und so weiter.](media/voice-consider-additional-components.png)

| Je nach Ihren Anforderungen | Beschreibung |
| :------------|:-------|
| [**Telefonnummernverwaltung**](pstn-connectivity.md#phone-number-management) | Wie Sie Telefonnummern erhalten und verwalten, hängt von der PstN-Verbindungsoption ab. Lesen Sie diesen Abschnitt, wenn Sie Telefonnummern beziehen, vorhandene Nummern übertragen, Servicenummern beziehen müssen und so weiter. |
| [**Anrufrouting und Wählpläne**](pstn-connectivity.md#call-routing-and-dial-plans) | Konfigurieren und Verwalten von Wählplänen, mit deren Hilfe gewählte Telefonnummern in ein alternatives Format (normalerweise E.164-Format) für die Anrufautorisierung und die Anrufrouting übersetzt werden. Lesen Sie diesen Abschnitt, wenn Sie wissen möchten, was Wählpläne sind und ob Sie Wählpläne für Ihre Organisation angeben müssen.|
| [**Notrufe**](pstn-connectivity.md#emergency-calling) | Wie Notrufe verwaltet und konfiguriert werden, hängt von der PstN-Konnektivitätsoption ab. Lesen Sie diesen Abschnitt, wenn Sie wissen möchten, wie Sie Notrufe für Ihr Unternehmen verwalten können. |
| [**Standortbasiertes Routing für direktes Routing**](pstn-connectivity.md#location-based-routing-for-direct-routing) |Informationen zur Verwendung Location-Based Routing (LBR) zum Einschränken der Microsoft Teams Umgehung für Benutzer anhand ihres geografischen Standorts. Lesen Sie diesen Abschnitt, wenn Ihre Organisation Direct-Routing an einem Ort verwendet, an dem keine gebührenpflichtige Umgehung zulässig ist.
| [**Netzwerktopologie für Cloud-Sprachfeatures**](pstn-connectivity.md#network-topology-for-voice-features) | Wenn Ihre Organisation Location-Based Routing (LBR) für Direct Routing oder dynamische Notrufe implementiert, müssen Sie Netzwerkeinstellungen für die Verwendung mit diesen Features in Microsoft Teams. Lesen Sie diesen Abschnitt, wenn Sie LBR für Direct-Routing implementieren, oder wenn Sie dynamische Notrufe mit Anrufplan oder Direct Routing implementieren. |
| [**Migrieren Ihrer vorhandenen Sprachlösung**](#migrate-your-existing-voice-solution-to-teams) | Was Sie bei der Migration Ihrer Sprachlösung zu Ihren Sprachlösungen denken müssen, Teams.  Lesen Sie diesen Abschnitt, wenn Sie von einer vorhandenen Sprachlösung zu einem Teams. 

> [!Important]
> Dieser Artikel konzentriert sich auf Sprachlösungen mit Microsoft Teams. Obwohl Lösungen mit Skype for Business Online weiterhin verfügbar sind, ist es wichtig zu wissen, dass Skype for Business Online am 31. Juli 2021 eingestellt wird.  Nach diesem Datum kann auf Skype for Business Onlinedienst nicht mehr zugegriffen werden. Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung – unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online – &mdash; &mdash; nicht mehr unterstützt. In diesem Artikel werden die Teams und erläutert, wie Sie bei Bedarf Ihr lokales Telefonienetzwerk mithilfe von Direct Routing oder Operator Teams mit Verbinden.


## <a name="phone-system"></a>Telefonsystem

Telefonsystem microsoft-Technologie zum Aktivieren von Anrufsteuerungs- und PBX-Funktionen (Private Branch Exchange) in der Microsoft 365-Cloud Microsoft Teams.

Telefonsystem kann mit Teams oder Skype for Business-Clients und zertifizierten Geräten verwendet werden. Telefonsystem können Sie Ihr vorhandenes PBX-System durch eine Reihe von Funktionen ersetzen, die direkt von Ihrem Microsoft 365. 

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

- [**Telefonsystem mit Anrufplan .**](pstn-connectivity.md#phone-system-with-calling-plan) Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Netzbetreiber.

- [**Telefonsystem mit Ihrem eigenen NETZBETREIBER**](operator-connect-plan.md)mithilfe des Operator Verbinden , der derzeit nur in der **öffentlichen Vorschau zur Verfügung steht.**  Wenn Ihr Verbinden Teilnehmer am Microsoft Operator Verbinden-Programm ist, kann er den Dienst verwalten, um PSTN-Anrufe an Teams. Informationen zu den Vorteilen und Anforderungen von Operatoren Verbinden und eine Liste der am Programm teilnehmenden Operatoren finden Sie unter [Planoperator Verbinden.](operator-connect-plan.md)

- [**Telefonsystem mit Ihrem eigenen PSTN-Netzbetreiber,**](pstn-connectivity.md#phone-system-with-direct-routing) indem Sie Direct Routing verwenden, um Ihre lokale Umgebung mit ihrem Teams.

Sie können auch eine Kombination von Optionen auswählen, die es Ihnen ermöglicht, eine Lösung für eine komplexe Umgebung zu entwerfen oder eine Mehrschrittmigration zu verwalten (weitere Informationen zur späteren Migration).

Die Telefonsystem sind unabhängig von der von Ihnen aktivierten PSTN-Konnektivitätsoption identisch. Es gibt jedoch einige Funktionsunterschiede, die sich auf die Konfiguration bestimmter Features Telefonsystem, z. B. Anrufrouting und Notrufe, auswirken. Weitere Informationen zu den PstN-Konnektivitätsoptionen und diesen Überlegungen zur Konfiguration finden Sie unter [PstN-Konnektivitätsoptionen.](pstn-connectivity.md)


## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrieren Sie Ihre vorhandene Sprachlösung zu Teams

> [!NOTE]
> Anleitungen zum Planen einer Teams-Sprachlösung als Teil Ihres Gesamtplans für das Upgrade von Skype for Business Server auf Teams finden Sie unter Überlegungen zum PSTN für das Upgrade von der lokalen Skype for Business auf Teams [PSTN.](upgrade-to-teams-on-prem-pstn-considerations.md)

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
