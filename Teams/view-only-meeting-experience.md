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
ms.openlocfilehash: 76137c0ebfe73c6ba500a0dbcdc8ee1a01de85fc
ms.sourcegitcommit: 242561bfc12504614633539ca696b91dfc890b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52328557"
---
# <a name="teams-view-only-meeting-experience"></a>Schreibgeschützte Teams-Besprechungserfahrung

> [!Note]
> Schreibgeschützte Übertragungen sind verfügbar in Microsoft 365 E3/E3/E5 und Microsoft 365 A3/A5. Dieses Feature wird am 1. März 2021 aktiviert werden, mit Standardeinstellung „DEAKTIVIERT“. Das Feature wird in der Microsoft 365 Government Community Cloud (GCC) gegen Ende März 2021 eingeführt. Für die Government Community Cloud High (GCCH) und das Verteidigungsministerium (Department of Defense, DoD) wird dies zu einem späteren Zeitpunkt eingeführt. Sie müssen nach diesem Datum die Standardrichtlinie ändern, wenn Sie möchten, dass das Feature standardmäßig AKTIVIERT ist. Verwenden Sie PowerShell, um die Richtlinie `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` zu aktivieren.

> [!Note]
> Wenn Ihre Besprechung oder Ihr Webinar die Kapazitätsgrenze erreicht, wird Teams nahtlos skaliert, um eine schreibgeschützte Übertragungserfahrung für 10 000 Personen zu ermöglichen. Außerdem können Sie in dieser Zeit der vermehrten Remotearbeit bis zum Ende des Jahres von noch größeren Übertragungen für 20 000 Personen profitieren.

Microsoft Teams ermöglicht bis zu 10 000 Teilnehmern den Beitritt zu einer Teams-Besprechung. Nachdem die Kapazität der Haupt besprechung erreicht wurde (d. h., wenn 1.000 Benutzer an einer Besprechung teilnehmen), werden weitere Teilnehmer mit einer 6-n-Ansicht teilnehmen.

Teilnehmer, die zuerst an der Besprechung teilnehmen, erhalten bis zur Kapazität der Hauptbesprechung alle Teams Besprechungserfahrung. Sie können Audio und Video freigeben, freigegebene Videos ansehen und im Besprechungschat mitmachen.

Teilnehmer, die der Besprechung nach Erreichen der Kapazitätsgrenze beitreten, werden eine schreibgeschützte Erfahrung erhalten.

Die Teilnehmer können über Desktop, Web und mobile Geräte (Android und iOS) Teams der NS-Ansicht teilnehmen.

> [!Note]
> Die aktuelle Beschränkung der Kapazität der "Haupt besprechung" (also die Anzahl der vollständig interaktiven Benutzer) beträgt 1000 und umfasst GCC.

## <a name="teams-view-only-experience-controls"></a>Teams von Steuerelementen für die 6-Ansicht

Sie aktivieren die "Nur anzeigen"-Erfahrung mithilfe von PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Wenn Sie die Option "Nur anzeigen" deaktivieren möchten, können Sie auch PowerShell verwenden.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In Zukunft können Sie die Option "Nur anzeigen" im Admin Center Teams aktivieren oder deaktivieren.

## <a name="impact-to-users"></a>Auswirkungen auf die Benutzer

Die Erfahrung eines Benutzers wird von mehreren Faktoren abhängen.

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht ist, kann ein Teilnehmer der Besprechung nicht beitreten, wenn einer der folgenden Punkte zutrifft:

- Ein Administrator hat die Teams Barrierefreiansicht entweder für den Organisator oder für den gesamten Mandanten deaktiviert.
- Der Nur-Ansicht-Teilnehmer kann den Wartebereich nicht umgehen. Wenn beispielsweise ein Organisator einer Besprechung entscheidet, dass nur Personen **in** meiner Organisation den Wartebereich umgehen und ein Teilnehmer außerhalb der Organisation versucht, als nur zum Anzeigen verfügbarer Teilnehmer beizukehren, kann er nicht teilnehmen.

Wenn die Kapazität der Haupt besprechung erreicht wurde, sehen der Besprechungsorganisator und die Organisatoren ein Banner, das sie informiert, dass neue Teilnehmer nur als nur zum Anzeigen teilnehmen werden.

  ![die Teams-Client- und Banner-Nachricht für Organisatoren und Referenten](media/chat-and-banner-message.png)

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht wurde, werden Besprechungsteilnehmer auf dem Bildschirm vor dem Beitritt informiert, dass sie im schreibgeschützten Modus beitreten werden.

  ![der Teams-Bildschirm vor dem Beitritt und die Nachricht für Teilnehmer, welche diese über den Beitritt im schreibgeschützten Modus informiert](media/view-only-pre-join-screen.png)

