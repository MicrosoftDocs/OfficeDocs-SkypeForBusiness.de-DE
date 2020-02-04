---
title: Konfigurieren von Clients für die Migration
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
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Konfigurieren von Clients für die Migration

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-21_

Dieses Thema enthält die empfohlenen Client Bereitstellungsschritte, die Sie vor der Migration zu lync Server 2013 ausführen sollten. Diese Konfigurationsänderungen sollten auf Office Communications Server 2007 R2 erfolgen. Es ist sehr wichtig, dass Sie diese Schritte vor der Migration durchführen. Ausführliche Informationen finden Sie unter [Planen von Clients und Geräten in lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>So konfigurieren Sie Clients vor der Migration

1.  Bereitstellen der neuesten Office Communications Server 2007 R2-Server-, Client-und Geräte Updates (Hotfixes):
    
      - [Anwenden von Office Communications Server 2007 R2-Updates](apply-office-communications-server-2007-r2-updates.md)
    
      - [Beschreibung des kumulativen Updatepakets für Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Abrufen von Software Updates für Geräte](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Verwenden Sie auf Office Communications Server 2007 R2 die Client Versions Filterung, damit nur Office Communications Server 2007 R2-Clients mit den aktuellsten Updates installiert werden können, um sich anzumeldet.

3.  Verwenden Sie in Office Communications Server 2007 R2 die Client Versions Filterung, um zu verhindern, dass lync Server 2013-Clients sich anmelden. Befolgen Sie die Schritte unter **Konfigurieren der Client Versions Filterung** unter [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) , um die in der folgenden Tabelle aufgelisteten Versionsfilter hinzuzufügen. Weisen Sie für jeden Versionsfilter den Aktions **Block**zu.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
    <th>Benutzer-Agent-Kopfzeile</th>
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

