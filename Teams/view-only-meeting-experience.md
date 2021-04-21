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
ms.openlocfilehash: 2f9df0bf1c4acaf8ec32db07ce4af961c491ba0d
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899116"
---
# <a name="teams-view-only-meeting-experience"></a>Schreibgeschützte Teams-Besprechungserfahrung

> [!Note]
> Schreibgeschützte Übertragungen sind verfügbar in Microsoft 365 E3/E3/E5 und Microsoft 365 A3/A5. Dieses Feature wird am 1. März 2021 aktiviert werden, mit Standardeinstellung „DEAKTIVIERT“. Das Feature wird in der Microsoft 365 Government Community Cloud (GCC) gegen Ende März 2021 eingeführt. Für die Government Community Cloud High (GCCH) und das Verteidigungsministerium (Department of Defense, DoD) wird dies zu einem späteren Zeitpunkt eingeführt. Sie müssen nach diesem Datum die Standardrichtlinie ändern, wenn Sie möchten, dass das Feature standardmäßig AKTIVIERT ist. Verwenden Sie PowerShell, um die Richtlinie `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` zu aktivieren.

> [!Note]
> Wenn Ihre Besprechung oder Ihr Webinar die Kapazitätsgrenze erreicht, wird Teams nahtlos skaliert, um eine schreibgeschützte Übertragungserfahrung für 10 000 Personen zu ermöglichen. Außerdem können Sie in dieser Zeit der vermehrten Remotearbeit bis zum Ende des Jahres von noch größeren Übertragungen für 20 000 Personen profitieren.

Microsoft Teams ermöglicht bis zu 10 000 Teilnehmern den Beitritt zu einer Teams-Besprechung. Nachdem die Kapazität der Hauptsitzung erreicht wurde (d. h., wenn 300 Benutzer an einer Besprechung teilnehmen), nehmen weitere Teilnehmer mit einer Nur-Ansicht-Erfahrung teil.

Teilnehmer, die zuerst an der Besprechung teilnehmen, erhalten bis zur Kapazität der Hauptbesprechung die vollständige Besprechungserfahrung von Teams. Sie können Audio und Video freigeben, freigegebene Videos ansehen und im Besprechungschat mitmachen.

Teilnehmer, die der Besprechung nach Erreichen der Kapazitätsgrenze beitreten, werden eine schreibgeschützte Erfahrung erhalten.

Teilnehmer können über Desktop, Web und Teams Mobile (Android und iOS) an der Ansichtserfahrung teilnehmen.

> [!Note]
> Die aktuelle Kapazitätsbeschränkung für die "Hauptsitzung", d. h. die Anzahl der vollständig interaktiven Benutzer, beträgt 300.

## <a name="teams-view-only-experience-controls"></a>Steuerelemente für die Ansichtserfahrung von Teams

Sie aktivieren die Ansichtserfahrung mit PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Zum Deaktivieren der Ansichtserfahrung können Sie auch PowerShell verwenden.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In Zukunft können Sie die Ansichtserfahrung im Teams Admin Center aktivieren oder deaktivieren.

## <a name="impact-to-users"></a>Auswirkungen auf die Benutzer

Die Erfahrung eines Benutzers wird von mehreren Faktoren abhängen.

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht ist, kann ein Teilnehmer der Besprechung nicht beitreten, wenn einer der folgenden Punkte zutrifft:

- Ein Administrator hat die Ansichtserfahrung nur für Teams für den Organisator oder für den gesamten Mandanten deaktiviert.
- Der Nur-Ansicht-Teilnehmer kann den Wartebereich nicht umgehen. Wenn beispielsweise ein Organisator einer Besprechung entscheidet, dass nur Personen **in** meiner Organisation den Wartebereich umgehen und ein Teilnehmer, der sich außerhalb der Organisation befindet, versucht, als Nur-Ansicht-Teilnehmer teilnehmen zu können, kann er nicht teilnehmen.

Wenn die Kapazität der Hauptsitzung erreicht ist, sehen der Besprechungsorganisator und die Organisatorin ein Banner, in dem sie darüber informiert werden, dass neue Teilnehmer als Nur-Ansicht-Teilnehmer beitreten werden.

  ![die Teams-Client- und Banner-Nachricht für Organisatoren und Referenten](media/chat-and-banner-message.png)

Wenn die Kapazitätsgrenze der Hauptbesprechung erreicht wurde, werden Besprechungsteilnehmer auf dem Bildschirm vor dem Beitritt informiert, dass sie im schreibgeschützten Modus beitreten werden.

  ![der Teams-Bildschirm vor dem Beitritt und die Nachricht für Teilnehmer, welche diese über den Beitritt im schreibgeschützten Modus informiert](media/view-only-pre-join-screen.png)

