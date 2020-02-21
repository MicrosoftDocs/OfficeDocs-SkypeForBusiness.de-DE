---
title: 'Lync Server 2013: definieren und Konfigurieren der Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb1f4ce9ec10b8babbf5507d56b9acb4bfb2494
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definieren und Konfigurieren der Topologie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-14_

Sie definieren und konfigurieren Ihre Topologie mithilfe des Topologie-Generators. Für den Topologie-Generator ist es nicht erforderlich, Mitglied der lokalen Gruppe Administratoren oder einer privilegierten Domänengruppe (beispielsweise Domänenadministratoren) zu sein. Sie können die Topologie als Standardbenutzer definieren. Beim erstmaligen Starten des Topologie-Generators und in nachfolgenden Bearbeitungssitzungen werden Sie zur Angabe des Speicherorts aufgefordert, an dem der Topologie-Generator das aktuelle Konfigurationsdokument laden soll. Sie haben folgende Möglichkeiten:

  - Herunterladen der Topologie aus einer vorhandenen Bereitstellung

  - Öffnen der Topologie aus einer lokalen Datei

  - Neue Topologie

Wenn Sie bereits eine Topologie definiert haben und den zentralen Verwaltungsspeicher eingerichtet haben, sollten Sie eine Topologie aus einer vorhandenen Bereitstellung herunterladen. Der Topologie-Generator liest die Informationen aus der Datenbank und ruft die aktuelle Definition ab. Wenn Sie über einen vorhandenen zentralen Verwaltungsspeicher verfügen, sollten Sie diese Option immer auswählen.

Wenn Sie keinen zentralen Verwaltungsspeicher eingerichtet haben und eine zuvor gespeicherte Konfiguration bearbeiten möchten, sollten Sie sich dafür entscheiden, die Topologie aus einer lokalen Datei zu öffnen. Bei dieser Datei handelt es sich um die Konfigurationsdatei, die in einer vorherigen Sitzung gespeichert wurde. Diese Option kann zum Bearbeiten der zuvor gespeicherten Topologie verwendet werden.

<div>


> [!WARNING]  
> Wenn Sie bereits eine Topologie veröffentlicht haben, sollten Sie keine lokale Konfigurationsdatei laden. Laden Sie die Topologie in diesem Fall aus einer vorhandenen Bereitstellung herunter.



</div>

Wählen Sie diese Option aus, um eine neue Topologie zu erstellen, wenn Sie eine neue Topologie-Generator-Konfiguration erstellen möchten. Ein zuvor gespeicherter Entwurf wird nur überschrieben, wenn Sie die neue Topologie unter demselben Dateinamen speichern wie die in einer vorherigen Entwurfssitzung erstellte Topologie.

In jeder dieser Optionen werden Sie aufgefordert, einen Speicherort für die Konfigurationsdatei des Topologie-Generators zu speichern. Die Datei kann an einem lokalen Speicherort, an einem gemeinsam genutzten Speicherort auf einer bereits eingerichteten Dateifreigabe oder auf einem Wechselmedium gespeichert werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definieren und Konfigurieren eines Front-End-Pool oder Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Bereitstellen gekoppelter Front-End-Pools für die Notfallwiederherstellung in lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Wählen Sie den zentralen Verwaltungs Server in lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

