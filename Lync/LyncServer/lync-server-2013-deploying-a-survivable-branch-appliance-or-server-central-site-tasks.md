---
title: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers – Aufgaben am zentralen Standort
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Führen Sie die Aufgaben in diesem Abschnitt auf der zentralen Website aus. Wenn Sie einen Überlebenden Verzweigungs Server bereitstellen, überspringen Sie die erste Aufgabe.

<div>


> [!IMPORTANT]
> Bevor Sie die Aufgaben in diesem Abschnitt ausführen, müssen die folgenden Bedingungen erfüllt sein: 
> <UL>
> <LI>
> <P>Lync Server muss am zentralen Standort eingerichtet sein.</P>
> <LI>
> <P>Ein Installationstechniker auf der Zweigstelle muss der RTCUniversalSBATechnicians-Gruppe hinzugefügt werden.</P></LI></UL>Darüber hinaus empfehlen wir, dass Sie die folgenden Schritte ausführen:
> <UL>
> <LI>
> <P>Stellen Sie einen DHCP-Server an jeder Verzweigungs Website bereit, damit Clients IP-Adressen abrufen können.</P>
> <LI>
> <P>Als Alternative zum Bereitstellen eines DHCP-Servers an jeder Verzweigungs Website aktivieren Sie lync Server DHCP auf der Survivable Branch-Appliance oder einem Überlebenden Verzweigungs Server mithilfe des Cmdlets "lync Server-Verwaltungsshell" <STRONG>-Cmdlet-CsRegistrarConfiguration – EnableDHCPServer $true </STRONG>. Ausführliche Informationen finden Sie im Abschnitt "Hardware-und Software Anforderungen" in der Planning-Dokumentation unter den Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität der Zweigstelle für lync Server 2013</A> .</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Hinzufügen von Zweigstellenstandorten zur Topologie in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definieren einer Survivable Branch Appliance oder eines Survivable Branch Servers in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