Solange es Platz hat, wird ein Benutzer immer der Hauptbesprechung beitreten. Wenn die Hauptbesprechung die Kapazitätsgrenze erreicht und einer oder mehrere Teilnehmer die Hauptbesprechung verlassen, dann hat die Hauptbesprechung wieder verfügbare Kapazität. Teilnehmer, die der Besprechung beitreten (oder wieder beitreten), werden der Hauptbesprechung beitreten, bis diese die Kapazitätsgrenze wieder erreicht. Teilnehmer, die die Ansichtserfahrung haben, werden nicht automatisch zur Hauptsitzung heraufgestuft und können nicht manuell zur Hauptsitzung heraufgestuft werden.

Wenn Presenter- und Teilnehmerrollen festgelegt wurden und ein Presenter versucht, an einer Besprechung zu teilnehmen, nachdem die Kapazität der Hauptbesprechung erreicht wurde, tritt er als Nur-Ansicht-Teilnehmer an und hat dieselben Einschränkungen wie andere Nur-Ansicht-Teilnehmer. Unterstützung, um sicherzustellen, dass alle Presenter an der Hauptsitzung teilnehmen, werden zu einem späteren Zeitpunkt durchgeführt. Der Organisator hat immer platzgarantierte Platz in der Hauptsitzung.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Auswirkungen auf Organisatoren und Besprechungsorganisatoren

Zu den Einschränkungen für Besprechungsorganisatoren und -organisatoren gehören:

- Sie werden keine Informationen über schreibgeschützte Teilnehmer haben. Wir unterstützten EDiscovery für schreibgeschützte Teilnehmer nicht.
- Die Benutzer in der Haupt besprechung können die Nur-Ansicht-Teilnehmer nicht sehen.
- Sie können keine schreibgeschützten Teilnehmer aus der Besprechung entfernen.

> [!Note]
> Die Teilnehmeranzahl gibt nur die Personen in der Hauptsitzung und nicht die Personen im Nur-Ansicht-Raum wieder. Deshalb erhalten Referenten keine genaue Anzahl der Personen in der schreibgeschützten Erfahrung.

## <a name="experience-for-view-only-attendees"></a>Erfahrung für schreibgeschützte Teilnehmer

Die schreibgeschützte Teams-Erfahrung erlaubt Teilnehmern Folgendes:

- Sie können den Teilnehmern in der Teams-Hauptbesprechung zuhören.
- Sie können den Video-Feed für aktive Sprecher sehen (wenn der aktive Sprecher Videos teilt).
- Anzeigen von Inhalten, die mithilfe der Desktop- oder Bildschirmfunktion für die Freigabe freigegeben werden.

Die folgenden Optionen in Besprechungen stehen den schreibgeschützten Teilnehmern nicht zur Verfügung:

- Sie können der Besprechung nicht beitreten, wenn der Teilnehmer basierend auf festgelegten Wartebereichsrichtlinien oder -Optionen die Berechtigung zum Umgehen des Wartebereichs nicht hat.
- Sie können dem schreibgeschützten Raum nicht mittels Audiokonferenz beitreten.
- Treten Sie dem Nur-Ansichtsraum mit microsoft Teams Rooms-System oder cloud video interop (CVI)-Diensten bei.
- Sie können ihr Audio oder Video nicht teilen.
- Sie können den Besprechungschat nicht sehen und nicht daran teilnehmen.
- Sie können den Video-Feed von Besprechungsteilnehmern nicht sehen, sofern der Teilnehmer nicht der aktive Sprecher ist.
- Weitere Informationen finden Sie unter PowerPoint-Dateien, die mithilfe der PowerPoint Live-Funktionalität oder einzelner Anwendungsfreigaben (mit anderen Als Desktop- oder Bildschirmfreigaben) freigegeben werden.
- Heben Sie ihre Hand in der Besprechung.
- Senden oder Sehen von Reaktionen.
- Interagieren Sie mit einer beliebigen 3P-App, die in die Teams-Besprechung integriert ist, einschließlich Umfragen.

## <a name="view-only-feature-limitations"></a>Schreibgeschützte Feature-Einschränkungen

- Nur Teilnehmer, die nur anzeigen können, können Liveuntertitel nur auf dem Desktop und im Web anzeigen. Derzeit werden nur englische Untertitel unterstützt. 
- Schreibgeschützte Teilnehmer werden durch Streaming-Technologie unterstützt.
- Schreibgeschützte Teilnehmer werden im Anwesenheitsbericht nicht eingeschlossen.
- Schreibgeschützte Teilnehmer werden eine einzelne Videoerfahrung haben. Sie können entweder den aktiven Sprecher sehen, oder den freigegebenen Inhalt, aber nicht beides.
- Derzeit unterstützen wir die Layouts **Galerie**. **Große Galerie** oder **Zusammen-Modus** für schreibgeschützte Teilnehmer nicht.  
- Schreibgeschützte Teilnehmer werden nicht die gleiche Latenzzeit haben wir normale Teilnehmer. <sup>1</sup>

  <sup>1</sup> Schreibgeschützte Teilnehmer werden in der Besprechung eine Verzögerung von 30 Sekunden für Video und Audio haben.  
