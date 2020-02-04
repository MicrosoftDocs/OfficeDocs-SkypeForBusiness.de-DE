---
title: 'Lync Server 2013: Konfigurieren von SQL Server für Lync Server'
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
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Konfigurieren von SQL Server für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-08-12_

In den Themen in diesem Abschnitt wird erläutert, wie Sie SQL Server für die Verwendung in einer Enterprise-Bereitstellung von lync Server bereitstellen und konfigurieren. Standard Edition-Server verwenden eine SQL Server Express-Version von SQL Server, die für die Arbeitslasten eines Standard Edition-Servers die richtige Größe hat.

Der lync Server 2013 Central-Verwaltungsspeicher enthält Benutzerdaten für alle Enterprise Edition-Server in einem Pool und ist für den Standort auf einem auf einem SQL Server basierenden Back-End-Server konzipiert. Als zentrales Repository kann der zentrale Verwaltungsspeicher nicht auf demselben Computer wie jede andere lync Server 2013-Rolle installiert werden. Der zentrale Verwaltungsspeicher kann sich nicht auf einem Enterprise Edition-Server im Pool befinden. Der zentrale Verwaltungsspeicher wird automatisch erstellt, wenn Sie die Topologie zum ersten Mal veröffentlichen, und wählen Sie aus, um die Datenbanken zu erstellen. Auf dem Computer, den Sie als Back-End-Server festlegen, muss bereits die SQL Server-Datenbanksoftware ausgeführt werden, damit die Installation erfolgreich durchgeführt werden kann.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Konfigurieren von SQL Server in Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Konfigurieren des SQL Server-Clusters für lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

