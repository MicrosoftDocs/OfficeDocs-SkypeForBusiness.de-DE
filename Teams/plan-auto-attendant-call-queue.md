---
title: Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Erfahren Sie mehr über automatische Telefonzentralen und Anrufwarteschleifen und wie Sie diese verwenden können, um Anrufern zu helfen, durch ein Menüsystem zu navigieren, um Personen oder Abteilungen in Ihrer Organisation zu erreichen.
ms.openlocfilehash: 218377b2082d1a057f503abbf83d37ff78686986
ms.sourcegitcommit: 55ba3ed53421da6619724a360d15e80262241079
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "67070736"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Planen von automatischen Telefonzentralen und Anrufwarteschleifen in Microsoft Teams

Mit automatischen Telefonzentralen können Sie Menüoptionen einrichten, um Anrufe basierend auf der Eingabe des Anrufers weiterzuleiten. Menüoptionen für eine automatische Telefonzentrale – z. B. "Für den Vertrieb drücken Sie 1 - Für Dienste drücken Sie 2" – lassen Sie eine Organisation eine Reihe von Optionen bereitstellen, die Anrufer schnell zu ihrem Ziel führen, ohne sich auf einen menschlichen Operator verlassen zu müssen, um eingehende Anrufe zu verarbeiten.

Anrufwarteschleifen sind Wartebereiche für Anrufer. In Situationen, in denen Anrufer jemanden mit einer bestimmten Spezialität – z. B. Vertrieb oder Service – anstelle einer bestimmten Person erreichen müssen, können Sie Anrufwarteschleifen verwenden, um Anrufer mit der Gruppe von Agents zu verbinden, die ihnen helfen können. Anrufer werden so lange gehalten, bis ein agent, der der Warteschleife zugewiesen ist, für den Anruf verfügbar ist.

Durch die gemeinsame Verwendung von automatischen Telefonzentralen und Anrufwarteschleifen können Anrufe auf einfache Weise an die geeignete Person oder Abteilung in Ihrer Organisation weitergeleitet werden.

## <a name="auto-attendants"></a>Automatische Telefonzentralen

Der Hauptzweck einer automatischen Telefonzentrale besteht darin, einen Anrufer basierend auf den Eingaben des Anrufers zu den bereitgestellten Menüoptionen an eine entsprechende Person oder Abteilung zu leiten. Anrufer können an bestimmte Personen in Ihrer Organisation, an Anrufwarteschleifen, in denen sie warten, um mit dem nächsten verfügbaren Agent zu sprechen, oder an Voicemail weitergeleitet werden. Für Geschäftszeiten, Arbeitsstunden und Feiertage können unterschiedliche Anrufweiterleitungsoptionen angegeben werden.

Menüeingabeaufforderungen können mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Spracherkennung akzeptiert Sprachbefehle für die freihändige Navigation, aber Anrufer können auch die Wähltastatur des Telefons verwenden, um in Menüs zu navigieren.

Jede automatische Telefonzentrale verfügt über eine bestimmte Sprache und Zeitzone. Wenn Sie geschäftet in mehreren Sprachen oder in mehreren Teilen der Welt, können Sie so viele verschiedene automatische Telefonzentralen erstellen, wie Sie für Ihre Anrufer benötigen.

Für jede automatische Telefonzentrale können Sie einen Operator konfigurieren. Während Sie Telefonistenanrufe so konfigurieren können, dass sie zu verschiedenen Zielen geleitet werden, ist das Operatorfeature so konzipiert, dass Anrufer mit einer bestimmten Person in Ihrer Organisation sprechen können, die ihnen helfen kann.

Automatische Telefonzentralen können so konfiguriert werden, dass Anrufer das Verzeichnis Ihrer Organisation entweder nach Name oder Durchwahlnummer durchsuchen können. Innerhalb einer automatischen Telefonzentrale können Sie angeben, wer für die Verzeichnissuche verfügbar ist, indem Sie Gruppen von Benutzern auswählen, die ein- oder ausgeschlossen werden sollen. (Dies wird als *Wählbereich* bezeichnet.)