Solange es Platz hat, wird ein Benutzer immer der Hauptbesprechung beitreten. Wenn die Hauptbesprechung die Kapazitätsgrenze erreicht und einer oder mehrere Teilnehmer die Hauptbesprechung verlassen, dann hat die Hauptbesprechung wieder verfügbare Kapazität. Teilnehmer, die der Besprechung beitreten (oder wieder beitreten), werden der Hauptbesprechung beitreten, bis diese die Kapazitätsgrenze wieder erreicht. Teilnehmer, die nur die Ansicht anzeigen, werden nicht automatisch zur Haupt besprechung heraufgestuft und können nicht manuell zur Haupt besprechung heraufgestuft werden.

Wenn Sprech- und Teilnehmerrollen festgelegt wurden und ein Moderator versucht, an einer Besprechung zu teilnehmen, nachdem die Hauptbesprechung Kapazität erreicht hat, tritt er als nur zum Anzeigen bestimmten Teilnehmer bei und hat dieselben Einschränkungen wie andere nur zum Anzeigen bestimmte Teilnehmer. Unterstützung für die Sicherstellung, dass alle Moderatoren an der Haupt besprechung teilnehmen, wird zu einem späteren Zeitpunkt durchgeführt. Der Organisator garantiert immer Platz in der Haupt besprechung.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Auswirkungen auf Organisatoren und Organisatoren von Besprechungen

Zu den Einschränkungen für Organisatoren und Organisatoren von Besprechungen gehören:

- Sie werden keine Informationen über schreibgeschützte Teilnehmer haben. Wir unterstützten EDiscovery für schreibgeschützte Teilnehmer nicht.
- Die Benutzer in der Haupt-Besprechung können die nur angezeigten Teilnehmer nicht sehen.
- Sie können keine schreibgeschützten Teilnehmer aus der Besprechung entfernen.

> [!Note]
> Die Teilnehmeranzahl gibt nur die Personen in der Haupt-Besprechung und nicht die Personen im 6-Personen-Raum wieder. Deshalb erhalten Referenten keine genaue Anzahl der Personen in der schreibgeschützten Erfahrung.

## <a name="experience-for-view-only-attendees"></a>Erfahrung für schreibgeschützte Teilnehmer

Die schreibgeschützte Teams-Erfahrung erlaubt Teilnehmern Folgendes:

- Sie können den Teilnehmern in der Teams-Hauptbesprechung zuhören.
- Sie können den Video-Feed für aktive Sprecher sehen (wenn der aktive Sprecher Videos teilt).
- Anzeigen der freigegebenen Inhalte mithilfe der Desktop- oder Bildschirmfreigabefunktion.

Die folgenden Optionen in Besprechungen stehen den schreibgeschützten Teilnehmern nicht zur Verfügung:

- Sie können der Besprechung nicht beitreten, wenn der Teilnehmer basierend auf festgelegten Wartebereichsrichtlinien oder -Optionen die Berechtigung zum Umgehen des Wartebereichs nicht hat.
- Sie können dem schreibgeschützten Raum nicht mittels Audiokonferenz beitreten.
- Nehmen Sie über ihr System oder Microsoft Teams-Räume CVI-Dienste (Cloud Video Interop) am 5-Raum teil.
- Sie können ihr Audio oder Video nicht teilen.
- Sie können den Besprechungschat nicht sehen und nicht daran teilnehmen.
- Sie können den Video-Feed von Besprechungsteilnehmern nicht sehen, sofern der Teilnehmer nicht der aktive Sprecher ist.
- Weitere PowerPoint, die mithilfe der PowerPoint Live-Funktionalität oder einzelner Anwendungsfreigaben (mit Anderen als Desktop- oder Bildschirmfreigaben) freigegeben werden.
- Heben Sie in der Besprechung die Hand.
- Senden oder sehen Sie Reaktionen.
- Interagieren Sie mit jeder 3P-App, die in die Teams-Besprechung integriert ist, einschließlich Umfragen.

## <a name="view-only-feature-limitations"></a>Schreibgeschützte Feature-Einschränkungen

- Nur anzeigende Teilnehmer können Liveuntertitel nur auf dem Desktop und im Web anzeigen. Derzeit werden nur englische Untertitel unterstützt. 
- Schreibgeschützte Teilnehmer werden durch Streaming-Technologie unterstützt.
- Schreibgeschützte Teilnehmer werden im Anwesenheitsbericht nicht eingeschlossen.
- Schreibgeschützte Teilnehmer werden eine einzelne Videoerfahrung haben. Sie können entweder den aktiven Sprecher sehen, oder den freigegebenen Inhalt, aber nicht beides.
- Derzeit unterstützen wir die Layouts **Galerie**. **Große Galerie** oder **Zusammen-Modus** für schreibgeschützte Teilnehmer nicht.  
- Schreibgeschützte Teilnehmer werden nicht die gleiche Latenzzeit haben wir normale Teilnehmer. <sup>1</sup>

  <sup>1</sup> Schreibgeschützte Teilnehmer werden in der Besprechung eine Verzögerung von 30 Sekunden für Video und Audio haben.  
