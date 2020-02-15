---
title: FAQ für lync Server 2013 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9de9555f9f009558b700a32ca6e58059eb5ea990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>FAQ für lync Server 2013 Stress and Performance Tool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

Hier finden Sie einige häufig gestellte Fragen zum lync Server 2013 Stress-und Leistungs Tool.

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>Kann ich LyncPerfTool. exe in Production ausführen?

Dies wird nicht empfohlen. Dieses Tool wirkt sich auf die Serverleistung, die Sicherheit und die Benutzerfreundlichkeit aus.

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>Ich werde meine Benutzer zum ersten Mal anmelden. Warum werden die Server mit einer derart hohen Auslastung betrieben?

Wenn sich die Benutzer zum ersten Mal anmelden, treten zusätzliche Vorgänge auf. Dadurch wird die Leistung auf dem Microsoft SQL Server Back-End-Server beeinträchtigt. Es wird empfohlen, dass Sie einen kurzen Test ausführen, der sich auf alle Benutzer anmeldet, und die Clients dann neu starten, bevor Sie Ergebnisse messen. Es werden nicht mehr als 12 gleichzeitige Benutzeranmeldesitzungen pro Sekunde unterstützt, dies hängt jedoch von Ihrer Hardwarekonfiguration ab.

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>Meine Clients haben keinen Arbeitsspeicher mehr. Was soll ich machen?

Wenn auf Ihren Clients kein Arbeitsspeicher mehr vorhanden ist, müssen Sie die Anzahl der Benutzer pro Computer reduzieren.

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>Meine Clients befinden sich immer bei 100 Prozent CPU. Was soll ich machen?

Wenn Ihre Clients mit einer sehr hohen CPU-Leistung betrieben werden, nachdem sich alle Benutzer angemeldet haben, müssen Sie die Anzahl der Benutzer pro Computer reduzieren. Hohe CPU-Spitzen sind akzeptabel, wenn Sie jedoch aufrecht erhalten werden, müssen Sie die Last reduzieren.

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>Kann ich das Tool auf dem Server selbst ausführen?

Nein. Dieses Szenario wird nicht unterstützt und kann aufgrund eines binären Konflikts fehlschlagen. Da es sich dabei um die Messung des Ressourcenverbrauchs auf dem Server handelt, würde das Tool dort durchführen, sodass die Messungen bedeutungslos wären.

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>Kann ich LyncPerfTool. exe auf einem virtuellen Server oder auf Microsoft Hyper-V Server 2008/2012 ausführen?

Ja.

</div>

<div>

## <a name="what-does-mpop-mean"></a>Was bedeutet mpop?

MPOP steht für mehrere Points of Presence. Es soll das Szenario simulieren, in dem Benutzer bei lync 2013 von mehreren Computern angemeldet sind. Beachten Sie, dass in LyncPerfTool. exe jeder Endpunkt das Standardprofil verwendet (das Profil wird also nicht zwischen den beiden Points of Presence geteilt).

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>Ich habe LyncPerfTool. exe gestartet, aber nichts geschieht. Was ist denn nun los?

Überprüfen Sie den Indikator Gesamtanzahl aktiver Endpunkte für die Clients, um zu sehen, ob die Benutzer eine Verbindung herstellen. Wenn Benutzer keine Verbindung herstellen, überprüfen Sie die lync Server 2013 Konfiguration. Dieses Problem tritt in der Regel auf, weil der Servername, das Benutzerpräfix oder das Kennwort falsch ist. Beachten Sie, dass externe Clients den Zugriffs Proxy als TargetServer-Wert angeben sollten. Überprüfen Sie den Port in der Konfigurationsdatei.

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>Woher weiß ich, dass etwas passiert?

Die verschiedenen LyncPerfTool-Leistungsindikatoren geben an, ob Benutzer eine Verbindung herstellen und Aktionen ausführen. Eine einfache Möglichkeit zum Überprüfen besteht jedoch darin, sich mit lync 2013 bei einem der Konten anzumelden und die gewünschte Aktion auszuführen.

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Ich habe Live Communications Server Tools zur Kapazitätsplanung für 2007 R2 und/oder lync Server 2010 installiert. Ist das in Ordnung?

Nein. Es gibt Interoperabilitätsprobleme, und Sie müssen alle Vorgängerversionen dieses Produkts deinstallieren.

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Werden mit den Stress-und Leistungstools die CAA-Topologie für Anruf Informationsserver eingerichtet?

Nein. Die Tools erstellen nur Benutzer, Kontakte und Verteilerlisten und simulieren die Benutzerlast.

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>Wie hoch ist die maximale Anzahl von Benutzern, die von den Tools unterstützt werden?

Mit diesen Tools haben wir insgesamt 80.000-Benutzer erstellt und Tests von insgesamt 30.000 Benutzern ausgeführt. Es werden maximal 120.000 Benutzer vorgeschlagen, wobei die technischen Einschränkungen je nach verfügbarer Client-und Server Hardware einen höheren Wert ermöglichen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

