---
title: Erstellen einer Anrufwarteschleife in Microsoft Teams
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
description: Hier erfahren Sie, wie Sie das Telefonsystem für Anrufwarteschleifen mit Microsoft Teams einrichten können. Diese bieten Optionen wie Begrüßungsnachrichten, Warteschleifenmusik, Anrufweiterleitung und weitere Features.
ms.openlocfilehash: cc0995a6355157de1b43a04caf7814e588232c48
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196749"
---
# <a name="create-a-call-queue"></a>Erstellen einer Anrufwarteschleife

Anrufwarteschleifen ermöglichen es, Anrufe an Personen in Ihrer Organisation weiterzuleiten, die bei einem bestimmten Problem oder einer bestimmten Frage helfen können. Die einzelnen Anrufe werden nach und nach an die Personen (sog. *Telefonberater*) in der Warteschleife verteilt. 

Für Anrufwarteschleifen gibt es die folgenden Optionen:

- Eine Begrüßungsnachricht.

- Musik, während Anrufer in der Warteschleife warten.

- Weiterleitung der Anrufe *nach Eingang* an Telefonberater.

- Optionen für das Vorgehen bei überzähligen Anrufen und Erreichen des Zeitlimits.

Lesen Sie [Automatische Telefonzentralen und Anrufwarteschleifen für Microsoft Teams planen](plan-auto-attendant-call-queue.md) und befolgen Sie die [Anweisungen für die ersten Schritte](plan-auto-attendant-call-queue.md#getting-started), bevor Sie die In diesem Artikel beschriebenen Schritte ausführen.

Gehen Sie zum Einrichten einer Anrufwarteschleife zum Microsoft Teams Admin Center, erweitern Sie **VoIP**, klicken Sie auf **Anrufwarteschleifen** und dann auf **Hinzufügen**.

## <a name="resource-account-and-language"></a>Ressourcenkonto und Sprache

![Screenshot der Einstellungen für Ressourcenkonto und Sprache](media/call-queue-name-language.png)

1. Geben Sie einen Namen für die Anrufwarteschleife ein.

2. Klicken Sie auf **Konten hinzufügen**, suchen Sie nach dem Ressourcenkonto, das Sie für diese Anrufwarteschleife verwenden möchten, klicken Sie auf **Hinzufügen** und dann nochmals auf **Hinzufügen**. (Agents sehen den Namen des Ressourcenkontos, wenn sie einen eingehenden Anruf erhalten.)

3. Wählen Sie eine [unterstützte Sprache aus.](create-a-phone-system-call-queue-languages.md) Diese Sprache wird für vom System generierte Sprachansagen und Voicemailtranskripte verwendet (sofern Sie diese aktivieren).

## <a name="greetings-and-music-on-hold-in-queue"></a>Begrüßung und Musik während des Wartens in der Warteschleife

Legen Sie fest, ob eine Begrüßung abgespielt werden soll, wenn Anrufer in der Warteschleife eintreffen. Die gewünschte Begrüßung muss in Form einer MP3-, WAV- oder WMA-Datei hochgeladen werden.

In Microsoft Teams wird für Anrufer in der Warteschleife Standardmusik wiedergegeben. Wenn Sie möchten, dass eine bestimmte Audiodatei wiedergegeben wird, klicken Sie auf **Audiodatei wiedergeben**, und laden Sie eine MP3-, WAV- oder WMA-Datei hoch.

> [!NOTE]
> Die hochgeladene Aufzeichnung darf nicht größer als 5 MB sein.
> Für die in Microsoft Teams-Anrufwarteschleifen wiedergegebene Standardmusik muss Ihre Organisation keine Lizenzgebühren zahlen. 

## <a name="call-agents"></a>Telefonberater

Lesen Sie den Abschnitt zu den [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites), um einer Anrufwarteschleife Telefonberater hinzufügen zu können.

![Screenshot der Einstellungen für Benutzer und Gruppen für Anrufwarteschleifen](media/call-queue-users-groups.png)

Sie können bis zu 20 Telefonberater einzeln und bis zu 200 über Gruppen hinzufügen.

Um einen Benutzer zur Warteschleife hinzuzufügen, klicken Sie auf **Benutzer hinzufügen**, Suchen Sie nach dem Benutzer, klicken Sie auf **Hinzufügen** und dann erneut auf **Hinzufügen**.

Um der Warteschleifee eine Gruppe hinzuzufügen, klicken Sie auf **Gruppen hinzufügen**, suchen Sie nach der Gruppe, klicken Sie auf **Hinzufügen** und dann erneut auf **Hinzufügen**. Sie können Verteilerlisten, Sicherheitsgruppen und Microsoft 365-Gruppen oder Microsoft Teams-Teams verwenden.

> [!NOTE]
> Bei Benutzern, die einer Gruppe neu hinzugefügt wurden, kann es bis zu acht Stunden dauern, bis sie den ersten Anruf erhalten.

## <a name="call-routing"></a>Anrufweiterleitung

![Screenshot der Einstellungen für Konferenzmodus und Routingmethode](media/call-queue-conference-mode-routing-method.png)

Im **Konferenzmodus** wird die Zeit, bis ein Anrufer mit einem Telefonberater verbunden wird, nachdem dieser den Anruf akzeptiert hat, erheblich reduziert. Damit der Konferenzmodus funktioniert, müssen die Telefonberater in der Anrufwarteschleife einen der folgenden Clients verwenden:

  - Die neueste Version des Microsoft Teams-Desktopclients, der Android-App oder der iOS-App
  - Microsoft Teams Telefon, Version 1449/1.0.94.2020051601 oder höher
  
Die Microsoft Teams-Konten von Telefonberatern müssen auf den Modus "Nur Microsoft Teams" festgelegt werden. Telefonberater, die diese Anforderungen nicht erfüllen, werden nicht in die Anrufweiterleitungsliste aufgenommen. Es wird empfohlen, den Konferenzmodus für Ihre Anrufwarteschleifen zu aktivieren, wenn alle Ihre Telefonberater kompatible Clients verwenden.

Die **Routingmethode** bestimmt die Reihenfolge, in der Anrufe aus der Warteschleife an die Telefonberater weitergeleitet werden. Wählen Sie eine der folgenden Optionen aus:

- Bei der **Weiterleitung durch Telefonzentrale** werden alle Telefonberater in der Warteschleife gleichzeitig angerufen. Der Anruf wird dem ersten Telefonberater, der den Anruf annimmt, zugewiesen.

- Bei der **seriellen Weiterleitung** werden alle Telefonberater nacheinander in der Reihenfolge angerufen, in der sie in der Liste der **Telefonberater** aufgeführt sind. Wenn ein Telefonberater einen Anruf ablehnt oder nicht annimmt, wird der nächste auf der Liste angerufen usf., bis der Anruf angenommen wird oder das Zeitlimit in der Warteschleife erreicht hat.

- Beim **Round Robin** werden die eingehenden Anrufe gleichmäßig verteilt, sodass jeder Telefonberater dieselbe Anzahl von Anrufen aus der Warteschleife erhält. Dies kann in einer Inbound-Vertriebsumgebung erwünscht sein, um für gleiche Chancen für alle Telefonberater zu sorgen.

- Bei der Option **Längste Inaktivität** wird jeder Anruf an den am längsten inaktiven Telefonberater weitergeleitet. Ein Telefonberater gilt als inaktiv, wenn sein Anwesenheitsstatus "Verfügbar" oder seit weniger als 10 Minuten "Abwesend" lautet. Telefonberater, deren Anwesenheitsstatus länger als 10 Minuten "Abwesend" lautet, werden nicht als inaktiv betrachtet und erhalten erst wieder Anrufe, nachdem sie ihren Status in "Verfügbar" geändert haben. 

![Screenshot der Einstellungen für Routing, Abmeldung und Benachrichtigungszeit](media/call-queue-presence-agents-time.png)


Bei der **Anwesenheitsbasierten Weiterleitung** wird anhand des Verfügbarkeitsstatus der Telefonberater festgestellt, ob ein Telefonberater in die Anrufweiterleitungsliste für die ausgewählte Routingmethode eingeschlossen werden soll. Telefonberater, deren Verfügbarkeitsstatus **Verfügbar** lautet, werden in die Anrufweiterleitungsliste aufgenommen und können Anrufe erhalten. Telefonberater, deren Verfügbarkeitsstatus auf einen anderen Status festgelegt ist, werden von der Anrufweiterleitungsliste ausgeschlossen und erhalten erst dann Anrufe, wenn ihr Verfügbarkeitsstatus wieder **Verfügbar** lautet. 

Sie können die anwesenheitsbasierte Anrufweiterleitung mit jeder der Weiterleitungsmethoden aktivieren.

Wenn ein Telefonberater den Empfang von Anrufen deaktiviert hat, wird er unabhängig von seinem aktuellen Verfügbarkeitsstatus nicht in die Anrufweiterleitungsliste aufgenommen. 

> [!NOTE]
> Telefonberater, die den Skype for Business-Client verwenden, werden nicht in die Anrufweiterleitungsliste aufgenommen, wenn die anwesenheitsbasierte Weiterleitung aktiviert ist. Wenn Telefonberater in Ihrer Organisation Skype for Business verwenden, aktivieren Sie die anwesenheitsbasierte Anrufweiterleitung nicht.

Die **Telefonberater-Benachrichtigungszeit** gibt an, wie lange das Telefon eines Telefonberaters klingelt, bevor die Warteschleife den Anruf an den nächsten Telefonberater umleitet.

Die folgenden Konfigurationen werden empfohlen:

- **Konferenzmodus** auf **Automatisch**
- **Weiterleitungsmethode** auf **Round Robin** oder **Am längsten inaktiv**
- **Anwesenheitsbasierte Weiterleitung** auf **Ein**
- **Telefonberater-Benachrichtigungszeit:** auf **20 Sekunden**

> [!NOTE]
> Wenn die anwesenheitsbasierte Weiterleitung nicht aktiviert ist und sich mehrere Anrufe in der Warteschleife befinden, wird das System diese Anrufe an die Telefonberater gleichzeitig und unabhängig von ihrem Anwesenheitsstatus weiterleiten. Dies führt zu mehreren Anrufbenachrichtigungen an Telefonberater, insbesondere, wenn einige den anfänglichen an sie weitergeleiteten Anruf nicht beantworten.

## <a name="call-overflow-handling"></a>Vorgehen bei überzähligen Anrufen

![Screenshot der Einstellungen für überzählige Anrufe](media/call-queue-overflow-handling.png)

Über die Option **Maximale Anrufe in der Warteschleife** wird festgelegt, wie viele Anrufe zu einem beliebigen Zeitpunkt maximal in der Warteschleife warten können. Der Standardwert lautet "50", möglich ist jedoch 0 bis 200. Wenn dieses Limit erreicht ist, wird ein Anruf gemäß der Angabe für die Einstellung **Wenn die maximale Anzahl von Anrufen erreicht ist** (siehe unten) behandelt.

Der Anruf kann beendet oder an eines der Anrufweiterleitungsziele umgeleitet werden. Beispielsweise könnte dem Anrufer die Möglichkeit gegeben werden, eine Voicemail für die Telefonberater in der Warteschleife zu hinterlassen. Informationen zu Nummernformaten für externe Übertragungen finden Sie unter [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) und [Übertragung an externe Telefonnummern – technische Details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details).

> [!NOTE]
> Wenn die maximale Anzahl von Anrufen auf "0" festgelegt ist, wird die Begrüßungsnachricht nicht abgespielt.

## <a name="call-timeout-handling"></a>Vorgehen bei Erreichen des Zeitlimits

![Screenshot der Einstellungen für Anrufzeitlimit](media/call-queue-timeout-handling.png)

Über die Einstellung **Zeitlimit für Anrufe: maximale Wartezeit** wird festgelegt, wie lange ein Anruf maximal in der Warteschleife gehalten werden kann, bevor er umgeleitet oder beendet wird. Sie können eine Dauer von 0 Sekunden bis 45 Minuten festlegen.

Der Anruf kann beendet oder an eines der Anrufweiterleitungsziele umgeleitet werden. Beispielsweise könnte dem Anrufer die Möglichkeit gegeben werden, eine Voicemail für die Telefonberater in der Warteschleife zu hinterlassen. Informationen zu Nummernformaten für externe Übertragungen finden Sie unter [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) und [Übertragung an externe Telefonnummern – technische Details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details).

Wenn Sie Ihre Zeitlimitoptionen für Anrufe ausgewählt haben, klicken Sie auf **Speichern**.

## <a name="caller-id-for-outbound-calls"></a>Anrufer-ID für ausgehende Anrufe

Da Telefonberater in einer Anrufwarteschleife u. U. Anrufe tätigen müssen, um z. B. auf einen Kundenanruf zu antworten, sollten Sie erwägen, die Anrufer-ID für Mitglieder einer Anrufwarteschleife auf die Dienstnummer einer entsprechenden automatischen Telefonzentrale festzulegen. Weitere Informationen finden Sie unter [Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams](caller-id-policies.md).

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
  - Microsoft Teams iPhone-App
  - Microsoft Teams Android-App

    > [!NOTE]
    > Anrufwarteschleifen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, Lync-Clients oder Skype for Business-IP-Telefone als Telefonberater.

## <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Sie können auch Windows PowerShell verwenden, um Anrufwarteschleifen zu erstellen und einzurichten. Zum Verwalten einer Anrufwarteschleife werden die folgenden Cmdlets verwendet.

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>Verwandte Themen

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Servicetelefonnummern erhalten](getting-service-phone-numbers.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
