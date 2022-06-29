---
title: Erstellen einer Anrufwarteschleife in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Erfahren Sie, wie Sie Anrufwarteschleifen in Microsoft Teams einrichten. Anrufwarteschleifen stellen eine Begrüßungsnachricht bereit, halten Musik, Anrufumleitung und andere Features bereit.
ms.openlocfilehash: b90dc937d9df1b8578e80c34c96030caf2db5bad
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494692"
---
# <a name="create-a-call-queue"></a>Erstellen einer Anrufwarteschleife

Anrufwarteschleifen leiten Anrufer an Personen in Ihrer Organisation weiter, die bei einem bestimmten Problem oder einer bestimmten Frage helfen können. Anrufe werden jeweils einzeln an die Personen in der Warteschlange verteilt, die als *Agents* bezeichnet werden.

Für Anrufwarteschleifen gibt es die folgenden Optionen:

- Eine Begrüßungsnachricht.
- Musik, während Anrufer in der Warteschleife warten.
- Weiterleitung der Anrufe *nach Eingang* an Telefonberater.
- Optionen für das Vorgehen bei überzähligen Anrufen und Erreichen des Zeitlimits.

Bevor Sie die Verfahren in diesem Artikel befolgen, müssen Sie sich mit ["Planen automatischer Telefonzentralen und Anrufwarteschleifen für Teams"](plan-auto-attendant-call-queue.md) vertraut machen und die [ersten Schritte](plan-auto-attendant-call-queue.md#getting-started) ausgeführt haben.

Die Schritte zum Einrichten einer Anrufwarteschleife umfassen:

1. Einrichten allgemeiner Informationen
1. Festlegen der Begrüßung und der Musik
1. Einrichten der Anrufbeantwortung
1. Auswählen und Zuweisen von Agents
1. Festlegen der Anrufüberlaufbehandlung
1. Festlegen der Behandlung von Anruftimeouts

Die im Artikel beschriebenen Schritte erstellen Anrufwarteschleifen mithilfe des Teams Admin Centers. Anweisungen zum Erstellen von Anrufwarteschleifen mithilfe von PowerShell finden [Sie unter Erstellen von Anrufwarteschleifen mit PowerShell-Cmdlets](create-a-phone-system-call-queue-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-call-queue"></a>Führen Sie die folgenden Schritte aus, um Ihre Anrufwarteschleife einzurichten.

# <a name="step-1-general-info"></a>[Schritt 1: Allgemeine Informationen](#tab/general-info)

## <a name="step-1-set-up-general-information"></a>Schritt 1: Einrichten allgemeiner Informationen

Um eine Anrufwarteschleife einzurichten, erweitern Sie im [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851) **VoIP**, wählen Sie **"Anrufwarteschleifen**" und dann " **Hinzufügen"** aus.

Geben Sie im Feld oben einen Namen für die Anrufwarteschleife ein.

### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

So fügen Sie ein vorhandenes Ressourcenkonto hinzu:

1. Klicken Sie unter **"Ressourcenkonten**" auf die Schaltfläche " **Hinzufügen** ", um ein Ressourcenkonto für diese Anrufwarteschleife hinzuzufügen.
1. Suchen Sie im Bereich **"Konten hinzufügen** " nach dem hinzuzufügenden Ressourcenkonto.
1. Wählen Sie die Schaltfläche **"Hinzufügen"** neben dem Ressourcenkonto aus, das Sie dieser Anrufwarteschleife zuweisen möchten.
1. Wählen Sie unten im Bereich die Schaltfläche **"Hinzufügen"** aus.

Wenn Sie ein Ressourcenkonto erstellen müssen:

1. Klicken Sie unter **"Ressourcenkonten**" auf die Schaltfläche " **Hinzufügen** ", um ein Ressourcenkonto für diese Anrufwarteschleife hinzuzufügen.
1. Suchen Sie im Bereich **"Konten hinzufügen** " nach einer beliebigen Gruppe von Buchstaben, um die Dropdownliste der Ergebnisse hochzuziehen.
1. Wählen Sie unten in den Ergebnissen die Schaltfläche **"+Ressourcenkonto hinzufügen** " aus.
1. Im Bereich **"Ressourcenkonto hinzufügen** ":
    1. Geben Sie einen beschreibenden **Anzeigenamen** ein, der für Agents sichtbar ist.
    1. Geben Sie einen beschreibenden **Benutzernamen** für das Ressourcenkonto ein.
    1. Wählen Sie das Dropdownmenü " **Ressourcenkontotyp** " und dann " **Anrufwarteschleife**" aus.
1. Wählen Sie unten im Bereich die Schaltfläche " **Speichern** " aus.
1. Wählen Sie im Bereich **"Ressourcenkonten** " die Schaltfläche " **Hinzufügen** " aus.

Agents wird der Name des Ressourcenkontos angezeigt, wenn sie einen eingehenden Anruf erhalten.

Weitere Informationen finden [Sie unter Verwalten von Teams-Ressourcenkonten](manage-resource-accounts.md).

### <a name="assign-a-calling-id-optional"></a>Zuweisen einer Anruf-ID (optional)

**Verfügbar für Teams-Kanal-/Collaborative Calling-Desktopbenutzer und mobile Teams-Clientbenutzer mit Standardanrufwarteschleifen.**

Sie können ausgehende Anrufer-ID-Nummern für die Agents zuweisen, indem Sie ein oder mehrere Ressourcenkonten mit einer Telefonnummer angeben. Agents können auswählen, welche ausgehende Anrufer-ID-Nummer für jeden ausgehenden Anruf verwendet werden soll. Innerhalb der Anruf-App können Agents ihre Anrufwarteschleife (CQ) / Automatische Telefonzentrale (AA) oder ihre eigene persönliche Direkte Einwahl (Direct InWard Dial, DID) verwenden.

> [!NOTE]
> Für das Ressourcenkonto, das für Anruf-ID-Zwecke verwendet wird, muss eine **Microsoft Teams Telefon System - Virtual User-Lizenz** und eine der folgenden zugewiesen sein:
>
> - Eine Anrufplanlizenz und eine zugewiesene Telefonnummer
> - Eine zugewiesene Telefonnummer des Telefons "Telefonieanbieter"
> - Eine Online-VoIP-Routingrichtlinie (Telefonnummernzuweisung ist optional, wenn Direct Routing verwendet wird)

1. Wählen **Sie unter "Anruf-ID zuweisen**" die Schaltfläche **"Hinzufügen"** aus.
1. Suchen Sie im Bereich " **Konten hinzufügen** " nach den Ressourcenkonten, die Agents für ausgehende Anrufer-ID-Zwecke verwendet werden sollen.
1. Wählen Sie die Schaltfläche **"Hinzufügen** " neben dem Ressourcenkonto mit einer zugewiesenen Telefonnummer aus.
1. Wählen Sie unten im Bereich die Schaltfläche **"Hinzufügen** " aus.

Wenn Sie nicht über ein Ressourcenkonto mit einer zugewiesenen Telefonnummer verfügen:

1. Klicken Sie unter **"Ressourcenkonten**" auf die Schaltfläche " **Hinzufügen** ", um ein Ressourcenkonto hinzuzufügen.
1. Suchen Sie im Bereich **"Konten hinzufügen** " nach einer beliebigen Gruppe von Buchstaben, um die Dropdownliste der Ergebnisse hochzuziehen.
1. Wählen Sie unten in den Ergebnissen die Schaltfläche **"+Ressourcenkonto hinzufügen** " aus.
1. Im Bereich **"Ressourcenkonto hinzufügen** ":
    1. Geben Sie einen beschreibenden **Anzeigenamen** ein, der für Anrufempfänger sichtbar ist.
    1. Geben Sie einen beschreibenden **Benutzernamen** für das Ressourcenkonto ein.
    1. Wählen Sie das Dropdownmenü " **Ressourcenkontotyp** " und dann " **Anrufwarteschleife**" aus.
1. Wählen Sie unten im Bereich die Schaltfläche " **Speichern** " aus.
1. Wählen Sie im Bereich **"Ressourcenkonten** " die Schaltfläche " **Hinzufügen** " aus.

Nachdem Sie dieses neue Ressourcenkonto für die Anruf-ID erstellt haben, müssen Sie weiterhin Folgendes ausführen:

- Zuweisen einer [Teams Telefon Standard – Virtuelle Benutzerlizenz](manage-resource-accounts.md#assign-a-license)
- Zuweisen einer Microsoft-Anrufplanlizenz, Zuweisen einer Telefonnummer für Telefonieanbieter oder Zuweisen einer Online-VoIP-Routingrichtlinie für Direct Routing
- Weisen Sie die [Diensttelefonnummer dem Ressourcenkonto zu](manage-resource-accounts.md#assign-a-service-number), wenn Sie den Microsoft-Anrufplan verwenden.

### <a name="set-the-call-queue-language"></a>Festlegen der Sprache der Anrufwarteschleife

Wählen Sie eine [unterstützte Sprache](create-a-phone-system-call-queue-languages.md) aus.

Diese Sprache wird für vom System generierte Sprachansagen und Voicemailtranskription verwendet, wenn Sie sie aktivieren.

Nachdem Sie eine Sprache ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Weiter**" aus.

# <a name="step-2---greeting-and-music"></a>[Schritt 2 – Begrüßung und Musik](#tab/greeting-music)

## <a name="step-2-add-a-greeting-and-on-hold-music"></a>Schritt 2: Hinzufügen einer Begrüßung und Wartemusik

Geben Sie an, ob Anrufern eine *Begrüßung* wiedergegeben werden soll, wenn sie in der Warteschleife ankommen.

Wenn Sie **"Audiodatei wiedergeben**" auswählen, müssen Sie eine MP3-, WAV- oder WMA-Datei mit der Begrüßung hochladen, die Sie wiedergeben möchten. Die hochgeladene Aufzeichnung darf nicht größer als 5 MB sein.

Teams bietet Anrufern Standardmusik, während sie *sich in einer Warteschleife befinden*.

- Für die in Microsoft Teams-Anrufwarteschleifen wiedergegebene Standardmusik muss Ihre Organisation keine Lizenzgebühren zahlen.
- Wenn Sie möchten, dass eine bestimmte Audiodatei wiedergegeben wird, klicken Sie auf **Audiodatei wiedergeben**, und laden Sie eine MP3-, WAV- oder WMA-Datei hoch.

> [!NOTE]
> Sie sind dafür verantwortlich, alle erforderlichen Rechte und Berechtigungen zur Verwendung von Musik oder Audiodateien mit Ihrem Microsoft Teams-Dienst unabhängig zu löschen und zu sichern, was geistiges Eigentum und andere Rechte an Musik, Soundeffekten, Audio, Marken, Namen und anderen Inhalten in der Audiodatei von allen relevanten Rechteinhabern umfassen kann, zu denen Künstler gehören können.  Schauspieler, Performer, Musiker, Songwriter, Komponisten, Plattenlabels, Musikheraufkleber, Gewerkschaften, Gilden, Rechtegesellschaften, Verwertungsgesellschaften und alle anderen Parteien, die die Urheberrechte, Soundeffekte, Audio- und andere Rechte an geistigem Eigentum besitzen, kontrollieren oder lizenzieren.

Nachdem Sie eine Begrüßung und Wartemusik ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Weiter**" aus.

# <a name="step-3---call-answering"></a>[Schritt 3 : Anrufbeantwortung](#tab/call-answering)

## <a name="step-3-set-up-who-will-answer-incoming-calls"></a>Schritt 3: Einrichten, wer eingehende Anrufe entgegennimmt

Überprüfen Sie die [Voraussetzungen für das Hinzufügen von Agents zu einer Anrufwarteschleife](plan-auto-attendant-call-queue.md#prerequisites).

### <a name="teams-channel"></a>Teams-Kanal

Sie können bis zu 200 Agents über einen Teams-Kanal hinzufügen. Sie müssen Mitglied des Teams oder der Ersteller oder Besitzer des Kanals sein, um der Warteschlange einen Kanal hinzufügen zu können.

Wenn Sie [einen Teams-Kanal zum Verwalten der Warteschlange verwenden](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e) möchten:

1. Wählen Sie das Optionsfeld " **Team** auswählen" und dann **"Kanal hinzufügen"** aus.
1. Suchen Sie nach dem Team, das Sie verwenden möchten, wählen Sie es aus, und wählen Sie **"Hinzufügen"** aus.
1. Wählen Sie den Kanal aus, den Sie verwenden möchten (es werden nur Standardkanäle unterstützt), und wählen Sie **"Übernehmen"** aus.

Die folgenden Clients werden unterstützt, wenn Sie einen Teams-Kanal für Anrufwarteschleifen verwenden:

- Microsoft Teams-Windows-Client
- Microsoft Teams Mac-Client

> [!NOTE]
> Wenn Sie diese Option verwenden, kann es bis zu 24 Stunden dauern, bis die Anrufwarteschleife voll funktionsfähig ist.
>
> Wenn mehr als 200 Mitglieder im Team vorhanden sind, werden nur die ersten 200 Mitglieder in alphabetischer Reihenfolge als Agents zur Anrufwarteschleife hinzugefügt.

### <a name="users-and-groups"></a>Benutzer und Gruppen

Sie können bis zu 20 Telefonberater einzeln und bis zu 200 über Gruppen hinzufügen.

Wenn Sie einzelne Benutzer oder Gruppen zur Warteschlange hinzufügen möchten:

1. Wählen Sie das Optionsfeld " **Benutzer und Gruppen auswählen** " aus.

So **fügen Sie einen Benutzer** zur Warteschlange hinzu:

1. Wählen Sie **"Benutzer hinzufügen"** aus, suchen Sie nach dem Benutzer, klicken Sie auf **"Hinzufügen"**, und klicken Sie dann auf **"Hinzufügen"**.

So **fügen Sie der Warteschlange eine Gruppe hinzu** :

1. Wählen Sie **"Gruppen hinzufügen"** aus, suchen Sie nach der Gruppe, klicken Sie auf **"Hinzufügen"** und dann auf **"Hinzufügen"**. 
    1. Sie können Verteilerlisten, Sicherheitsgruppen und Microsoft 365-Gruppen oder Microsoft Teams-Teams verwenden.

> [!NOTE]
> Bei Benutzern, die einer Gruppe neu hinzugefügt wurden, kann es bis zu acht Stunden dauern, bis sie den ersten Anruf erhalten.
>
> Wenn mehr als 200 Mitglieder in der Gruppe vorhanden sind, werden nur die ersten 200 Mitglieder in alphabetischer Reihenfolge als Agents zur Anrufwarteschleife hinzugefügt.

### <a name="conference-mode"></a>Konferenzmodus

Der **Konferenzmodus** reduziert die Zeit, die ein Anrufer benötigt, um mit einem Agent verbunden zu werden, nachdem der Agent den Anruf angenommen hat. Damit der Konferenzmodus funktioniert, müssen die Telefonberater in der Anrufwarteschleife einen der folgenden Clients verwenden:

- Die neueste Version des Microsoft Teams-Desktopclients, der Android-App oder der iOS-App
- Microsoft Teams Telefon Version 1449/1.0.94.2020051601 oder höher
  
Die Teams-Konten von Agents müssen auf den TeamsOnly-Modus festgelegt sein. Telefonberater, die diese Anforderungen nicht erfüllen, werden nicht in die Anrufweiterleitungsliste aufgenommen. Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschleifen zu aktivieren, wenn Ihre Agents kompatible Clients verwenden.

> [!NOTE]
> Der Konferenzmodus wird nicht unterstützt, wenn Telefonanrufe von einem Direct Routing-Gateway, das für standortbasiertes Routing aktiviert ist, an die Warteschlange weitergeleitet werden.
>
> Der Konferenzmodus wird nicht unterstützt, wenn Telefonanrufe von Skype for Business Server an die Warteschlange weitergeleitet werden.
> 
> Der Konferenzmodus ist erforderlich, wenn Teams-Benutzer Anrufe mit Anrufwarteschleifen konsultieren/durchstellen müssen.
>
> Agents hören möglicherweise die konfigurierte Wartemusik in der Warteschleife für bis zu 2 Sekunden, wenn sie dem Anruf zum ersten Mal beitreten.


> [!TIP]
> Das Festlegen des **Konferenzmodus** auf **"Ein** " ist die empfohlene Einstellung.

Nachdem Sie ihre Anrufbeantwortungsoptionen ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Weiter**" aus.

# <a name="step-4---agent-routing"></a>[Schritt 4 : Agent-Routing](#tab/agent-routing)

## <a name="step-4-select-your-agent-routing-options"></a>Schritt 4: Auswählen der Optionen für das Agentrouting

Die **Routingmethode** bestimmt die Reihenfolge, in der Anrufe aus der Warteschleife an die Telefonberater weitergeleitet werden.

Wählen Sie eine der folgenden Optionen aus:

- Bei der **Weiterleitung durch Telefonzentrale** werden alle Telefonberater in der Warteschleife gleichzeitig angerufen. Der Anruf wird dem ersten Telefonberater, der den Anruf annimmt, zugewiesen.

- Bei der **seriellen Weiterleitung** werden alle Telefonberater nacheinander in der Reihenfolge angerufen, in der sie in der Liste der **Telefonberater** aufgeführt sind. Wenn ein Agent einen Anruf schließt oder nicht entgegennimmt, wird der nächste Agent angerufen. Dies wird wiederholt, bis der Anruf angenommen wird oder ein Timesout vorliegt.

- Beim **Round Robin** werden die eingehenden Anrufe gleichmäßig verteilt, sodass jeder Telefonberater dieselbe Anzahl von Anrufen aus der Warteschleife erhält. Diese Routingmethode kann in einer Eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit aller Telefonisten sicherzustellen.

- Bei der Option **Längste Inaktivität** wird jeder Anruf an den am längsten inaktiven Telefonberater weitergeleitet. Ein Agent gilt als im Leerlauf, wenn sein Anwesenheitsstatus verfügbar ist. Agents, deren Anwesenheitsstatus nicht verfügbar ist, sind erst dann zum Empfangen von Anrufen berechtigt, wenn sie ihren Anwesenheitsstatus in "Verfügbar" ändern.

Es wird empfohlen, die **Routingmethode** auf **Roundrobin** oder **Den längsten Leerlauf** festzulegen.

> [!NOTE]
> Wenn die [Complianceaufzeichnung](teams-recording-policy.md) für die Agents aktiviert ist, wird die Kombination aus **Konferenzmodus** und **Telefonzentralenrouting** nicht unterstützt. Wenn Sie den **Konferenzmodus** verwenden müssen, wählen Sie **serielles Routing**, **Roundrobin** oder **längsten Leerlauf** als **Routingmethode** aus. Wenn Sie **das Telefonzentralenrouting** verwenden müssen, legen Sie den **Konferenzmodus** auf **"Aus**" fest.
>
> Bei Verwendung des **längsten Leerlaufs** und wenn weniger Anrufe in der Warteschleife als verfügbare Agents vorhanden sind, werden nur die ersten beiden längsten Agents im Leerlauf mit Anrufen aus der Warteschleife angezeigt.
>
> Bei Verwendung des **längsten Leerlaufs** kann es vorkommen, dass ein Agent einen Anruf aus der Warteschleife erhält, kurz nachdem er nicht mehr verfügbar ist, oder eine kurze Verzögerung beim Empfangen eines Anrufs aus der Warteschleife, nachdem er verfügbar wurde.
>
> Anrufpräsentationen in der Anrufwarteschleife für Agents können mit einschränkungen für standortbasiertes Routing in Konflikt stehen. In diesem Fall erhält der Agent ein Popup-Popup, kann den Anruf jedoch nicht annehmen. Diese Bedingung wird fortgesetzt, bis ein anderer Agent verfügbar ist, um den Anruf zu beantworten, der Anrufer hängt auf, oder die Timeoutbedingung für die Anrufwarteschleife tritt auf.  

### <a name="presence-based-call-routing"></a>Anwesenheitsbasierte Anrufweiterleitung

**Das anwesenheitsbasierte Anrufrouting** verwendet den Verfügbarkeitsstatus von Telefonisten, um zu ermitteln, ob ein Agent in die Anrufweiterleitungsliste für die ausgewählte Routingmethode aufgenommen werden soll.

Telefonberater, deren Verfügbarkeitsstatus **Verfügbar** lautet, werden in die Anrufweiterleitungsliste aufgenommen und können Anrufe erhalten. Telefonberater, deren Verfügbarkeitsstatus auf einen anderen Status festgelegt ist, werden von der Anrufweiterleitungsliste ausgeschlossen und erhalten erst dann Anrufe, wenn ihr Verfügbarkeitsstatus wieder **Verfügbar** lautet.

Sie können das **anwesenheitsbasierte Anrufrouting** mit jeder der Routingmethoden aktivieren.

Wenn ein Telefonberater den Empfang von Anrufen deaktiviert hat, wird er unabhängig von seinem aktuellen Verfügbarkeitsstatus nicht in die Anrufweiterleitungsliste aufgenommen.

Es wird empfohlen, das **anwesenheitsbasierte Routing** zu aktivieren.

> [!NOTE]
> Wenn der **längste Leerlauf** als Routingmethode ausgewählt wird, ist anwesenheitsbasiertes Routing erforderlich und automatisch aktiviert, obwohl der Umschalter "Anwesenheitsbasiertes Routing" **deaktiviert** und abgeblendet ist.
>
> Wenn das anwesenheitsbasierte Routing nicht aktiviert ist und mehrere Anrufe in der Warteschlange vorhanden sind, stellt das System diese Anrufe unabhängig von ihrem Anwesenheitsstatus den Agents gleichzeitig vor. Diese Aktion führt zu mehreren Anrufbenachrichtigungen an Agents, insbesondere, wenn einige Agents den anfänglichen Anruf, der ihnen angezeigt wird, nicht annehmen.
>
> Bei Verwendung des **anwesenheitsbasierten Routings** kann es vorkommen, dass ein Agent einen Anruf aus der Warteschleife erhält, kurz nachdem er nicht mehr verfügbar ist, oder eine kurze Verzögerung beim Empfangen eines Anrufs aus der Warteschleife, nachdem er verfügbar wurde.
>
> Telefonberater, die den Skype for Business-Client verwenden, werden nicht in die Anrufweiterleitungsliste aufgenommen, wenn die anwesenheitsbasierte Weiterleitung aktiviert ist. Wenn Telefonberater in Ihrer Organisation Skype for Business verwenden, aktivieren Sie die anwesenheitsbasierte Anrufweiterleitung nicht.

### <a name="call-agents-can-opt-out-of-taking-calls"></a>Telefonisten können die Anrufannahme deaktivieren

Sie können angeben, ob Telefonisten die Möglichkeit haben, die Anrufannahme zu deaktivieren oder nicht.

Es wird empfohlen, die Anrufer zu aktivieren, **um die Anrufannahme zu deaktivieren**.

### <a name="agent-alert-time"></a>Agent-Benachrichtigungszeit

Die **Telefonberater-Benachrichtigungszeit** gibt an, wie lange das Telefon eines Telefonberaters klingelt, bevor die Warteschleife den Anruf an den nächsten Telefonberater umleitet.

Es wird empfohlen, die **Agent-Benachrichtigungszeit** auf **20 Sekunden** festzulegen.

Nachdem Sie die Optionen für die Anrufweiterleitung des Agents ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Weiter**" aus.

# <a name="step-5---call-overflow"></a>[Schritt 5 – Anrufüberlauf](#tab/call-overflow)

## <a name="step-5-set-how-to-handle-call-overflow"></a>Schritt 5: Festlegen der Behandlung des Anrufüberlaufs

Über die Option **Maximale Anrufe in der Warteschleife** wird festgelegt, wie viele Anrufe zu einem beliebigen Zeitpunkt maximal in der Warteschleife warten können.

Der Standardwert lautet "50", möglich ist jedoch 0 bis 200.

Wenn dieses Limit erreicht ist, wird ein Anruf gemäß der Angabe für die Einstellung **Wenn die maximale Anzahl von Anrufen erreicht ist** (siehe unten) behandelt.

Sie können wählen, **ob** Sie den Anruf trennen oder an eines der Anrufweiterleitungsziele **umleiten** möchten.

Beispielsweise könnte dem Anrufer die Möglichkeit gegeben werden, eine Voicemail für die Telefonberater in der Warteschleife zu hinterlassen.

Informationen zu externen [Übertragungen finden Sie unter Voraussetzungen](./plan-auto-attendant-call-queue.md#prerequisites) und externe [Telefonnummernübertragungen – technische Details](create-a-phone-system-auto-attendant.md?tabs=additional-resources) zur Nummernformatierung.

> [!NOTE]
> Wenn die maximale Anzahl von Anrufen auf 0 festgelegt ist, wird die Begrüßungsnachricht nicht wiedergegeben.
>
> Stellen Sie bei der Umleitung zu freigegebenen Voicemails sicher, dass **Personen außerhalb dieser Organisation dieses Team per E-Mail senden** können, für das Team/die Gruppe im Microsoft 365 Admin Center aktiviert ist.

Nachdem Sie Ihre Timeoutoptionen für Anrufe ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Weiter**" aus.

# <a name="step-6---call-timeout"></a>[Schritt 6 – Timeout für Anrufe](#tab/call-timeout)

## <a name="step-6-set-how-to-handle-call-timeouts"></a>Schritt 6: Festlegen der Behandlung von Timeouts für Anrufe

Über die Einstellung **Zeitlimit für Anrufe: maximale Wartezeit** wird festgelegt, wie lange ein Anruf maximal in der Warteschleife gehalten werden kann, bevor er umgeleitet oder beendet wird.

Sie können eine Dauer von 0 Sekunden bis 45 Minuten festlegen.

Sie können den Anruf **trennen** oder an eines der Ziele für die Anrufweiterleitung **umleiten** .

Beispielsweise könnte dem Anrufer die Möglichkeit gegeben werden, eine Voicemail für die Telefonberater in der Warteschleife zu hinterlassen.

Informationen zu externen [Übertragungen finden Sie unter Voraussetzungen](./plan-auto-attendant-call-queue.md#prerequisites) und externe [Telefonnummernübertragungen – technische Details](create-a-phone-system-auto-attendant.md?tabs=additional-resources) zur Nummernformatierung.

> [!NOTE]
> Stellen Sie bei der Umleitung zu freigegebenen Voicemails sicher, dass **Personen außerhalb dieser Organisation dieses Team per E-Mail senden** können, für das Team/die Gruppe im Microsoft 365 Admin Center aktiviert ist.

Nachdem Sie die Optionen für die Anrufweiterleitung des Agents ausgewählt haben, wählen Sie unten auf der Seite "**Anrufwarteschleife hinzufügen**" die Schaltfläche "**Absenden**" aus.

# <a name="additional-resources"></a>[Weitere Ressourcen](#tab/additional-resources)

## <a name="summary-of-recommended-call-queue-settings"></a>Zusammenfassung der empfohlenen Einstellungen für die Anrufwarteschleife

Die folgenden Konfigurationen werden empfohlen:

- **Konferenzmodus** auf **"Ein**"
- **Weiterleitungsmethode** auf **Round Robin** oder **Am längsten inaktiv**
- **Anwesenheitsbasierte Weiterleitung** auf **Ein**
- **Telefonberater-Benachrichtigungszeit:** auf **20 Sekunden**

## <a name="call-queue-feature-compatibility"></a>Kompatibilität der Anrufwarteschleifenfeatures

|Feature                          |Teams Desktop<sup>1</sup> |Teams-Web | Teams Mobile<sup>2</sup> |Lync |IP-Telefone | Standardanrufwarteschleifen |Kanalbasierte Anrufwarteschleifen | Kommentar |
|:--------------------------------|:------------------------:|:--------:|:--------------:|:---:|:--------:|:--------------------:|:------------------------:|:--------|
|**Agent-Routingmethoden**        |                          |          |                |     |          |                      |                          |   |
|`Attendant Routing`              |J                         |J         |J               |J    |J         |J                     |J                         |*Standard*     |
|`Longest Idle`<sup>3</sup>       |J                         |J         |J               |N    |J         |J                     |J                         |*Empfohlen* |
|`Round Robin`                    |J                         |J         |J               |J    |J         |J                     |J                         |*Empfohlen* |
|`Serial`                         |J                         |J         |J               |J    |J         |Y<sup>4</sup>         |Y<sup>4</sup>             |   |
|**Agent-Routingoptionen**        |                          |          |                |     |          |                      |                          |   |
|`Presence Based Routing`<sup>3</sup>|J                      |J         |J               |N    |J         |J                     |J                         |*Empfohlen* |
|`Agents can Opt-out`               |J                       |J         |J               |Y<sup>7</sup>|Y<sup>7</sup>|J          |J                         |*Standard*     |
|**Übertragungsmodi**               |                          |          |                |     |          |                      |                          |   |
|`Conference Mode`<sup>5</sup>    |J                         |J         |J               |N    |Y<sup>6</sup>|J                  |J                         |*Empfohlen* |
|`Transfer Mode`                  |J                         |J         |J               |J    |J         |J                     |J                         |*Standard*              |
|**Collaborative Calling**        |                          |          |                |     |          |                      |                          |   |
|`Channel Based Queues`             |J                       |N         |N               |N    |N         |n/a                   |Y<sup>8</sup>             |   |
|**Dynamische Anrufer-ID**            |                          |          |                |     |          |                      |                          |   |
|`Standard call queue`            |N                         |N         |J               |N    |N         |J                     |n/a                       |   |
|`Channel based call queue`       |J                         |n/a       |n/a             |n/a  |n/a       |n/a                   |J                         |   |
|**PSTN-Konnektivitätsmethoden**    |                          |          |                |     |          |                      |                          |Siehe Hinweis 9   |
|`Calling Plans`                  |J                         |J         |J               |J    |J         |J                     |J                         |   |
|`Direct Routing`                 |J                         |J         |J               |N    |N         |J                     |J                         |   |
|`Operator Connect`               |J                         |J         |J               |     |          |J                     |J                         |   |
|**Sonstige**                |                          |          |                |     |          |                      |                          |   |
|`Call toast shows Resource Account Name` |J                 |N         |J               |J    |          |J                     |J                         |              |

### <a name="notes"></a>Hinweise

1. Microsoft Teams Windows-Client, Microsoft Teams Mac-Client, Microsoft Teams auf virtualisierter Desktopinfrastruktur.
2. Microsoft Teams iPhone-App, Microsoft Teams Android-App.
3. Wenn Sie "Längster Leerlauf" für die Agent-Routingmethode auswählen, wird das anwesenheitsbasierte Routing automatisch aktiviert.
4. Die Reihenfolge kann nur festgelegt werden, wenn einzelne Benutzer als Teil der Standardanrufwarteschleifen hinzugefügt werden. Wenn eine Verteilerliste oder ein Teams-Kanal verwendet wird, ist die Reihenfolge alphabetisch.
5. Der Konferenzmodus wird nicht unterstützt, wenn Telefonanrufe von einem Direct Routing-Gateway, das für standortbasiertes Routing aktiviert ist, an die Warteschlange weitergeleitet werden.
6. nur Microsoft Teams Telefon.
7. Über die Seite "Benutzereinstellungenportal" unter [https://aka.ms/vmsettings](https://aka.ms/vmsettings).
8. Es werden nur öffentliche Kanäle unterstützt.
9. Automatische Telefonzentralen und Anrufwarteschleifen können keine Anrufe zwischen PSTN-Konnektivitätsmethoden übertragen.

## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden für Telefonberater in einer Anrufwarteschleife unterstützt:

- Skype for Business 2016-Desktopclient (32- und 64-Bit-Version)
- Lync 2013-Desktopclient (32- und 64-Bit-Version)
- Alle von Microsoft Teams unterstützten IP-Telefonmodelle. Weitere Informationen finden Sie unter [Erwerben von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
- Mac Skype for Business-Client (Version 16.8.196 und höher)
- Android Skype for Business-Client (Version 6.16.0.9 und höher)
- iPhone Skype for Business-Client (Version 6.16.0 und höher)
- Mac Skype for Business-Client (Version 6.16.0 und höher)
- Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)
- Microsoft Teams Mac-Client
- Microsoft Teams auf [virtualisierter Desktopinfrastruktur](teams-for-vdi.md) (Windows Virtual Desktop, Citrix und VMware)
- Microsoft Teams iPhone-App
- Microsoft Teams Android-App

  > [!NOTE]
  > Anrufwarteschleifen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, Lync-Clients oder Skype for Business-IP-Telefone als Telefonberater. Der Teams-Client wird nur mit einem [Koexistenzmodus von "Nur Teams](setting-your-coexistence-and-upgrade-settings.md)" unterstützt.

## <a name="call-queue-diagnostic-tool"></a>Diagnosetool für die Anrufwarteschleife

Als Administrator können Sie mit dem folgenden Diagnosetool überprüfen, ob eine Anrufwarteschleife Anrufe empfangen kann:

1. Wählen Sie unten **Tests ausführen** aus, um das Diagnosetool im Microsoft 365 Admin füllen.

   > [!div class="nextstepaction"]
   > [Ausführen von Tests: Teams-Anrufwarteschleife](https://aka.ms/TeamsCallQueueDiag)

2. Geben Sie im Diagnosebereich "Ausführen" das Ressourcenkonto in das Feld **"Benutzername" oder "E-Mail** " ein, und wählen Sie dann **"Tests ausführen**" aus.

3. Die Tests geben die besten nächsten Schritte zurück, um alle Mandanten-, Richtlinien- und Ressourcenkontokonfigurationen zu adressieren, um zu überprüfen, ob die Anrufwarteschleife In der Lage ist, Anrufe zu empfangen.

---

## <a name="related-topics"></a>Verwandte Themen

[Hier erfahren Sie, was Sie mit Microsoft Teams Telefon](here-s-what-you-get-with-phone-system.md)

[Servicetelefonnummern erhalten](getting-service-phone-numbers.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
