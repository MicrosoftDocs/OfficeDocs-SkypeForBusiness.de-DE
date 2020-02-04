---
title: 'Lync Server 2013: Veröffentlichen der Standortdatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Veröffentlichen der Standortdatenbank aus lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

Die neuen Standorte, die Sie der Standortdatenbank hinzugefügt haben, stehen dem Client erst nach der Veröffentlichung zur Verfügung.

Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für das folgende Cmdlet:

  - **Publish-CsLisConfiguration**

Wenn Sie ELIN-Gateways (Emergency Location Identification Number) verwenden, müssen Sie die ELINs auch in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hochladen. Ihr PSTN-Betreiber verlangt möglicherweise, dass Sie ein bestimmtes Format für die ELIN-Einträge verwenden. Weitere Informationen erhalten Sie von Ihrem PSTN-Betreiber. Sie können die Datensätze aus der Datenbank des Standort Informationsdiensts exportieren und diese nach Bedarf formatieren.

<div>

## <a name="to-publish-the-location-database"></a>So veröffentlichen Sie die Standortdatenbank

  - Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

  - Führen Sie das folgende Cmdlet aus, um die Standortdatenbank zu veröffentlichen.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

