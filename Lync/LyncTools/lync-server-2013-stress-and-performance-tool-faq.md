---
title: Häufig gestellte Fragen zu lync Server 2013 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Häufig gestellte Fragen zu lync Server 2013 Stress and Performance Tool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Hier finden Sie einige häufig gestellte Fragen zum lync Server 2013-Tool Stress und Leistung.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool. exe in Production ausführen?

Wir empfehlen dies nicht. Dieses Tool hat Auswirkungen auf die Serverleistung, Sicherheit und Benutzerfreundlichkeit.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Ich habe mich zum ersten Mal bei meinen Benutzern angemeldet. Warum werden die Server mit einer derart großen Auslastung ausgeführt?

Wenn sich die Benutzer zum ersten Mal anmelden, werden weitere Vorgänge ausgeführt. Dadurch wird die Leistung auf dem Microsoft SQL Server-Back-End-Server beeinträchtigt. Wir empfehlen, dass Sie einen kurzen Test ausführen, bei dem alle Benutzer angemeldet sind, und dann die Clients neu starten, bevor Sie Ergebnisse messen. Wir unterstützen nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde, dies hängt aber von Ihrer Hardwarekonfiguration ab.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Für meine Clients ist der Arbeitsspeicher knapp. Was soll ich tun?

Wenn auf Ihren Clients der Arbeitsspeicher knapp wird, müssen Sie die Anzahl der Benutzer pro Computer verringern.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Meine Clients sind immer mit einer CPU von 100 Prozent. Was soll ich tun?

Wenn Ihre Clients mit einer sehr großen CPU ausgeführt werden, nachdem sich alle Benutzer angemeldet haben, müssen Sie die Anzahl der Benutzer pro Computer reduzieren. Hohe CPU-Spitzen sind akzeptabel, aber wenn Sie unterstützt werden, müssen Sie die Auslastung reduzieren.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>Kann ich das Tool auf dem Server selbst ausführen?

Nummer Dieses Szenario wird nicht unterstützt und kann aufgrund eines binären Konflikts fehlschlagen. Da der Punkt darin besteht, den Ressourcenverbrauch auf dem Server zu messen, würde das Ausführen des Tools die Maße bedeutungslos machen.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool. exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?

Ja.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Was bedeutet mpop?

MPOP steht für mehrere Anwesenheits Punkte. Damit soll das Szenario simuliert werden, in dem Benutzer von mehreren Computern bei lync 2013 angemeldet sind. Beachten Sie, dass in LyncPerfTool. exe jeder Endpunkt das Standardprofil verwendet (das Profil wird jedoch nicht zwischen den beiden Anwesenheits Punkten aufgeteilt).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich habe LyncPerfTool. exe gestartet, aber es geschieht nichts. Was ist los?

Überprüfen Sie den Indikator Gesamtzahl aktiver Endpunkte auf den Clients, um festzustellen, ob die Benutzer eine Verbindung herstellen. Wenn Benutzer keine Verbindung herstellen, überprüfen Sie Ihre lync Server 2013-Konfiguration. Dieses Problem tritt in der Regel auf, weil der Servername, das Benutzerpräfix oder das Kennwort falsch ist. Beachten Sie, dass externe Clients den Zugriffs Proxy als TargetServer-Wert angeben sollten. Überprüfen Sie den Port in der Konfigurationsdatei.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Woran erkenne ich, dass etwas passiert?

Die verschiedenen LyncPerfTool-Leistungsindikatoren geben an, ob Benutzer eine Verbindung herstellen und Aktionen ausführen. Eine einfache Möglichkeit zur Überprüfung besteht jedoch darin, sich mit lync 2013 bei einem der Konten anzumelden und die gewünschte Aktion durchzuführen.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Ich habe Live Communications Server 2007 R2-Kapazitäts Planungs Tools und/oder lync Server 2010 installiert. Ist das in Ordnung?

Nummer Es gibt Interoperabilitätsprobleme, und Sie müssen alle vorherigen Versionen dieses Produkts deinstallieren.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Werden die Stress-und Leistungstools die CAA-Anruf Informationsserver-Topologie einrichten?

Nummer Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten und simulieren die Benutzerauslastung.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Was ist die maximale Anzahl von Benutzern, die von den Tools unterstützt werden?

Wir haben bis zu insgesamt 80.000-Benutzer erstellt und Tests mit insgesamt 30.000 Benutzern durchgeführt, die diese Tools verwenden. Wir empfehlen maximal 120.000-Benutzer, auch wenn die technischen Einschränkungen je nach verfügbarer Client-und Server Hardware einen höheren Wert zulassen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

