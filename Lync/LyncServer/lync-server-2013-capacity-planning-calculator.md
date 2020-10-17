---
title: Lync Server 2013 Kapazitäts planungsrechner
description: Lync Server 2013 Kapazitäts planungsrechner.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f78019c98cf280f38249ac52cd063cede5319af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565141"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Verwenden des Kapazitäts Planungs Rechners für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-21_

Der Rechner zur Kapazitätsplanung von Microsoft® lync™ Server 2013 steht zum Download zur Verfügung <https://www.microsoft.com/download/details.aspx?id=36828> . Es wurde entwickelt, um Sie bei der Ermittlung von Server Anforderungen basierend auf der Anzahl von Benutzern und Kommunikationsmodalitäten zu unterstützen, die in Ihrer Organisation aktiviert sind. Sie geben das Profil Ihrer Organisation ein, und der Rechner enthält Empfehlungen, die Sie bei der Planung Ihrer Topologie unterstützen.

Die vom Rechner erstellten Empfehlungen dienen nur zu Planungszwecken. Die tatsächliche Auslastungssimulation ist erforderlich, um sicherzustellen, dass lync Server 2013 angemessen bereitgestellt wird. Verwenden Sie zum Ausführen von Belastungstests unter simulierter Last das [Tool lync Server 2013 Stress and Performance](https://go.microsoft.com/fwlink/?linkid=282724).

Nachdem Sie Ihr Benutzerprofil und die Modalitäten festgelegt haben, die Sie für Ihre Benutzer aktivieren möchten, ist es an der Zeit, den Rechner zu verwenden, um die Anzahl der benötigten Server, Arbeitsspeicher und Bandbreite zu planen. Diese Version des Rechners bietet keine Anleitung für Datenträger-e/a-Anforderungen.

Dieser Rechner ergänzt die [Microsoft lync Server](https://go.microsoft.com/fwlink/?linkid=282725) und [Microsoft lync Server](lync-server-2013-planning.md). Verwenden Sie den Rechner, nachdem Sie das Handbuch überprüft und eine empfohlene Topologie mithilfe des Planungstools erstellt haben.

Sie können am meisten von dem Rechner profitieren, wenn Sie genaue, detaillierte Informationen zu Ihrem bestimmten Benutzerprofil haben. Beispielsweise kann der Prozentsatz an sprachaktivierten Benutzern, durchschnittliche Anrufe pro Benutzer und Stunde, Anrufdauer und der Prozentsatz gleichzeitiger Benutzer in Konferenzen einen großen Unterschied in den Server Anforderungen mit sich bringen. Die Genauigkeit der vom Rechner erstellten Empfehlungen hängt von der Genauigkeit der von Ihnen bereitgestellten Informationen ab.

<div>

## <a name="using-the-capacity-calculator"></a>Verwenden des Kapazitäts Rechners

Der Rechner ist eine Microsoft Excel® Kalkulationstabelle. Orange gefärbte Zellen werden von Ihnen eingegeben. Es werden Standardwerte eingegeben (80.000 Benutzer in einem Pool mit zwölf Front-End-Servern), Sie können diese Werte jedoch entsprechend den Anforderungen Ihrer Organisation ändern.

Das Nutzungsmodell enthält die folgenden Abschnitte. Geben Sie zum Berechnen der Kapazitätsanforderungen wie beschrieben Daten ein:

**Instant Messaging und Anwesenheit**

  - Geben Sie unter Anzahl der Benutzer die Anzahl der Benutzer ein, die gleichzeitig angemeldet sein sollen. Diese Nummer ist normalerweise 80% der Gesamtzahl der gestellten Benutzer. In den meisten Fällen sind 100% ihrer gleichzeitigen Benutzer für Sofortnachrichten und Anwesenheitsinformationen aktiviert. Der Standardwert ist 80.000.

  - Durchschnittliche Anzahl von Kontakten in der Kontaktliste gibt die Anzahl der Kontakte an, die für die Überprüfung der Systemanforderungen verwendet werden. Diese Nummer kann nicht geändert werden.

**Enterprise-VoIP**

  - Geben Sie unter für Enterprise-VoIP aktivierte Benutzer den Prozentsatz der Benutzer ein, die für Enterprise-VoIP aktiviert sind. Der Standardwert ist 60%.

  - Geben Sie im Durchschnitt Anzahl der Anrufe pro Benutzer pro Stunde (Spitzenwert) die Anzahl der Anrufe pro Stunde ein, die der durchschnittliche Benutzer in Zeiten der Spitzenauslastung an der Teilnahme erwartet. Der Standardwert ist 4.

  - Geben Sie in Prozentsatz der Anrufe, die die medienumgehung verwenden, den Prozentsatz der Anrufe ein, die von Ihren Benutzern getätigt werden und die Vermittlungsserver umgehen. Der Standardwert ist 65%.

  - Geben Sie in Prozentsatz der VoIP-Benutzer, die an UC-PSTN-anrufen beteiligt sind, den Prozentsatz der Anrufe Ihrer Organisation ein, bei denen es sich um UC-PSTN-Telefonanrufe handelt. Der Standardwert ist 60%

  - In Prozentsatz der an UC-UC-Anrufe beteiligten Sprachbenutzer zeigt den Prozentsatz der Benutzer an, die für Enterprise-VoIP aktiviert sind und nur für UC-UC-Anrufe aktiviert werden. Diese Nummer wird basierend auf den Angaben berechnet, die Sie für den Prozentsatz der für UC-PSTN-Anrufe aktivierten VoIP-Benutzer eingegeben haben.

**Konferenzen**

  - Geben Sie in Prozentsatz der Benutzer in gleichzeitigen Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden. Der Standardwert ist 5%.

  - Geben Sie in Prozentsatz der Konferenzen mit nur Gruppen-Chat (keine Stimme) den Prozentsatz der Konferenzen ein, deren Konferenzen nur Chatnachrichten umfassen sollen. Das bedeutet, dass keine Audio-Komponente enthalten ist. Der Standardwert ist 10%

  - Geben Sie in Prozentsatz der Benutzer, die Einwahlkonferenzen verwenden, den Prozentsatz der gleichzeitigen Teilnehmer an Konferenzen ein, die Einwahlkonferenzen verwenden sollen. Der Standardwert ist 15%.

  - Geben Sie in Prozentsatz der Konferenzen, die Voice verwenden, den Prozentsatz der Konferenzen ein, die eine Audio-Komponente enthalten sollen.
    
      - Wenn 20% Ihrer VoIP-Konferenzen auch reguläre Videos enthalten, aktivieren Sie das Kontrollkästchen einschließlich Video (keine Mehrfachansicht).
    
      - Wenn 20% ihrer Konferenzen auch Multi-View-Video enthalten, aktivieren Sie das Kontrollkästchen einschließlich Multiview-Ansicht.
    
      - Wenn 50% Ihrer VoIP-Konferenzen auch die Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen einschließlich Anwendungsfreigabe.
    
      - Wenn 20% Ihrer VoIP-Konferenzen Datenuploads umfassen, beispielsweise Microsoft PowerPoint® Präsentationen, aktivieren Sie das Kontrollkästchen einschließlich Webkonferenzen.

**Mobilität**

  - Geben Sie in Prozentsatz der für Mobilität aktivierten Benutzer den Prozentsatz der Benutzer ein, die zum Herstellen einer Verbindung mit lync Server über mobile Geräte aktiviert werden sollen. Der Standardwert ist 40%.

Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests an, die in lync Server 2013 Performance Labs ausgeführt werden. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert. Die folgenden Werte werden berechnet:

  - Front-End-CPU: Prozentsatz der CPU-Auslastung, wenn die gesamte Last von einem Front-End-Server der gleichen Spezifikationen wie der Server, der in Microsoft Tests verwendet wurde, verarbeitet wurde.

  - Netzwerk in Mbit/s: Bandbreitenanforderungen in Megabit pro Sekunde (Mbit/s) für die entsprechende Arbeitsauslastung.

  - Arbeitsspeicher in GB: erforderlicher Arbeitsspeicher in Gigabyte (GB) für die entsprechende Arbeitsauslastung.

Die grünen Zellen zeigen Empfehlungen für das von Ihnen eingegebene Nutzungsmodell an.

  - Gesamtzahl der Front-End-Server: die erforderliche Anzahl physischer Server basiert auf dedizierten Servern, auf denen lync Server 2013 mit Dualprozessor, Hex-Kern, mit 2.260 Megazyklen.

  - Beachten Sie, dass die Aktivierung von Hyperthreading empfohlen wird und dass die Leistung für Server verbessert wurde, die Audio/Video unterstützen.

  - Edgeserver: die Anzahl der erforderlichen Edgeserver, basierend auf 30% aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden.

  - Archivierung/Anruf Detail Aufzeichnung/Quality of Experience Services Store: die Anzahl der Speicher, die für Archivierungs-oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.

  - Back-End-Datenbankserver erforderlich (erforderliche Pools): die Anzahl der Back-End-Datenbankserver, die zur Unterstützung der ausgewählten Arbeitsauslastung erforderlich sind.

Darüber hinaus werden in der Zeile neben Gesamt-Front-End-Server Weitere Informationen zur Last auf den Servern und im Netzwerk für alle geplanten Arbeitslasten bereitgestellt.

  - Durchschnittliche CPU-Auslastung: die durchschnittliche CPU-Auslastung pro Front-End-Server.

  - Netzwerk in Mbit/s: die erforderliche Bandbreitenzuweisung zur Unterstützung des von Ihnen eingegebenen Nutzungs Modells.

  - Arbeitsspeicher in GB: Arbeitsspeicher in Gigabyte, erforderlich für jeden Front-End-Server.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Berechnen der Leistungskennzahlen für Ihre Prozessoren

Bei allen CPU-Nutzungszahlen in der Tabelle wird davon ausgegangen, dass jeder Server über einen Dualprozessor, einen Hex-Kern mit 2,26 GHz, mindestens 32 GB Arbeitsspeicher sowie 8 oder mehr Festplatten mit 10.000-RPM mit mindestens 72 GB freiem Speicherplatz verfügt.

Wenn Ihre Server unterschiedliche Prozessoren haben, können Sie die Zahlen so anpassen, dass Sie mit Ihrer Hardware übereinstimmen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

