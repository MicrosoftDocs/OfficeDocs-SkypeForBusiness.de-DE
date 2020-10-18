---
title: 'Lync Server 2013: Installieren der lync Server 2013 Management Packs'
description: 'Lync Server 2013: Installieren der lync Server 2013 Management Packs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573831"
---
# <a name="installing-the-lync-server-2013-management-packs"></a>Installieren der lync Server 2013 Management Packs

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

System Center Operations Manager kann nur einen kleinen Teil des Windows-Betriebssystems überwachen. Sie können die Funktionen von System Center Operations Manager jedoch erweitern, indem Sie Management Packs installieren, Software, die bestimmt, welche Elemente von System Center Operations Manager überwacht werden können, einschließlich der Art und Weise, wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst und gemeldet werden sollen. Microsoft lync Server 2013 enthält zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:

  - Das Component and User Management Pack (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync Server Probleme, die in Ereignisprotokollen aufgezeichnet werden, die von Leistungsindikatoren registriert wurden oder in den Datensätzen "Call Detail Records" (KDS) oder QoE (Quality of Experience) protokolliert wurden. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Chatnachrichten oder SMS-Messaging benachrichtigt werden. SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.
    
    <div>
    

    > [!NOTE]  
    > Weitere Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter Konfigurieren der Benachrichtigung in der TechNet-Bibliothek unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> .

    
    </div>

  - Das Active Monitoring Pack (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet die Schlüssel lync Server Komponenten proaktiv, beispielsweise die Anmeldung am System, den Austausch von Chatnachrichten oder das tätigen von Anrufen an ein Telefon im öffentlichen Telefonnetz (PSTN). Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen lync Server ausgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.

Die beiden in lync Server 2013 enthaltenen Management Packs umfassen eine große Anzahl von Verbesserungen hinsichtlich der mit Microsoft lync Server 2010 verwendeten Management Packs. Beispielsweise ist das Management Pack für die lync Server 2013-Komponente nicht auf die Überwachung lync Server selbstlimitiert. Zusätzlich zur Überwachung von Ereignisprotokollen und Leistungsindikatoren für lync Server kann das Component Management Pack auch die Leistung von und Warnungen für wichtige Elemente wie die folgenden ermitteln:

  - **Internet Information Services (IIS)**     Warnungen werden ausgegeben, wenn Internet Informationsdienste offline geschaltet werden. Dies ist wichtig, da die lync Server-Webdienste von IIS abhängig sind.

  - **Prozess Verwendung**     Warnungen werden ausgegeben, wenn Systemressourcen (wie zum Beispiel verfügbarer Arbeitsspeicher) langsam gestartet werden. Diese Warnungen werden auch dann ausgegeben, wenn lync Server nicht für die hohe Systemauslastung verantwortlich ist.

  - **Computer Fehlerereignisse**     Bei Hardware-oder Softwareproblemen, die die Lebensfähigkeit eines Servers gefährden, werden Warnungen ausgegeben. Beispielsweise werden lync Server Administratoren benachrichtigt, wenn ein Server in Gefahr zu sein scheint, dass ein Festplattenfehler auftritt.

Die neuen Management Packs verfügen außerdem über eine erweiterte Berichtsfunktion. Zu den neuen Berichten für lync Server 2013 gehören:

  - Bericht zur Verfüg **barkeit von End-to-End-Szenarien**     In diesem Bericht wird die Verfügbarkeit/Uptime für wichtige lync Server Dienste wie Registrierung oder Anwesenheit erläutert.

  - **Kapazitäts Bericht**     In diesem Bericht werden mithilfe von Leistungsindikatorinformationen Trends für Systemkomponenten wie Arbeitsspeicher Verfügbarkeit und Prozessorauslastung dargestellt.

  - **Komponentenbericht**     In diesem Bericht werden die wichtigsten Warnungs Generatoren aufgelistet, die nach lync Server-Komponente gruppiert sind.

Zusätzlich zu diesen vorgefertigten Berichten melden die Management Packs für lync Server 2013 automatisch Warnungen für die Zuverlässigkeit von Anrufen (Metriken, die bei der Aufzeichnung von Kommunikationsdatensätzen gemessen werden) und QoE-Zustände (Metriken, gemessen an der Qualität der Erfahrung). Wenn Sie die Aufzeichnung von Anrufdetails aktiviert haben, können Sie Benachrichtigungen über die Anruf Zuverlässigkeit überprüfen, indem Sie das folgende Verfahren in der System Center Operations Manager-Konsole ausführen:

  - Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und klicken Sie dann auf **Anrufzuverlässigkeit**.

Führen Sie dieses Verfahren in der System Center Operations Manager-Konsole aus, um die Quality of Experience-Warnungen anzuzeigen:

  - Erweitern Sie **Überwachen**, **Zustand Microsoft Lync Server 2013** und **Anrufzuverlässigkeit und Medienqualität**, und erweitern Sie dann **Medienqualität**.

Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in Microsoft lync Server 2010 verwendet wird. Dies bedeutet, dass sich jeder System Center-Agent im wesentlichen selbst erkennt und seine Existenz dem zentralen Verwaltungs Server meldet. Durch die Ermittlung auf Computerebene wird die Verwaltung ihrer System Center-Infrastruktur vereinfacht und es können auch verschiedene Versionen der lync Server Management Packs (beispielsweise Management Packs für lync Server 2010 und Management Packs für lync Server 2013) nebeneinander bestehen.

</div>

<span> </span>

</div>

</div>

</div>

