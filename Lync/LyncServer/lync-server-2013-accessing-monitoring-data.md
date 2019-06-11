---
title: 'Lync Server 2013: Zugreifen auf Überwachungsdaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f6033c927a0d0c27b139d889c5fb0b0d9d4825
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Zugreifen auf Überwachungsdaten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank „LcsCdr“ für Kommunikationsdatensätze und „QoEMetrics“ für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.

Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten in Frage stellen sollten, sind die lync Server-Überwachungsberichte. Überwachungsberichte sind eine Reihe von Standardberichten, die vom Microsoft SQL Server-Berichterstattungsdienst veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Überwachungsberichte werden mit lync Server 2013 ausgeliefert und können über den lync Server-Bereitstellungs-Assistenten installiert werden, nachdem lync Server installiert und die Überwachung konfiguriert wurde.

Wie bereits an früherer Stelle angemerkt, ist für Monitoring-Berichte SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.

Weitere Informationen finden Sie im Bereitstellungshandbuch für lync Server 2013 im Thema [Installieren der lync Server 2013-Überwachungsberichte](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) .

</div>

<span> </span>

</div>

</div>

</div>

