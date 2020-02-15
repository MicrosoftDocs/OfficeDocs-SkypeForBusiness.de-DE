---
title: 'Lync Server 2013: Verwalten der Dienstqualität (Quality of Service, QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b6661bb9e34db11099bc0f1a7526ba23792198
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Verwalten der Dienstqualität (Quality of Service, QoS) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

Bei der Dienstqualität (Quality of Service, QoS) handelt es sich um eine Netzwerktechnologie, die in einigen Organisationen zum Bereitstellen einer optimalen Benutzerfreundlichkeit für die Audio- und Videokommunikation verwendet wird. QoS kommt am häufigsten in Netzwerken mit beschränkter Bandbreite zum Einsatz, bei denen eine große Anzahl Netzwerkpakete um eine relativ geringe Bandbreite konkurrieren, Die Dienstqualität stellt für Administratoren eine Möglichkeit dar, um Paketen mit Audio- oder Videodaten höhere Prioritäten zuzuweisen. Durch die Zuweisung einer höheren Priorität zu diesen Paketen kann die Audio- und Videokommunikation schneller und mit weniger Unterbrechungen ausgeführt werden als Netzwerksitzungen, in denen Dateiübertragungen, Webbrowsen oder Datenbanksicherungen erfolgen. Die Ursache dafür ist die Zuweisung einer "Best Effort"-Priorität zu den Netzwerkpaketen, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden.

<div>


> [!NOTE]  
> In der Regel wird die Dienstqualität nur auf Kommunikationssitzungen innerhalb Ihres internen Netzwerks angewendet. Beim Implementieren von QoS konfigurieren Sie die Server und Router zwar für die Unterstützung der Paketmarkierung, Sie konfigurieren diese Geräte jedoch für die Unterstützung der Paketmarkierung auf eine bestimmte Art und Weise. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Selbst wenn die Dienstqualität in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass sie auf dieselbe Art und Weise wie der Dienst in Ihrem Netzwerk konfiguriert ist.



</div>

Für Microsoft lync Server 2013 ist keine Dienstqualität erforderlich. Wenn Sie QoS derzeit nicht verwenden, ist es nicht erforderlich, den Dienst vor der Installation von lync Server 2013 zu installieren. Wenn in Ihrem Netzwerk eine erhebliche Menge an Paketverlusten auftritt, empfiehlt es sich, dieses Problem zu beheben, indem Sie zusätzliche Bandbreite hinzufügen. Wenn keine weitere Bandbreite hinzugefügt werden kann, sollten Sie stattdessen die Quality of Service implementieren.

Lync Server 2013 bietet eine umfassende Unterstützung für die Dienstqualität: Das bedeutet, dass Organisationen, die bereits QoS verwenden, problemlos lync Server in Ihre vorhandene Netzwerkinfrastruktur integrieren können. Um dies zu tun, müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie lync Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt in der Regel nicht zum Ändern der von diesen Geräten verwendeten DSCP-Codes verwenden.

  - [Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mit lync Server 2013 Sie die Dienstqualität nicht aktivieren oder deaktivieren, indem Sie beispielsweise einen Eigenschaftswert auf "true" oder "false" festlegen. Stattdessen wird die Dienstqualität durch die Konfiguration von Portbereichen und die anschließende Erstellung und Anwendung einer Gruppenrichtlinie aktiviert. Wenn Sie sich später dazu entschließen, QoS nicht zu verwenden, können Sie die Dienstqualität einfach durch Entfernen der entsprechenden Gruppenrichtlinienobjekte "deaktivieren".

  - [Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die anderen Server konfigurieren.

  - [Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Diese Portbereiche gelten nur für Clientcomputer und stimmen in der Regel nicht mit den auf Ihren Servern konfigurierten Portbereichen überein.

  - [Konfigurieren einer Dienst Qualitätsrichtlinie in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Mithilfe dieser Richtlinien werden die DSCP-Codes ermittelt, die auf verschiedene Pakettypen angewendet werden.

  - [Konfigurieren einer Dienst Qualitätsrichtlinie für Ihre a/V-Edgeserver in lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Dieser Vorgang sollte nur für die interne Seite Ihrer Edgeserver ausgeführt werden. Die Ursache dafür ist, dass die Dienstqualität nicht für die Verwendung im Internet, sondern in Ihrem internen Netzwerk konzipiert ist.

  - [Konfigurieren von Quality of Service Policies in lync Server 2013 für Clients, die auf Windows 7 oder Windows 8 auszuführen](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)sind. Beachten Sie, dass Microsoft lync Server 2013 QoS für andere Windows-Betriebssysteme wie Windows Vista oder Windows XP nicht unterstützt.

  - [Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition Geräten in lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Standardmäßig ist QoS für lync Phone Edition-Geräte aktiviert. Sie können jedoch den DSCP-Standardwert ändern, um sicherzustellen, dass für alle Audiopakete in Ihrer Organisation derselbe DSCP-Code verwendet wird.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für die neuen Windows PowerShell-Cmdlets, die für die Verwaltung der Dienstqualität auf dieser Plattform zur Verfügung stehen. Weitere Informationen finden Sie unter Network Quality of Service-Cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)unter.



</div>

</div>

<span> </span>

</div>

</div>

</div>

