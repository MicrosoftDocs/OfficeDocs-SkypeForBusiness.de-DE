---
title: Lync Server 2013-Kapazitäts planungsrechner
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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Verwenden des Kapazitäts Planungs Rechners für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-21_

Der Microsoft® lync™ Server 2013 <http://www.microsoft.com/en-us/download/details.aspx?id=36828>-Kapazitäts planungsrechner steht zum Download zur Verfügung. Es wurde entwickelt, um Ihnen bei der Ermittlung der Server Anforderungen zu helfen, die auf der Anzahl der Benutzer und Kommunikationsmodalitäten basieren, die in Ihrer Organisation aktiviert sind. Sie geben das Profil Ihrer Organisation ein, und der Rechner bietet Empfehlungen, die Ihnen bei der Planung Ihrer Topologie helfen.

Die vom Rechner erstellten Empfehlungen dienen nur zu Planungszwecken. Eine tatsächliche Auslastungssimulation ist erforderlich, um sicherzustellen, dass lync Server 2013 angemessen bereitgestellt wird. Verwenden Sie zum Ausführen von Belastungstests unter einer simulierten Belastung das [Stress-und Leistungs Tool lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Nachdem Sie Ihr Benutzerprofil und die Modalitäten festgelegt haben, die Sie für Ihre Benutzer aktivieren möchten, ist es an der Zeit, den Rechner zu verwenden, um die Anzahl der benötigten Server, Arbeitsspeicher und Bandbreite zu planen. Diese Version des Rechners bietet keine Anleitungen in Hinblick auf Datenträger-E/A-Anforderungen.

Dieser Rechner ergänzt den [Microsoft lync Server](http://go.microsoft.com/fwlink/?linkid=282725) und [Microsoft lync Server](lync-server-2013-planning.md). Verwenden Sie den Rechner, nachdem Sie die Anleitung gelesen und mithilfe des Planungstools eine empfohlene Topologie erstellt haben.

Den besten Nutzen erzielen Sie mit dem Rechner, wenn Sie genaue und ausführliche Informationen zu Ihrem speziellen Benutzerprofil haben. Beispielsweise können der Prozentsatz von VoIP-aktivierten Benutzern, der Durchschnitt der Anrufe pro Benutzer und Stunde, die Anrufdauer und der Prozentsatz von gleichzeitigen Benutzern in Konferenzen einen großen Unterschied hinsichtlich der Serveranforderungen ausmachen. Die Genauigkeit der Empfehlungen, die vom Rechner erstellt werden, hängt von der Genauigkeit der Informationen ab, die Sie bereitgestellt haben.

<div>

## <a name="using-the-capacity-calculator"></a>Arbeiten mit dem Kapazitätsrechner

Der Rechner ist eine Microsoft Excel®-Kalkulationstabelle. Orange farbige Zellen sind für die Eingabe von Ihnen. Es werden Standardwerte eingegeben (80.000-Benutzer in einem Pool mit zwölf Front-End-Servern), aber Sie können diese Werte entsprechend den Anforderungen Ihrer Organisation ändern.

Das Nutzungsmodell enthält die folgenden Abschnitte. Um Ihre Kapazitätsanforderungen zu berechnen, geben Sie Daten wie beschrieben ein:

**Chat und Anwesenheit**

  - Geben Sie unter Anzahl der Benutzer die Anzahl der Benutzer ein, die gleichzeitig angemeldet sein sollen. Diese Anzahl entspricht meist 80 % der Gesamtzahl der bereitgestellten Nutzer. In den meisten Situationen werden 100 % der gleichzeitigen Nutzer für Chat und Anwesenheit aktiviert. Der Standardwert ist 80.000.

  - Durchschnittliche Anzahl von Kontakten in der Kontaktliste gibt die Anzahl von Kontakten an, die zur Überprüfung Ihrer Systemanforderungen verwendet wird. Diese Nummer kann nicht geändert werden.

**Enterprise-VoIP**

  - Geben Sie in für Enterprise-VoIP aktivierte Benutzer den Prozentsatz der Benutzer ein, die für Enterprise-VoIP aktiviert sind. Der Standardwert ist 60 %.

  - Geben Sie in durchschnittliche Anzahl der Anrufe pro Benutzer pro Stunde (Peak) die Anzahl der Anrufe pro Stunde ein, an denen der durchschnittliche Benutzer in Zeiten der Spitzenlast teilnehmen soll. Der Standardwert ist 4.

  - Geben Sie in Prozentsatz der Anrufe, die Medienumgehung nutzen den Prozentsatz der Anrufe ein, die von Ihren Nutzern getätigt, aber nicht über den Vermittlungsserver abgewickelt werden. Der Standardwert ist 65%.

  - Geben Sie in Prozentsatz der VoIP-Nutzer, die an UC-PSTN-Anrufen beteiligt sind den Prozentsatz der Anrufe in Ihrer Organisation ein, die Anrufe über das UC-Telefonfestnetz (UC-PSTN) sind. Der Standardwert ist 60%.

  - In Prozent der Sprachbenutzer, die an UC-UC-anrufen beteiligt sind, wird der Prozentsatz der Benutzer angezeigt, die für Enterprise-VoIP aktiviert sind und nur für UC-UC-Anrufe aktiviert werden. Diese Anzahl wird auf Basis des Werts berechnet, den Sie in Prozentsatz der VoIP-Nutzer, die an UC-PSTN-Anrufen beteiligt sind eingegeben haben.

**Konferenzen**

  - Geben Sie in Prozent der Benutzer in parallelen Konferenzen den Prozentsatz der Benutzer ein, die gleichzeitig an Konferenzen teilnehmen werden. Der Standardwert ist 5 %.

  - Geben Sie in Prozent der Konferenzen mit nur Gruppen-Chat (keine Stimme) den Prozentsatz der Konferenzen ein, deren Konferenzen nur Chatnachrichten einbeziehen sollen. Das bedeutet, dass keine Audiokomponente enthalten ist. Der Standardwert ist 10%.

  - Geben Sie in Prozent der Benutzer, die Einwahlkonferenzen verwenden, den Prozentsatz der gleichzeitigen Teilnehmer in Konferenzen ein, die Einwahlkonferenzen verwenden werden. Der Standardwert ist 15 %.

  - Geben Sie in Prozent der Konferenzen, die Voice verwenden, den Prozentsatz der Konferenzen ein, die eine Audio-Komponente enthalten sollen.
    
      - Wenn 20 % Ihrer VoIP-Konferenzen auch normale Videoelemente umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Video (kein Multiview).
    
      - Wenn 20 % Ihrer Konferenzen auch Multiview-Videoelemente umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Multiview.
    
      - Wenn 50 % Ihrer VoIP-Konferenzen auch Anwendungsfreigabe umfassen, aktivieren Sie das Kontrollkästchen Einschließlich Anwendungsfreigabe.
    
      - Wenn 20% ihrer Sprachkonferenzen Datenuploads wie Microsoft PowerPoint-® Präsentationen einschließen, aktivieren Sie das Kontrollkästchen einschließlich Webkonferenzen.

**Mobilität**

  - Geben Sie in Prozent der Benutzer, die für Mobilität aktiviert sind, den Prozentsatz der Benutzer ein, die für die Verbindung zu lync Server mithilfe mobiler Geräte aktiviert werden sollen. Der Standardwert ist 40 %.

Wenn Sie alle erforderlichen Informationen eingegeben haben, schätzt der Kapazitäts Rechner Ihre Anforderungen. Die gelben Zellen zeigen berechnete Werte für CPU-, Arbeitsspeicher-und Bandbreitenanforderungen basierend auf Tests an, die in lync Server 2013 Performance Labs ausgeführt werden. Die Zahlen werden als Richtlinie bereitgestellt, nicht jede einzelne Variation wird getestet und validiert. Die folgenden Werte werden berechnet:

  - Front-End-CPU: Prozentsatz der CPU-Auslastung, wenn der gesamte Ladevorgang von einem Front-End-Server mit den gleichen Spezifikationen wie der in Microsoft-Tests verwendete Server gehandhabt wurde.

  - Netzwerk in MBit/s: Bandbreitenanforderungen in Megabit pro Sekunde (MBit/s) für die entsprechende Arbeitsauslastung.

  - Arbeitsspeicher in GB: Arbeitsspeicher in Gigabyte (GB), der für die entsprechende Arbeitsauslastung erforderlich ist.

In den grünen Zellen werden Empfehlungen für das Nutzungsmodell angezeigt, das Sie eingegeben haben.

  - Gesamtzahl der Front-End-Server: die Anzahl der erforderlichen physikalischen Server basiert auf dedizierten Servern mit lync Server 2013 mit Dualprozessor, Hex-Core und 2.260 Megazyklen.

  - Es wird empfohlen, Hyperthreading zu aktivieren, denn damit lässt sich nachweislich die Leistung von Servern verbessern, die Audio/Video unterstützen.

  - Edgeserver: die Anzahl der erforderlichen Edgeserver, basierend auf 30% aller gleichzeitigen Benutzer, die über die Edgeserver kommunizieren. Dieser Prozentsatz kann im Rechner nicht geändert werden.

  - Speicher für die Dienste Archivierung/Aufzeichnung von Kommunikationsdatensätzen/Quality of Experience: Die Anzahl von Speichern, die für Archivierungs- oder Überwachungsfeatures erforderlich sind, sofern diese in Ihrer Organisation aktiviert sind.

  - Erforderliche Back-End-Datenbankserver (erforderliche Pools): Die Anzahl von Back-End-Datenbankservern, die erforderlich sind, damit die ausgewählte Auslastung unterstützt werden kann.

Die Zeile neben „Gesamtzahl der Front-End-Server“ enthält zusätzlich weitere Informationen zu der Last auf den Servern und im Netzwerk für alle geplanten Auslastungen zusammengenommen.

  - Durchschnittliche CPU-Auslastung: Die durchschnittliche CPU-Nutzung pro Front-End-Server.

  - Netzwerk in MBit/s: Die Bandbreitenzuteilung, die erforderlich ist, damit das von Ihnen eingegebene Nutzungsmodell unterstützt wird.

  - Arbeitsspeicher in GB: Der Arbeitsspeicher in Gigabyte, der für jeden Front-End-Server erforderlich ist.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Anpassen an Ihre Prozessoren

Für alle CPU-Nutzungswerte auf dem Arbeitsblatt wird angenommen, dass jeder Server einen Dualprozessor mit sechs Kernen und 2,26 GHz, mindestens 32 GB Arbeitsspeicher und mindestens 8 10.000-U/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz hat.

Wenn Ihre Server andere Prozessoren haben, können Sie die Werte entsprechend Ihrer Hardware anpassen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

