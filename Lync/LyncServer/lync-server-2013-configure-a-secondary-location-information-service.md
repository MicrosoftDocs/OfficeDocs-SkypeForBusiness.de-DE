---
title: 'Lync Server 2013: Konfigurieren einer sekundären Standortinformationsdienst'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a13e99aa7f9e3da9ddd04f5c8e7763c7de1481a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Konfigurieren einer sekundären Standortinformationsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

Lync Server 2013 stellt eine Webdienstschnittstelle bereit, die Sie verwenden können, um das Standortinformationsdienst auf eine SLS-Datenbank (Secondary Location Source) zu deuten. Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss Standortinformationsdienst WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der Standortinformationsdienst zunächst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet die standortanforderung vom Client an die SLS-Datenbank. Wenn der Speicherort im SLS vorhanden ist, sendet der Standortinformationsdienst den Standort dann zurück an den Client.

Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation für das folgende Cmdlet:

  - **Gruppe-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>So konfigurieren Sie die sekundäre Standortdatenbank (SLS)

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