Anrufer können eine automatische Telefonzentrale entweder über eine direkte Telefonnummer erreichen, wenn sie konfiguriert ist, oder indem sie von einer anderen automatischen Telefonzentrale oder einer Anrufwarteschleife umgeleitet werden.

## <a name="call-queues"></a>Anrufwarteschleifen

Eine Anrufwarteschleife entspricht einem Warteraum in einem physischen Gebäude. Anrufer warten im Wartebereich, während Anrufe an die Agents in der Warteschleife weitergeleitet werden. Anrufwarteschleifen werden häufig für Vertriebs- und Dienstfunktionen verwendet. Anrufwarteschleifen können jedoch für jede Situation verwendet werden, in der die Anzahl der Anrufe Ihre interne Kapazität überschreitet, z. B. ein Empfangsmitarbeiter in einer besetzten Einrichtung.

Anrufwarteschleifen ermöglichen das spezifische Routing von Anrufen in Fällen, in denen die Gesamtzahl der Anrufer in der Warteschleife oder die Wartezeit die von Ihnen angegebenen Grenzwerte überschreitet. Anrufe können an bestimmte Personen, Voicemail, andere Anrufwarteschleifen oder automatische Telefonzentralen weitergeleitet werden.

Wie automatische Telefonzentralen haben Anrufwarteschleifen jeweils eine Spracheinstellung. Sie können unterschiedliche Anrufwarteschleifen verwenden, wenn Sie geschäftet in mehreren Sprachen. Agents können Mitglieder mehrerer Warteschlangen sein, wenn sie mehrsprachiger Art sind.

Für jede Anrufwarteschleife können Sie angeben, ob Agents in der Warteschleife die Anrufannahme ablehnen können und ob Anrufe basierend auf ihren Anwesenheitsinformationen in Teams an sie weitergeleitet werden sollen.

Sie können einer Anrufwarteschleife eine Telefonnummer zuweisen. Anrufwarteschleifen bieten jedoch keine separate Anrufweiterleitung für Arbeitsstunden und Feiertage. Sofern Ihre Anrufwarteschleife nicht 24/7 besetzt ist, empfehlen wir, die Telefonnummer einer automatischen Telefonzentrale zuzuweisen, die während der Geschäftszeiten zur Anrufwarteschleife umleitet.

## <a name="prerequisites"></a>Voraussetzungen

Um automatische Telefonzentralen und Anrufwarteschleifen zu konfigurieren, benötigen Sie die folgenden Ressourcen:

- Ein [Ressourcenkonto](manage-resource-accounts.md) für jede automatische Telefonzentrale und jede Anrufwarteschleife
- Eine kostenlose Microsoft Teams Telefon Ressourcenkontolizenz für jedes Ressourcenkonto, das direkt von Teams-Benutzern oder externen Telefonnummern wählbar ist
- Mindestens eine [Microsoft-Dienstnummer](getting-service-phone-numbers.md), eine Telefonieanbieternummer, eine Direct Routing-Nummer oder eine Hybridnummer für jedes Ressourcenkonto, das direkt über externe Telefonnummern wählbar sein soll
  - Die Servicenummer kann eine gebührenpflichtige oder gebührenfreie Nummer sein.

> [!NOTE]
> Ressourcenkonten sind für die Anmeldung deaktiviert und müssen so bleiben. Chat und Anwesenheit sind für diese Konten nicht verfügbar.

Agents, die Anrufe aus den Anrufwarteschleifen erhalten, müssen online oder lokal aktiviert Enterprise-VoIP werden. Wenn die Anrufwarteschleifen Direct Routing-Nummern verwenden, ist außerdem Folgendes erforderlich:

