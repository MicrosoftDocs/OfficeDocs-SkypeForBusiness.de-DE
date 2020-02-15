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
ms.openlocfilehash: 3acb91831a57ba68648ee513af337abe6a894849
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a><span data-ttu-id="2c1a4-102">Zugreifen auf Überwachungsdaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c1a4-102">Accessing monitoring data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c1a4-103">_**Letztes Änderungsstand des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="2c1a4-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="2c1a4-p101">Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank "LcsCdr" für Kommunikationsdatensätze und "QoEMetrics" für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>

<span data-ttu-id="2c1a4-106">Ein Tool, das Sie für den Zugriff auf und die Analyse von Überwachungsdaten berücksichtigen sollten, sind die lync Server Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-106">One tool you should consider for accessing and analyzing monitoring data is the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="2c1a4-107">Bei den Überwachungsberichten handelt es sich um eine Reihe von Standardberichten, die von Microsoft SQL Server Reporting Service veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-107">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="2c1a4-108">Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-108">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="2c1a4-109">Überwachungsberichte werden mit lync Server 2013 ausgeliefert und können über den lync Server-Bereitstellungs-Assistenten installiert werden, nachdem lync Server installiert und die Überwachung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-109">Monitoring Reports ship with Lync Server 2013 and can be installed from the Lync Server Deployment Wizard after Lync Server has been installed and monitoring has been configured.</span></span>

<span data-ttu-id="2c1a4-p103">Wie bereits an früherer Stelle angemerkt, ist bei den Monitoring-Berichten SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>

<span data-ttu-id="2c1a4-112">Weitere Informationen finden Sie im Thema [Installieren von lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) im lync Server 2013-Bereitstellungshandbuch.</span><span class="sxs-lookup"><span data-stu-id="2c1a4-112">For more information, see the topic [Installing Lync Server 2013 Monitoring Reports](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) in the Lync Server 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

