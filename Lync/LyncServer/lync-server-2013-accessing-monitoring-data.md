---
title: 'Lync Server 2013: Zugreifen auf Überwachungsdaten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 766b5a7786a9bbdb2cf09c8504824aaab24bbb80
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Zugreifen auf Überwachungsdaten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-05_

Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank "LcsCdr" für Kommunikationsdatensätze und "QoEMetrics" für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.

Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten berücksichtigen sollten, sind die lync Server Überwachungsberichte. Bei den Überwachungsberichten handelt es sich um eine Reihe von Standardberichten, die von Microsoft SQL Server Reporting Service veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Überwachungsberichte werden mit lync Server 2013 ausgeliefert und können über den lync Server-Bereitstellungs-Assistenten installiert werden, nachdem lync Server installiert und die Überwachung konfiguriert wurde.

Wie bereits an früherer Stelle angemerkt, ist bei den Monitoring-Berichten SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.

Weitere Informationen finden Sie im Thema [Installieren von lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) im lync Server 2013-Bereitstellungshandbuch.

</div>

<span> </span>

</div>

</div>

</div>