- Eine Online-VoIP-Routingrichtlinie zugewiesen, wenn die Anrufwarteschleife den Übertragungsmodus verwendet
- Eine Audiokonferenzlizenz oder eine Online-VoIP-Routingrichtlinie, die zugewiesen ist, wenn die Anrufwarteschleife den Konferenzmodus verwendet

Wenn Ihre Agents die Microsoft Teams-App für Anrufwarteschleifenanrufe verwenden, müssen sie sich im TeamsOnly-Modus befinden.

Wenn Sie ein Ressourcenkonto für Anrufleitungs-ID-Zwecke in Anrufwarteschleifen verwenden, muss das Ressourcenkonto über eine Lizenz für das Teams-Telefonressourcenkonto und eine der folgenden Zugewiesenen verfügen:

- Eine [Anrufplanlizenz](calling-plans-for-office-365.md) und eine zugewiesene Telefonnummer
- Eine zugewiesene Telefonnummer [des Telefons "Telefonieanbieter"](operator-connect-plan.md)
- Eine [Online-VoIP-Routingrichtlinie](manage-voice-routing-policies.md) (Telefonnummernzuweisung ist optional, wenn Direct Routing verwendet wird)

Wenn eine automatische Telefonzentrale oder Anrufwarteschleife Anrufe an eine externe Nummer übergibt, müssen bestimmte Ressourcenkonten, wie unten beschrieben, über eine Lizenz für das Microsoft Teams-Telefonressourcenkonto und eine der folgenden Zugewiesenen verfügen:

- Eine [Anrufplanlizenz](calling-plans-for-office-365.md) und eine zugewiesene Telefonnummer
- Eine zugewiesene Telefonnummer [des Telefons "Telefonieanbieter"](operator-connect-plan.md)
- Eine [Online-VoIP-Routingrichtlinie](manage-voice-routing-policies.md) (Telefonnummernzuweisung ist optional, wenn Direct Routing verwendet wird)

Welches Ressourcenkonto lizenziert werden soll:
- Lizenzieren des Ressourcenkontos für die erste automatische Telefonzentrale, die den Anruf empfängt, wenn diese automatische Telefonzentrale an andere automatische Telefonzentralen oder Anrufwarteschleifen übergibt, die Anrufe extern übertragen
- Lizenzieren Sie in allen anderen Anrufszenarien das Ressourcenkonto der automatischen Telefonzentrale oder Anrufwarteschleife, die die externe Übertragung durchführt.

