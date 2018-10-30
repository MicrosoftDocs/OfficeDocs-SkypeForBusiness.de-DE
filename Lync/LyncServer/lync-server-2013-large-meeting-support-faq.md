---
title: Lync Server 2013-Unterstützung für große Besprechungen – Häufig gestellte Fragen
TOCTitle: Lync Server 2013-Unterstützung für große Besprechungen – Häufig gestellte Fragen
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204804(v=OCS.15)
ms:contentKeyID: 49293636
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013-Unterstützung für große Besprechungen – Häufig gestellte Fragen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Die folgenden Abschnitte enthalten Antworten auf häufige Fragen zum Erstellen und Ausführen großer Besprechungen.

## Frage: Wie viele Benutzer können an einer großen Besprechung teilnehmen?

Für das Lync Server-Benutzermodell sind Grenzwerte angegeben, und zwar 250 Benutzer in einem freigegebenen Pool bzw. 1000 Benutzer in einem dedizierten Pool, der speziell für große Besprechungen vorgesehen ist. Diese Zahlen entsprechen jedoch nur der Anzahl von Benutzern bei unseren Tests, die mit einem bestimmten Satz von Hardware durchgeführt wurden. Basierend auf den Testergebnissen empfehlen wir diese Grenzwerte für maximale Größen. Sie können für Ihre Organisation jedoch die tatsächliche Anzahl der in Besprechungen zulässigen Teilnehmer steuern, indem Sie eine oder mehrere Konferenzrichtlinien konfigurieren (diese können Sie mit Windows PowerShell-Cmdlets in der Lync Server-Verwaltungsshell oder über die Lync Server-Systemsteuerung konfigurieren). Die Anzahl, die Sie in der Richtlinie angeben, kann eine beliebige 32-Bit-Ganzzahl zwischen 1 und 4.294.967.295 sein, aber empfohlen wird eine Größe zwischen einschließlich 2 und 250 Teilnehmern. Der Standardwert ist 250.

## Frage: Wie viele Besprechungen oder andere Arbeitsauslastungen sind für einen dedizierten Pool für große Besprechungen zulässig?

Um bei großen Besprechungen mit bis zu 1000 Teilnehmern die beste Benutzererfahrung zu erzielen, wird empfohlen, in einem dedizierten Pool für große Besprechungen jeweils immer nur eine große Besprechung zu hosten. Zudem wird empfohlen, keine anderen Arbeitsauslastungen im Pool auszuführen, während eine große Besprechung stattfindet.

## Frage: Sollten die Organisatoren großer Besprechungen auf dem dedizierten Pool verwaltet werden?

Nein. Es wird empfohlen, auf dem dedizierten Pool nur die Mitarbeiter zu verwalten, die für die Planung großer Besprechungen verantwortlich sind, und keine anderen Benutzer. Hierdurch wird verhindert, dass anderer Datenverkehr aus Echtzeitkommunikationen zu Problemen bei großen Besprechungen führt, die im Pool gehostet werden. Große Besprechungen im dedizierten Pool sollten mit einem Benutzerkonto geplant werden, das dem für die Planung großer Besprechungen zuständigen Personal zugewiesen ist. Sie sollten das Benutzerkonto des Besprechungsorganisators (der Benutzer, der eine große Besprechung anfordert) als Referenten für die große Besprechung hinzufügen.

## Frage: Welche Medienmodalitäten können in einer großen Besprechung verwendet werden?

Große Besprechungen mit bis zu 1000 Benutzern können Audio, Video, PowerPoint-Freigabe, Whiteboards und den Abruf von Anwesenheitsinformationen umfassen.

## Frage: Kann ich in großen Besprechungen einen Gruppenchat verwenden?

Ja. Jedoch kann eine große Anzahl von Chatnachrichten, insbesondere wenn diese von sehr vielen Besprechungsteilnehmern gesendet werden, die Benutzerfreundlichkeit beeinträchtigen, da es Probleme mit dem schnellen Textbildlauf im Chatfester geben kann. Durch das Senden einer großen Anzahl von Chatnachrichten an bis zu 1000 Benutzer kann zudem eine beträchtliche Serverlast entstehen, die zu einer Leistungsbeeinträchtigung führen kann. Im Allgemeinen ist die Chatfunktion nur für Fragen und Antworten erforderlich.

## Können Benutzer an einer großen Besprechung teilnehmen, indem sie sich über ein Telefon einwählen?

Ja. Wenn der Lync Server 2013-Pool ordnungsgemäß bereitgestellt und für die Einwahlkonferenz aktiviert ist, können sich Benutzer per Telefon in eine große Besprechung einwählen. Unsere Tests haben ergeben, dass sich in einem Zeitraum von 10 Minuten bis zu 15 % der 1000 Benutzer einwählen konnten.

## Frage: Kann ich große Topologien in einer virtuellen Topologie hosten?

Wir haben keine großen Besprechungen in einer virtuellen Topologie gehostet. Daher wird die Verwendung virtueller Computer zum Hosten eines dedizierten Pools für große Besprechungen nicht unterstützt.

