---
title: Bereitstellen von Survivable Branch Appliance-oder Server zentralen-Standortaufgaben
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebb3dd9fbeeaed69951ac11ee780bbe8d371a86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531362"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-zentralen Websiteaufgaben

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Führen Sie die Aufgaben in diesem Abschnitt am zentralen Standort aus. Wenn Sie ein Survivable Branch Server bereitstellen, überspringen Sie den ersten Vorgang.

<div>


> [!IMPORTANT]
> Bevor Sie die Aufgaben in diesem Abschnitt ausführen, müssen die folgenden Bedingungen erfüllt sein: 
> <UL>
> <LI>
> <P>Lync Server müssen am zentralen Standort eingerichtet sein.</P>
> <LI>
> <P>Ein Installationstechniker am Zweigstellenstandort muss der Gruppe "Gruppe" rtcuniversalsbatechnicians "hinzugefügt werden.</P></LI></UL>Darüber hinaus wird empfohlen, dass Sie die folgenden Schritte ausführen:
> <UL>
> <LI>
> <P>Bereitstellen eines DHCP-Servers an jedem Zweigstellenstandort, um Clients das Abrufen von IP-Adressen zu ermöglichen.</P>
> <LI>
> <P>Als Alternative zur Bereitstellungeines DHCP-Servers an jedem Zweigstellenstandort aktivieren Sie lync Server DHCP auf dem Survivable Branch Appliance oder Survivable Branch Server mithilfe des lync Server-Verwaltungsshell Cmdlets " <STRONG>Gruppe-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>". Ausführliche Informationen finden Sie im Abschnitt "Hardware-und Software Anforderungen" der Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013</A> in der Planungsdokumentation.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Hinzufügen eines Survivable Branch Appliance zu Active Directory in lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definieren einer Survivable Branch Appliance oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