> [!NOTE]
> Wenn der dem Ressourcenkonto zugewiesene Anrufplan deaktiviert oder entfernt wird, werden [Guthaben für Kommunikationen](what-are-communications-credits.md), sofern im Mandanten verfügbar (ohne dem Ressourcenkonto zugewiesen) verwendet. Wenn kein Anrufplan oder Guthaben für Kommunikationen vorhanden ist, schlägt der Anruf fehl.
>
> Direct Routing-Servicenummern für automatische Telefonzentralen und Anrufwarteschleifen werden nur für Microsoft Teams-Benutzer und -Telefonberater unterstützt.
> 
> Übertragungen zwischen Anrufplan-, Telefonie- und Direct Routing-Trunks werden nicht unterstützt.
> 
> In einem Hybridszenario muss das Ressourcenkonto lokal erstellt werden. Weitere Informationen finden Sie unter [Planen von Cloud-Anrufwarteschleifen](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Geschäftsentscheidungen

Bevor Sie Ihre automatischen Telefonzentralen und Anrufwarteschleifen einrichten, sollten Sie einige Entscheidungen zur Verwendung dieser Features in Ihrem Unternehmen treffen. Diese Entscheidungen bestimmen die Einstellungen, die Sie auswählen, wenn Sie Ihre automatischen Telefonzentralen und Anrufwarteschleifen konfigurieren.

Dokumentieren Sie Ihre Antworten auf diese Fragen, und geben Sie die Informationen an den Administrator, der die Konfiguration durchführt.

- Welche Sprachen benötigen Sie? Wo werden diese Sprachen benötigt – welche Abteilung oder Gruppe?
- Möchten Sie Spracheingaben von Anrufern oder nur Wähleingaben zulassen?
- Benötigen Sie ein separates Anrufrouting für Arbeitsstunden oder Feiertage? Was sind die Stunden und Feiertage?
- Möchten Sie es Agents in einer Anrufwarteschleife ermöglichen, die Anrufannahme zu deaktivieren?
- Möchten Sie, dass Agents in Ihren Anrufwarteschleifen oder Ihr Operator eine bestimmte Anrufer-ID haben, wenn sie sich auswählen?
- Möchten Sie das [Parken und Abrufen von Anrufen](call-park-and-retrieve.md) in Ihrer Organisation aktivieren, um bei Anrufübergaben zwischen Personen oder Abteilungen zu helfen?
- Möchten Sie für die Sprachansagen eigene Aufzeichnen oder die vom System generierte Stimme verwenden? (Die vom System generierte Stimme ist einfach zu aktualisieren.)

## <a name="technical-decisions"></a>Technische Entscheidungen

Wenn Sie automatische Telefonzentralen und Anrufwarteschleifen verwenden, um Anrufer mit Personen in Ihrer Organisation zu verbinden, müssen Einige technische Entscheidungen getroffen werden, bevor Sie die Konfiguration starten.

Agents können Anrufwarteschleifen auf folgende Weise hinzugefügt werden:

- Einzelne Benutzer
- Verteilerlisten
- Sicherheitsgruppen, einschließlich E-Mail-aktivierter Sicherheitsgruppen
- Microsoft 365-Gruppen oder Teams

Sie können bei Bedarf eine Kombination dieser Optionen für jede Warteschlange verwenden. Gruppen mit einer E-Mail-Adresse können für Voicemail verwendet werden. Die Verwendung von Teams bietet viele Vorteile, darunter freigegebene Dateispeicherung und Chat zwischen Agents, ein gemeinsames Postfach, in dem Voicemails empfangen werden können, und eine erweiterbare Plattform, die die Integration in Ihre Branchenanwendungen oder Power Apps umfassen kann.

Es wird empfohlen, eine Strategie zum Hinzufügen von Telefonisten zu Warteschlangen auszuwählen, bevor Sie Ihre Konfiguration starten.

Wenn Sie über eine vorhandene Infrastruktur für automatische Telefonzentralen und Anrufwarteschleifen verfügen und zu Teams migrieren, benötigen Sie einen Plan, um Ihre vorhandenen Telefonnummern an die neuen automatischen Telefonzentralen und Anrufwarteschleifen zu übertragen. Möglicherweise müssen Sie einen [Portierungsauftrag](phone-number-calling-plans/port-order-overview.md) erstellen, um Ihre Nummern von einem anderen Anbieter zu verschieben. Es wird empfohlen, vorübergehend eine oder mehrere neue Telefonnummern zu erwerben und ihre automatischen Telefonzentralen- und Anrufwarteschleifenflüsse zu testen, bevor Sie sie über die Nummern wechseln, die Sie derzeit in Betrieb haben.

**Der Konferenzmodus** ist eine Option in Anrufwarteschleifen, die die Zeit für die Verbindung von Teams-VOIP-Anrufen und PSTN-Anrufen mit einem Agent erheblich reduziert. Damit der Konferenzmodus funktioniert, müssen die Telefonberater in der Anrufwarteschleife einen der folgenden Clients verwenden:

- Die neueste Version des Microsoft Teams-Desktopclients, der Android-App oder der iOS-App
- Microsoft Phone System Version 1449/1.0.94.2020051601 oder höher
  
Legen Sie die Teams-Konten von Agents auf den reinen Teams-Modus fest. Telefonberater, die diese Anforderungen nicht erfüllen, werden nicht in die Anrufweiterleitungsliste aufgenommen.

Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschleifen zu aktivieren, wenn alle Ihre Telefonberater kompatible Clients verwenden.

**Anrufweiterleitungsflusspläne** helfen bei der Ermittlung der effizientesten Weiterleitung für Personen, die sich in Ihre Organisation einwähnen. Informationen zum Planen des Anrufweiterleitungsflusses finden Sie unter [Planen des Anrufweiterleitungsflusses](plan-your-call-routing-flow.md).

## <a name="getting-started"></a>Erste Schritte

Nachdem Sie die Planungsaufgaben in diesem Artikel abgeschlossen haben, führen Sie die folgenden Schritte aus, um Ihre automatischen Telefonzentralen und Anrufwarteschleifen einzurichten:

1. Rufen Sie die Servicenummern ab, die Sie für die automatischen Telefonzentralen und Anrufwarteschleifen benötigen, auf die Sie durch Direkteinwahl von außerhalb Ihrer Organisation zugreifen können möchten. Dies kann das [Übertragen von Nummern von einem anderen Anbieter](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder [das Anfordern neuer Servicenummern](getting-service-phone-numbers.md) umfassen.

2. Rufen Sie eine [Microsoft Teams Phone-Ressourcenkontolizenz](teams-add-on-licensing/virtual-user.md) für jedes Ressourcenkonto ab, das Sie erstellen möchten. Diese Lizenzen sind kostenlos, daher empfehlen wir, ein paar zusätzliche Lizenzen zu erhalten, falls Sie sich entscheiden, in Zukunft Änderungen an Ihren Ressourcenkonten vorzunehmen.

3. [Erstellen Sie ein Ressourcenkonto](manage-resource-accounts.md) für jede automatische Telefonzentrale und Anrufwarteschleife, die Sie erstellen möchten. Weisen Sie jedem Konto eine Microsoft Teams-Telefonressourcenkontolizenz und optional eine Dienstnummer zu.

4. [Erstellen Sie die Feiertage](set-up-holidays-in-teams.md) , für die Sie ein separates Anrufrouting in Ihren automatischen Telefonzentralen haben möchten.

5. Richten Sie optional das [Parken und Abrufen von Anrufen](call-park-and-retrieve.md) ein, wenn Sie dieses Feature verwenden möchten, um Anrufüberweisungen zu unterstützen.

6. Erstellen Sie die Gruppen, die Sie verwenden möchten, um die Telefonberater für die Anrufwarteschleifen zu enthalten.

7. Wenn Sie die Durchwahl zulassen möchten, stellen Sie sicher, dass Sie die Durchwahlnummer Ihrer Benutzer zu ihrem Azure Active Directory-Profil hinzugefügt haben.

Nachdem Sie die oben beschriebenen Schritte abgeschlossen haben, können Sie Ihre automatischen Telefonzentralen und Anrufwarteschleifen erstellen. Da automatische Telefonzentralen und Anrufwarteschleifen Anrufe aneinander umleiten können, verweisen Sie auf das von Ihnen erstellte Workflowdiagramm, um zu bestimmen, welche automatische Telefonzentrale oder Anrufwarteschleife zuerst erstellt werden soll. Im Beispiel im obigen Diagramm würden Sie die Vertriebs- und Supportanrufwarteschleifen erstellen, bevor Sie die automatische Haupttelefonzentrale von Contoso erstellen, da die automatische Hauptzentrale Anrufer an die Vertriebs- und Supportanrufwarteschleifen weiterleiten muss.

In den folgenden Artikeln finden Sie Informationen zum Erstellen automatischer Telefonzentralen und Anrufwarteschleifen:

- [Einrichten einer automatischen Telefonzentrale](create-a-phone-system-auto-attendant.md)
- [Erstellen einer Anrufwarteschleife](create-a-phone-system-call-queue.md)

Wenn Sie umfangreichere Funktionen benötigen, z. B. die Integration in Workflows, Bots und SMS, sollten Sie [Azure Communication Services](/azure/communication-services/overview) in Betracht ziehen.

## <a name="related-topics"></a>Verwandte Themen

[Planen von direktem Routing](direct-routing-plan.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
