---
title: Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Der zentralisierte Protokollierungsdienst wird von Einstellungen und Parametern gesteuert und konfiguriert, die vom zentralen Protokollierungsdienst-Controller (CLSController) zum Senden von Befehlen an den zentralen Protokollierungsdienst-Agent (CLSAgent) des jeweiligen Computers erstellt und verwendet werden. Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Fall eines Start Befehls) die Konfiguration der Szenarien, Anbieter, Protokollgröße, Ablauf Verfolgungs Dauer und Flags, um mit dem Sammeln von Ablaufverfolgungsprotokollen entsprechend den bereitgestellten Konfigurationsinformationen zu beginnen.

<div>


> [!IMPORTANT]
> Nicht alle Windows PowerShell-Cmdlets, die für den zentralisierten Protokollierungsdienst aufgeführt sind, sind für die Verwendung mit lync Server 2013 lokalen Bereitstellungen vorgesehen. Die folgenden Cmdlets sind zwar möglicherweise anscheinend funktionsfähig, aber nicht für die Verwendung mit lync Server 2013 lokalen Bereitstellungen ausgelegt: 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Sets-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>und <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</P>
> <LI>
> <P><STRONG>CsClsSearchTerm-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> und <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Sets-CsClsSearchTerm</A>.</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Sets-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>und <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</P></LI></UL>Die in diesen Cmdlets definierten Einstellungen behindern oder verursachen keine unerwünschten Verhaltensweisen, sind jedoch für die Verwendung mit Microsoft 365 ausgelegt und ergeben keine erwarteten Ergebnisse in lokalen Bereitstellungen. Dies bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht verwendet werden, ihre Verwendung ist jedoch ein erweitertes Thema, das in dieser Dokumentation nicht behandelt wird.


</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

In den Themen in diesem Abschnitt werden die Konfigurationsoptionen, Parameter und Einstellungen für den zentralisierten Protokollierungsdienst definiert. Informationen zum Konfigurieren des zentralisierten Protokollierungsdiensts, zum Abrufen der Konfigurationseinstellungen, zum Erstellen von Szenarien, zur Verwaltung von Sicherheitsgruppen für den zentralisierten Protokollierungsdienst, zum Suchen und mehr finden Sie in den folgenden Themen.

  - [Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten in lync Server 2013](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Cmdlets für die zentralisierte Protokollierung in lync Server 2013](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

