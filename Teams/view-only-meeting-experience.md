---
title: Schreibgeschützte Besprechungserfahrung
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informationen über die schreibgeschützte Besprechungserfahrung in Teams für Administratoren, Referenten und Teilnehmer
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875055"
---
# <a name="teams-view-only-meeting-experience"></a>Schreibgeschützte Teams-Besprechungserfahrung

> [!Note]
> Schreibgeschützte Übertragungen sind verfügbar in Microsoft 365 E3/E3/E5 und Microsoft 365 A3/A5. Dieses Feature wird am 1. März 2021 aktiviert werden, mit Standardeinstellung „DEAKTIVIERT“. Das Feature wird in der Microsoft 365 Government Community Cloud (GCC) gegen Ende März 2021 eingeführt. Für die Government Community Cloud High (GCCH) und das Verteidigungsministerium (Department of Defense, DoD) wird dies zu einem späteren Zeitpunkt eingeführt. Sie müssen nach diesem Datum die Standardrichtlinie ändern, wenn Sie möchten, dass das Feature standardmäßig AKTIVIERT ist. Verwenden Sie PowerShell, um die Richtlinie `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` zu aktivieren.

> [!Note]
> Wenn Ihre Besprechung oder Ihr Webinar die Kapazitätsgrenze erreicht, wird Teams nahtlos skaliert, um eine schreibgeschützte Übertragungserfahrung für 10 000 Personen zu ermöglichen. Außerdem können Sie in dieser Zeit der vermehrten Remotearbeit bis zum Ende des Jahres von noch größeren Übertragungen für 20 000 Personen profitieren.

Microsoft Teams ermöglicht bis zu 10 000 Teilnehmern den Beitritt zu einer Teams-Besprechung. Wenn die Kapazitätsgrenze für die Hauptbesprechung erreicht ist, können zusätzliche Teilnehmer über eine schreibgeschützte Erfahrung beitreten.

Teilnehmer, die der Besprechung als Erste vor dem Erreichen der Kapazitätsgrenze der Besprechung beitreten, werden die volle Teams-Besprechungserfahrung erhalten. Sie können Audio und Video freigeben, freigegebene Videos ansehen und im Besprechungschat mitmachen.

Teilnehmer, die der Besprechung nach Erreichen der Kapazitätsgrenze beitreten, werden eine schreibgeschützte Erfahrung erhalten.

Wir bieten volle Unterstützung für Android- und iOS-Mobilgeräte, über welche ein Teilnehmer beitreten kann.

> [!Note]
> Die aktuelle Limite für die Anzahl der Personen, die in eine Besprechung anrufen und darin chatten können, beträgt 300 in WW und 250 in GCC, GCC High und DoD.

Die schreibgeschützte Erfahrung ist standardmäßig für jeden Organisator deaktiviert, welcher E3/E5/A3/A5 SKU hat. Es ist keine weitere Konfiguration oder kein weiterer Setup notwendig.

## <a name="disable-teams-view-only-experience"></a>Schreibgeschützte Teams-Erfahrung deaktivieren

Administratoren können die schreibgeschützte Erfahrung mittels PowerShell deaktivieren.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

Zukünftig wird es für Administratoren auch möglich sein, die schreibgeschützte Erfahrung im Teams-Admin Center zu deaktivieren.

## <a name="impact-to-users"></a>Auswirkungen auf die Benutzer

Die Erfahrung eines Benutzers wird von mehreren Faktoren abhängen.

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht ist, kann ein Teilnehmer der Besprechung nicht beitreten, wenn einer der folgenden Punkte zutrifft:

- Ein Administrator hat die schreibgeschützte Teams-Erfahrung deaktiviert.
- Der Teilnehmer hat nicht die Berechtigung zum Umgehen des Wartebereichs.

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht wurde, werden der Besprechungsorganisator und die Referenten ein Banner sehen, welches sie über das Erreichen der Kapazitätsgrenze der Besprechung informiert und darüber, dass neue Teilnehmer als schreibgeschützte Teilnehmer beitreten werden.

  ![die Teams-Client- und Banner-Nachricht für Organisatoren und Referenten](media/chat-and-banner-message.png)

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht wurde, werden Besprechungsteilnehmer auf dem Bildschirm vor dem Beitritt informiert, dass sie im schreibgeschützten Modus beitreten werden.

  ![der Teams-Bildschirm vor dem Beitritt und die Nachricht für Teilnehmer, welche diese über den Beitritt im schreibgeschützten Modus informiert](media/view-only-pre-join-screen.png)

