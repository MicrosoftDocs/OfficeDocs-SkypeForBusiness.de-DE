---
title: Exportieren Sie Ihre Topologie, und kopieren Sie Sie in externe Medien für die Edge-Installation.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 784ed29372b137d5d3f58d749a3660d11cbb55d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exportieren der lync Server 2013 Topologie und kopieren auf externe Medien für die Edge-Installation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Nachdem Sie Ihre Topologie veröffentlicht haben, benötigt der lync Server-Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers, um den Bereitstellungsprozess auf dem Server zu starten. Im internen Netzwerk sind die Daten direkt von den Servern verfügbar, aber Edgeserver, die sich nicht in der internen Domäne befinden, können nicht auf die Daten zugreifen. Um die Topologie-Konfigurationsdaten für eine Edgeserver-Bereitstellung zur Verfügung zu stellen, müssen Sie die Topologiedaten in eine Datei exportieren und auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die im Edgeserver verfügbar ist) kopieren, bevor Sie die lync Server DEP ausführen. loyment-Assistent im Edgeserver. Verwenden Sie das folgende Verfahren, um Ihre Topologie-Konfigurationsdaten auf dem Edgeserver bereitzustellen, die Sie bereitstellen.

<div>


> [!NOTE]
> Nachdem Sie lync Server 2013 auf einem Edgeserver installiert haben, verwalten Sie die Edgeserver mit den Verwaltungstools im internen Netzwerk, wodurch die Konfiguration automatisch auf alle Edgeserver in Ihrer Bereitstellung repliziert wird. Die einzige Ausnahme ist das zuweisen und Installieren von Zertifikaten und das Beenden und starten von Diensten, die beide auf der Edgeserver ausgeführt werden müssen.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>So stellen Sie Ihre Topologiedaten mithilfe von lync Server-Verwaltungsshell auf einem Edgeserver zur Verfügung

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie im lync Server-Verwaltungsshell das folgende Cmdlet aus:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Kopieren Sie die exportierte Datei auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die im Edgeserver während der Bereitstellung zur Verfügung steht).

</div>

</div>

<span> </span>

</div>

</div>

</div>

