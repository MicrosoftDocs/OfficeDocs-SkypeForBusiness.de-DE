---
title: 'Lync Server 2013: Definieren und Konfigurieren der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definieren und Konfigurieren der Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-14_

Sie definieren und konfigurieren Ihre Topologie mithilfe des Topologie-Generators. Für den Topologie-Generator ist es nicht erforderlich, dass Sie Mitglied der lokalen Gruppe Administratoren oder einer privilegierten Domänengruppe (beispielsweise Domänenadministratoren) sind. Sie können Ihre Topologie als Standardbenutzer definieren. Wenn Sie den Topologie-Generator bei der ersten Verwendung und nachfolgenden Bearbeitungssitzungen starten, werden Sie aufgefordert, den Speicherort anzugeben, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Folgende Optionen stehen zur Auswahl:

  - Herunterladen der Topologie aus einer vorhandenen Bereitstellung

  - Öffnen der Topologie aus einer lokalen Datei

  - Neue Topologie

Wenn Sie bereits eine Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Datenbank und ruft die aktuelle Definition ab. Wenn Sie über einen vorhandenen zentralen Verwaltungsspeicher verfügen, sollten Sie immer diese Option auswählen.

Wenn Sie keinen zentralen Verwaltungsspeicher eingerichtet haben und eine zuvor gespeicherte Konfiguration bearbeiten möchten, sollten Sie die Topologie aus einer lokalen Datei öffnen. Die Datei, die Sie öffnen, ist die Konfigurationsdatei, die in einer vorherigen Sitzung gespeichert wurde. Sie können diese Option verwenden, um die zuvor gespeicherte Topologie zu bearbeiten.

<div>


> [!WARNING]  
> Wenn Sie bereits über eine veröffentlichte Topologie verfügen, sollten Sie keine lokale Konfigurationsdatei laden. Sie sollten die Topologie aus einer vorhandenen Bereitstellung herunterladen.



</div>

Wählen Sie aus, um eine neue Topologie zu erstellen, wenn Sie eine neue Topologie-Generator-Konfiguration erstellen möchten. Ein zuvor gespeichertes Design wird nur dann überschrieben, wenn Sie es als die Datei speichern, die Sie in einer früheren Entwurfssitzung erstellt haben.

In jeder dieser Optionen werden Sie aufgefordert, einen Speicherort für die Konfigurationsdatei des Topology Builder zu speichern. Der Speicherort für die Datei kann ein lokaler Speicherort, ein freigegebener Speicherort auf einer festgelegten Dateifreigabe oder ein Wechselmedium sein.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Bereitstellen von Front-End-Poolpaaren für die Notfallwiederherstellung in Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Auswählen des zentralen Verwaltungsservers in Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

