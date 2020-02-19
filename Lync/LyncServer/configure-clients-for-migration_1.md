---
title: Konfigurieren der Clients für die Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 542ee4d581d4df26a528a14fda5de792c2a2ad09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Konfigurieren der Clients für die Migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-21_

Dieses Thema enthält die empfohlenen Schritte zur Clientbereitstellung, die Sie vor der Migration zu lync Server 2013 durchführen sollten. Diese Konfigurationsänderungen sollten in Office Communications Server 2007 R2 vorgenommen werden. Es ist sehr wichtig, dass diese Schritte vor der Migration durchgeführt werden. Ausführliche Informationen finden Sie unter [Planning for Clients and Devices in lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>So konfigurieren Sie Clients vor der Migration

1.  Bereitstellen der neuesten Office Communications Server 2007 R2 Server-, Client-und Geräte Updates (Hotfixes):
    
      - [Anwenden von Office Communications Server 2007 R2 Updates](apply-office-communications-server-2007-r2-updates.md)
    
      - [Beschreibung des kumulativen Updatepakets für Communicator 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Abrufen von Softwareupdates für Geräte](https://go.microsoft.com/fwlink/?linkid=335809)

2.  Verwenden Sie auf Office Communications Server 2007 R2 die Client Versions Filterung, damit nur Office Communications Server 2007 R2 Clients mit den neuesten installierten Updates angemeldet werden können.

3.  Verwenden Sie auf Office Communications Server 2007 R2 die Client Versions Filterung, um zu verhindern, dass lync Server 2013-Clients sich anmelden. Führen Sie die unter **Konfigurieren der Client Versions Filterung** unter [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) beschriebenen Schritte aus, um die in der folgenden Tabelle aufgeführten Versionsfilter hinzuzufügen. Weisen Sie für jeden Versionsfilter die Aktion **Blockieren** zu.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>Benutzer-Agent-Header</th>
    <th>Version</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*..* *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*..* *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*..* *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