Solange es Platz hat, wird ein Benutzer immer der Hauptbesprechung beitreten. Wenn die Hauptbesprechung die Kapazitätsgrenze erreicht und einer oder mehrere Teilnehmer die Hauptbesprechung verlassen, dann hat die Hauptbesprechung wieder verfügbare Kapazität. Teilnehmer, die der Besprechung beitreten (oder wieder beitreten), werden der Hauptbesprechung beitreten, bis diese die Kapazitätsgrenze wieder erreicht. Teilnehmer, die sich in der schreibgeschützten Erfahrung befinden, werden nicht automatisch in die Hauptbesprechung befördert, und sie können derzeit auch nicht manuell in die Hauptbesprechung befördert werden.

Wenn die Rollen für Referenten/Teilnehmer noch nicht zugeordnet sind, werden Plätze in der Hauptbesprechung nach dem Motto „wer zuerst kommt, wird zuerst bedient“ aufgefüllt. Sobald die Kapazitätsgrenze der Besprechung erreicht ist, werden alle Benutzer der schreibgeschützten Erfahrung beitreten.

## <a name="impact-to-meeting-presenters"></a>Auswirkung auf Referenten der Besprechung

Zu den Einschränkungen für Referenten der Besprechung gehören:

- Sie werden keine Informationen über schreibgeschützte Teilnehmer haben. Wir unterstützten EDiscovery für schreibgeschützte Teilnehmer nicht.
- Benutzer können schreibgeschützte Teilnehmer nicht sehen.
- Sie können keine schreibgeschützten Teilnehmer aus der Besprechung entfernen.

> [!Note]
> Die Teilnehmerzahl spiegelt nur die Teilnehmer in der Besprechung wider, nicht die Personen im schreibgeschützten Raum. Deshalb erhalten Referenten keine genaue Anzahl der Personen in der schreibgeschützten Erfahrung.

## <a name="experience-for-view-only-attendees"></a>Erfahrung für schreibgeschützte Teilnehmer

Die schreibgeschützte Teams-Erfahrung erlaubt Teilnehmern Folgendes:

- Sie können den Teilnehmern in der Teams-Hauptbesprechung zuhören.
- Sie können den Video-Feed für aktive Sprecher sehen (wenn der aktive Sprecher Videos teilt).
- Sie können Inhalte sehen, welche über die „Desktop freigeben“-Funktionalität freigegeben werden.

Die folgenden Optionen in Besprechungen stehen den schreibgeschützten Teilnehmern nicht zur Verfügung:

- Sie können der Besprechung nicht beitreten, wenn der Teilnehmer basierend auf festgelegten Wartebereichsrichtlinien oder -Optionen die Berechtigung zum Umgehen des Wartebereichs nicht hat.
- Sie können dem schreibgeschützten Raum nicht mittels Audiokonferenz beitreten.
- Sie können dem schreibgeschützten Raum nicht über das Microsoft Teams-Raumsystem oder über Cloud Video Interop (CVI)-Dienste beitreten.
- Sie können ihr Audio oder Video nicht teilen.
- Sie können den Besprechungschat nicht sehen und nicht daran teilnehmen.
- Sie können den Video-Feed von Besprechungsteilnehmern nicht sehen, sofern der Teilnehmer nicht der aktive Sprecher ist.
- Sie können keine PowerPoint-Dateien sehen, die mit der nativen PowerPoint-Freigabefunktion oder einzelnen Anwendungsfreigaben (mit Ausnahme der Desktopfreigabe) freigegeben wurden.

## <a name="view-only-feature-limitations"></a>Schreibgeschützte Feature-Einschränkungen

- Schreibgeschützte Teilnehmer werden Liveuntertitel immer sehen, unabhängig von der Einstellung für Liveuntertitel für diese Besprechung. Derzeit werden nur englische Untertitel unterstützt. 
- Schreibgeschützte Teilnehmer werden durch Streaming-Technologie unterstützt.
- Schreibgeschützte Teilnehmer werden im Anwesenheitsbericht nicht eingeschlossen.
- Schreibgeschützte Teilnehmer werden eine einzelne Videoerfahrung haben. Sie können entweder den aktiven Sprecher sehen, oder den freigegebenen Inhalt, aber nicht beides.
- Derzeit unterstützen wir die Layouts **Galerie**. **Große Galerie** oder **Zusammen-Modus** für schreibgeschützte Teilnehmer nicht.  
- Schreibgeschützte Teilnehmer werden nicht die gleiche Latenzzeit haben wir normale Teilnehmer. <sup>1</sup>

  <sup>1</sup> Schreibgeschützte Teilnehmer werden in der Besprechung eine Verzögerung von 30 Sekunden für Video und Audio haben.  
