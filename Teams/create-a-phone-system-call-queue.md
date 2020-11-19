---
title: Erstellen einer Anrufwarteschlange in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie das Telefon System für Anrufwarteschlangen mit Microsoft Teams einrichten, die eine Grußnachricht, Musik, Anrufumleitung und andere Funktionen enthalten.
ms.openlocfilehash: 57ef565a333f89772f5c9d35d664785c2e166679
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49135935"
---
# <a name="create-a-call-queue"></a>Erstellen einer Anrufwarteschlange

Anrufwarteschlangen bieten eine Methode zum Weiterleiten von Anrufern an Personen in Ihrer Organisation, die mit einem bestimmten Problem oder einer bestimmten Frage helfen können. Anrufe werden einzeln an die Personen in der Warteschlange verteilt (die als *Agents* bezeichnet werden). 

Anrufwarteschlangen bieten Folgendes:

- Eine Grußnachricht.

- Musik, während die Leute in einer Warteschleife warten.

- Anrufweiterleitung-in *First Out* (FIFO)-Auftrags-zu-Agents

- Behandlungsoptionen für Warteschlangen Überlauf und-Timeout

Stellen Sie sicher, dass Sie den [Plan für automatische Team-Telefonzentralen und-Warteschlangen](plan-auto-attendant-call-queue.md) gelesen haben, und folgen Sie den [Schritten unter erste](plan-auto-attendant-call-queue.md#getting-started) Schritte, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen.

Zum Einrichten einer Anrufwarteschlange erweitern Sie im Team Admin Center die **Sprache**, klicken Sie auf **Anrufwarteschlangen**, und klicken Sie dann auf **Hinzufügen**.

## <a name="resource-account-and-language"></a>Ressourcenkonto und-Sprache

![Screenshot der Ressourcenkonto-und Spracheinstellungen](media/call-queue-name-language.png)

1. Geben Sie einen Namen für die Anrufwarteschlange ein. Agents sehen diesen Namen, wenn ein eingehender Anruf von der Warteschlange empfangen wird.

2. Klicken Sie auf **Konten hinzufügen**, suchen Sie nach dem Ressourcenkonto, das Sie für diese Anrufwarteschlange verwenden möchten, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen**.

3. Wählen Sie eine Sprache aus. Diese Sprache wird für System generierte Sprachansagen und Voicemail-Transkription verwendet (wenn Sie Sie aktivieren).

## <a name="greetings-and-music-on-hold-in-queue"></a>Gruß-und Musikwiedergabe in Warteschlange

Geben Sie an, ob Sie einen Gruß an Anrufer wiedergeben möchten, wenn Sie in der Warteschlange ankommen. Sie müssen eine MP3-, WAV-oder WMA-Datei hochladen, die die Ansage enthält, die Sie wiedergeben möchten.

Teams stellt Anrufern Standardmusik zur Verfügung, während Sie in einer Warteschlange gehalten werden. Wenn Sie eine bestimmte Audiodatei wiedergeben möchten, wählen Sie **Audiodatei wiedergeben** aus, und laden Sie eine MP3-, WAV-oder WMA-Datei hoch.

> [!NOTE]
> Die hochgeladene Aufzeichnung darf nicht größer als 5 MB sein.
> Die Standardmusik, die in Teams-Anrufwarteschlangen bereitgestellt wird, ist von den von Ihrer Organisation zu zahlenden Gebühren befreit. 

## <a name="call-agents"></a>Anruf-Agents

Lesen Sie die [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) , um Agents zu einer Anrufwarteschlange hinzufügen zu können.

![Screenshot der Einstellungen für Benutzer und Gruppen für Anrufwarteschlangen](media/call-queue-users-groups.png)

Sie können bis zu 20 Agents einzeln und bis zu 200-Agents über Gruppen hinzufügen.

Wenn Sie der Warteschlange einen Benutzer hinzufügen möchten, klicken Sie auf **Benutzer hinzufügen**, suchen Sie nach dem Benutzer, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen**.

Wenn Sie der Warteschlange eine Gruppe hinzufügen möchten, klicken Sie auf **Gruppen hinzufügen**, suchen Sie nach der Gruppe, klicken Sie auf **hinzu** fügen, und klicken Sie dann auf **Hinzufügen**. Sie können Verteilerlisten, Sicherheitsgruppen und Microsoft 365-Gruppen oder Microsoft Teams-Teams verwenden.

> [!NOTE]
> Neue Benutzer, die zu einer Gruppe hinzugefügt wurden, können bis zu acht Stunden dauern, bis Ihr erster Anruf eingeht.

## <a name="call-routing"></a>Anrufweiterleitung

![Screenshot der Einstellungen für den Konferenzmodus und die Routingmethode](media/call-queue-conference-mode-routing-method.png)

Der **Konferenzmodus** verringert erheblich die Zeitdauer, die ein Anrufer mit einem Agenten verbunden sein muss, nachdem der Agent den Anruf angenommen hat. Damit der Konferenzmodus funktioniert, müssen die Agents in der Anrufwarteschlange einen der folgenden Clients verwenden:

  - Die neueste Version des Microsoft Teams-Desktop Clients, der Android-App oder der IOS-App
  - Microsoft Teams Phone Version 1449/1.0.94.2020051601 oder höher
  
Die Konten von Agenten Teams müssen auf "nur für Teams" eingestellt sein. Agents, die die Anforderungen nicht erfüllen, werden nicht in die Anruf Weiterleitungsliste aufgenommen. Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschlangen zu aktivieren, wenn Ihre Agents alle kompatible Clients verwenden.

> [!NOTE]
> Busy on Busy wird vom Konferenzmodus nicht unterstützt. Agents in Warteschlangen anrufen, die keine Anrufwarteschlange sind, werden möglicherweise weiterhin mit einem Anruf Warteschlangen Anruf angezeigt, wenn Anwesenheits basiertes Routing nicht aktiviert ist.

Die **Routing Methode** bestimmt die Reihenfolge, in der die Agents Anrufe aus der Warteschlange empfangen. Wählen Sie eine der folgenden Optionen aus:

- **Attendant-Routing** klingelt alle Agents in der Warteschlange zur gleichen Zeit. Der Anruf wird vom ersten Anruf Agenten abgeholt.

- Das **serielle Routing** klingelt alle Anruf-Agents einzeln in der Reihenfolge, die in der Liste der **Anruf-Agents** festgelegt ist. Wenn ein Agent einen Anruf abschließt oder nicht annimmt, klingelt der Anruf beim nächsten Agenten und versucht alle Agenten, bis er abgeholt wird oder ein Timeout annimmt.

- **Round Robin** balanciert die Weiterleitung eingehender Anrufe, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält. Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.

- **Längster Leerlauf** leitet jeden Anruf an den Agenten weiter, der die längste Zeit inaktiv war. Ein Agent gilt als im Leerlauf, wenn sein Anwesenheitsstatus verfügbar ist oder wenn sein Anwesenheitsstatus für weniger als 10 Minuten abwesend war. Agents, deren Anwesenheitsstatus für mehr als 10 Minuten abwesend war, werden nicht als im Leerlauf betrachtet und sind nicht berechtigt, Anrufe entgegenzunehmen, bis Sie deren Anwesenheit in verfügbar ändern. 

![Screenshot der Einstellungen für Routing, abmelden und Benachrichtigungszeit](media/call-queue-presence-agents-time.png)


Bei **Anwesenheits basiertem Routing** wird der Verfügbarkeitsstatus von Anruf-Agents verwendet, um zu ermitteln, ob ein Agent in die Anruf Weiterleitungsliste für die ausgewählte Routingmethode aufgenommen werden soll. Anruf-Agents, deren Verfügbarkeitsstatus auf **verfügbar** festgesetzt ist, sind in der Anruf Weiterleitungsliste enthalten und können Anrufe empfangen. Agents, deren Verfügbarkeitsstatus auf einen beliebigen anderen Status festgesetzt ist, werden aus der Anruf Weiterleitungsliste ausgeschlossen und empfangen keine Anrufe, bis sich der Verfügbarkeitsstatus wieder in **verfügbar** ändert. 

Sie können das anwesenheitsbasierte Anrufrouting mit einer der Routingmethoden aktivieren.

Wenn sich ein Agent für das Abrufen von Anrufen entscheidet, wird er nicht in die Anruf Weiterleitungsliste aufgenommen, unabhängig davon, auf welchen Verfügbarkeitsstatus er festgesetzt ist. 

> [!NOTE]
> Agents, die den Skype for Business-Client verwenden, sind in der Anruf Weiterleitungsliste nicht enthalten, wenn Anwesenheits basiertes Routing aktiviert ist. Wenn Sie über Agenten verfügen, die Skype for Business verwenden, aktivieren Sie das anwesenheitsbasierte Anrufrouting nicht.

**Agent-Warnungszeit** gibt an, wie lange das Telefon eines Agenten klingelt, bevor die Warteschlange den Anruf an den nächsten Agenten weiterleitet.

Für Warteschlangen mit großem Datenaufkommen empfehlen wir die folgenden Einstellungen:

- **Konferenzmodus** für **Auto**
- **Routingmethode** für das **Attendant-Routing**
- **Anwesenheits basiertes Routing** auf **ein**
- **Agent-Warnungszeit:** bis **20 Sekunden**

## <a name="call-overflow-handling"></a>Anruf Überlauf Behandlung

![Screenshot der Einstellungen für den Anruf Überlauf](media/call-queue-overflow-handling.png)

**Maximale Anrufe in der Warteschlange** geben die maximale Anzahl von Anrufen an, die zu einem beliebigen Zeitpunkt in der Warteschlange warten können. Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen. Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie er durch das festgelegt wird, **Wenn die maximale Anzahl von Anrufen erreicht ist** .

Sie können wählen, ob Sie den Anruf trennen oder ihn an alle Anruf Weiterleitungs Ziele weiterleiten möchten. So können Sie beispielsweise den Anrufer für die Agents in der Warteschlange eine Sprachnachricht hinterlassen. Informationen zu externen Übertragungen finden Sie unter [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) und [Übertragungen externer Telefonnummern – technische Details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) zur Nummernformatierung.

> [!NOTE]
> Wenn die maximale Anzahl von Anrufen auf 0 festgesetzt wird, wird die Ansage nicht wiedergegeben.

## <a name="call-timeout-handling"></a>Anruf Timeout Behandlung

![Screenshot der Anruf Timeouteinstellungen](media/call-queue-timeout-handling.png)

**Anruf Timeout: maximale Wartezeit** gibt an, wie lange ein Anruf maximal in der Warteschlange gehalten werden kann, bevor er umgeleitet oder getrennt wird. Sie können einen Wert von 0 Sekunden bis 45 Minuten angeben.

Sie können wählen, ob Sie den Anruf trennen oder ihn an eines der Anruf Weiterleitungs Ziele weiterleiten möchten. So können Sie beispielsweise den Anrufer für die Agents in der Warteschlange eine Sprachnachricht hinterlassen. Informationen zu externen Übertragungen finden Sie unter [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) und [Übertragungen externer Telefonnummern – technische Details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) zur Nummernformatierung.

Wenn Sie die Optionen für das Anruf Timeout ausgewählt haben, klicken Sie auf **Speichern**.

## <a name="caller-id-for-outbound-calls"></a>Rufnummernanzeige für ausgehende Anrufe

Da sich die Agents in einer Anrufwarteschlange möglicherweise auswählen, um einen Kundenanruf zurückzugeben, sollten Sie in der Lage sein, die Rufnummernanzeige für Mitglieder einer Anrufwarteschlange auf die Dienstnummer einer entsprechenden automatischen Telefonzentrale festzulegen. Weitere Informationen finden Sie unter [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md) .

## <a name="supported-clients"></a>Unterstützte Clients

Die folgenden Clients werden für Anruf-Agents in einer Anrufwarteschlange unterstützt:

  - Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)
  - Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)
  - Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).
  - Mac Skype for Business-Client (Version 16.8.196 und höher)
  - Android Skype for Business-Client (Version 6.16.0.9 und höher)
  - iPhone Skype for Business-Client (Version 6.16.0 und höher)
  - Mac Skype for Business-Client (Version 6.16.0 und höher)
  - Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)
  - Microsoft Teams Mac-Client
  - Microsoft Teams-iPhone-App
  - Microsoft Teams Android-App

    > [!NOTE]
    > Anrufwarteschlangen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, lync-Clients oder Skype for Business-IP-Telefone als Agents.

## <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.

- [Neu – CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Satz-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
