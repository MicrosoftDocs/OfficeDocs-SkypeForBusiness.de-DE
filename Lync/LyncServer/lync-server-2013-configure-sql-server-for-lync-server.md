---
title: 'Lync Server 2013: Konfigurieren von SQL Server für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435fad8ff60a25b897eff91416e2809a6e2284f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Konfigurieren von SQL Server für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-08-12_

In den Themen in diesem Abschnitt wird erläutert, wie Sie SQL Server bereitstellen und konfigurieren, die in einer Enterprise-Bereitstellung von lync Server verwendet werden. Standard Edition-Server verwenden eine zusammengefasste SQL Server Express Version von SQL Server, die für die Arbeitslasten eines Standard Edition-Server richtig dimensioniert ist.

Der lync Server 2013 zentrale Verwaltungsspeicher speichert Benutzerdaten für alle Enterprise Edition-Server in einem Pool und ist auf einem SQL Server basierten Back-End-Server ausgelegt. Als zentrales Repository kann der zentrale Verwaltungsspeicher nicht auf demselben Computer installiert werden wie eine beliebige andere lync Server 2013 Rolle. Der zentrale Verwaltungsspeicher kann sich nicht auf einem Enterprise Edition-Server im Pool befinden. Der zentrale Verwaltungsspeicher wird automatisch erstellt, wenn Sie die Topologie zum ersten Mal veröffentlichen, und wählen Sie aus, um die Datenbanken zu erstellen. Der Computer, den Sie als Back-End-Server festlegen, muss bereits SQL Server Datenbanksoftware ausgeführt werden, damit die Installation erfolgreich abgeschlossen werden kann.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [SQL Server der Daten-und Protokolldatei Platzierung für lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Konfigurieren von SQL Server in lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Bereitstellungsberechtigungen für SQL Server in lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Datenbankinstallation mit lync Server-Verwaltungsshell in lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Konfigurieren von SQL Server Clustering für lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

