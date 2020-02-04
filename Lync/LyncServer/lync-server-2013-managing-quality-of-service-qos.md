---
title: 'Lync Server 2013: Verwalten von Quality of Service (QoS)'
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
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Verwalten von QoS (Quality of Service) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

Quality of Service (QoS) ist eine Netzwerktechnologie, die in einigen Organisationen verwendet wird, um ein optimales Endbenutzererlebnis für Audio-und Videokommunikation zu gewährleisten. QoS wird am häufigsten in Netzwerken verwendet, in denen die Bandbreite begrenzt ist: da eine große Anzahl von Netzwerkpaketen für einen relativ geringen Anteil an verfügbarer Bandbreite konkurrieren, bietet die Dienstqualität eine Möglichkeit für Administratoren, Paketen höhere Prioritäten zuzuweisen. Durchführen von Audio-oder Videodaten. Wenn Sie diesen Paketen eine höhere Priorität geben, werden die Audio-und Videokommunikation wahrscheinlich schneller und mit weniger Unterbrechung abgeschlossen, als Netzwerksitzungen, die Dinge wie Dateiübertragungen, Webbrowser oder Datenbanksicherungen betreffen. Das liegt daran, dass für Netzwerkpakete, die für Dateiübertragungen oder Datenbanksicherungen verwendet werden, die Priorität "Best Effort" zugewiesen wird.

<div>


> [!NOTE]  
> In der Regel gilt die Dienstqualität nur für Kommunikationssitzungen in Ihrem internen Netzwerk. Wenn Sie QoS implementieren, konfigurieren Sie Ihre Server und Router so, dass die Paket Kennzeichnung unterstützt wird. Sie können diese Geräte jedoch so konfigurieren, dass die Paket Kennzeichnung auf eine bestimmte Weise unterstützt wird. Sie können nicht davon ausgehen, dass die Dienstqualität im Internet oder in anderen Netzwerken unterstützt wird. Auch wenn Quality wenn Service in anderen Netzwerken unterstützt wird, gibt es keine Garantie dafür, dass QoS auf die gleiche Weise konfiguriert wird, wie Sie den Dienst in Ihrem Netzwerk konfiguriert haben.



</div>

Microsoft lync Server 2013 erfordert keine Dienstqualität; Wenn Sie derzeit keine QoS verwenden, müssen Sie den Dienst nicht installieren, bevor Sie lync Server 2013 installieren. Wenn Sie eine beträchtliche Menge an Paketverlust in Ihrem Netzwerk erleben, empfiehlt es sich, dieses Problem zu beheben, indem Sie zusätzliche Bandbreite hinzufügen. Wenn das Hinzufügen von mehr Bandbreite nicht möglich ist, sollten Sie stattdessen Quality of Service implementieren.

Lync Server 2013 bietet umfassende Unterstützung für die Dienstqualität: Dies bedeutet, dass Organisationen, die bereits QoS verwenden, lync Server problemlos in Ihre vorhandene Netzwerkinfrastruktur integrieren können. Dazu müssen Sie die folgenden Aufgaben ausführen:

  - [Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Standardmäßig ist QoS für Computer und andere Geräte (z. B. iPhones), auf denen andere Betriebssysteme ausgeführt werden, deaktiviert. Obwohl Sie lync Server zum Aktivieren und Deaktivieren der Dienstqualität für Geräte verwenden können, können Sie das Produkt in der Regel nicht zum Ändern der DSCP-Codes verwenden, die von diesen Geräten verwendet werden.

  - [Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Sie müssen eine eindeutige Gruppe von Ports für unterschiedliche Pakettypen reservieren, beispielsweise für Audio und Video. Mit lync Server 2013 können Sie die Dienstqualität nicht aktivieren oder deaktivieren, indem Sie beispielsweise einen Eigenschaftswert auf "wahr" oder "falsch" festlegen. Stattdessen aktivieren Sie die Dienstqualität, indem Sie Portbereiche konfigurieren und dann Gruppenrichtlinien erstellen und anwenden. Wenn Sie sich später entschließen, QoS zu verwenden, können Sie die Qualität des Diensts einfach deaktivieren, indem Sie die entsprechenden Gruppenrichtlinienobjekte entfernen.

  - [Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md) Obwohl dies nicht erforderlich ist, können Sie Ihre Edgeserver für die Verwendung derselben Portbereiche wie die der anderen Server konfigurieren.

  - [Konfigurieren von Portbereichen für Ihre Microsoft lync-Clients in lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md) Diese Portbereiche gelten nur für Clientcomputer und sind in der Regel nicht identisch mit den Portbereichen, die auf Ihren Servern konfiguriert sind.

  - [Konfigurieren einer Quality of Service-Richtlinie in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Diese Richtlinien bestimmen die DSCP-Codes, die auf unterschiedliche Pakettypen angewendet werden.

  - [Konfigurieren einer Quality of Service-Richtlinie für Ihre a/V-Edgeserver in lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md) Dies sollte nur für die interne Seite Ihrer Edgeserver erfolgen. Das liegt daran, dass Quality of Service für die Verwendung in Ihrem internen Netzwerk und nicht im Internet vorgesehen ist.

  - [Konfigurieren von Dienst Qualitätsrichtlinien in lync Server 2013 für Clients, die unter Windows 7 oder Windows 8 ausgeführt werden](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md) Beachten Sie, dass Microsoft lync Server 2013 QoS für andere Windows-Betriebssysteme wie Windows Vista oder Windows XP nicht unterstützt.

  - [Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten in lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md) Standardmäßig ist QoS für lync Phone Edition-Geräte aktiviert. Möglicherweise möchten Sie jedoch den standardmäßigen DSCP-Wert ändern, um sicherzustellen, dass alle Audiopakete in Ihrer Organisation denselben DSCP-Code verwenden.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Windows Server 2012 oder Windows Server 2012 R2 verwenden, interessieren Sie sich möglicherweise für den neuen Satz von Windows PowerShell-Cmdlets, die für die Verwaltung der Dienstqualität auf dieser Plattform zur Verfügung stehen. Weitere Informationen finden Sie unter Network Quality of Service-Cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)unter.



</div>

</div>

<span> </span>

</div>

</div>

</div>

