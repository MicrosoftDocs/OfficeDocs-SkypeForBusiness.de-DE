---
title: 'Lync Server 2013: Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51950080d5f1c9aca2e94fe64f9e1d440da97b59
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

Lync Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und medienumgehung. Diese Features Teilen bestimmte Konfigurationsanforderungen für netzwerkregionen, Netzwerkstandorte und Zuordnungen der einzelnen Subnetze in der lync Server Topologie mit einem Netzwerkstandort. Ausführliche Informationen zur Bereitstellungsplanung für diese Funktionen finden Sie unter:

  - [Planung der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planung von Notrufdiensten (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Ausführliche Informationen zur Bereitstellung der einzelnen Funktionen finden Sie unter [Deploying Advanced Enterprise Voice Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in der Bereitstellungsdokumentation.

Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die allen drei erweiterten Enterprise-VoIP-Features gemeinsam sind.

<div>

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

<div>


> [!NOTE]  
> Netzwerkregionen sind nicht identisch mit lync Server Einwahlkonferenz Regionen, die zum Zuordnen von Zugriffsnummern für Einwahlkonferenzen mit einem oder mehreren lync Server Wählplänen erforderlich sind. Ausführliche Informationen zu Regionen mit Einwahlkonferenzen finden Sie unter <A href="lync-server-2013-dial-in-conferencing-requirements.md">Einwahlkonferenz Anforderungen in lync Server 2013</A> in der Planungsdokumentation.



</div>

Für die Anrufsteuerung ist es erforderlich, dass für jede netzwerkregion ein zugeordneter lync Server zentraler Standort vorhanden ist, der den Mediendatenverkehr innerhalb der Region verwaltet (also Entscheidungen basierend auf den von Ihnen konfigurierten Richtlinien trifft, ob eine echt Zeit-Audio-oder Videositzung möglich ist oder nicht. festgelegt werden). Lync Server zentralen Standorte stellen keine geografischen Standorte, sondern logische Gruppen von Servern dar, die als Pool oder eine Gruppe von Pools konfiguriert sind. Ausführliche Informationen zu zentralen Standorten finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation. Siehe auch [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md) in der Unterstützungsdokumentation.

Zum Konfigurieren einer netzwerkregion können Sie entweder die Registerkarte **Regionen** im Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder die Cmdlets **New-CsNetworkRegion** oder **CsNetworkRegion** lync Server-Verwaltungsshell ausführen. Anweisungen finden Sie unter [erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.

Die gleichen Netzwerkbereichs Definitionen werden von allen drei erweiterten Enterprise-VoIP-Funktionen gemeinsam verwendet. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Zum Zuordnen eines lync Server zentralen Standorts zu einer netzwerkregion geben Sie den Namen des zentralen Standorts entweder mithilfe des Abschnitts " **Netzwerkkonfiguration** " in lync Server-Systemsteuerung oder durch Ausführen der Cmdlets " **New-CsNetworkRegion** " oder " **Sets-CsNetworkRegion** lync Server-Verwaltungsshell" an. Anweisungen finden Sie unter [erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.

</div>

<div>

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

<div>


> [!NOTE]  
> Netzwerkstandorte werden nur von den erweiterten Enterprise-VoIP-Funktionen verwendet. Sie sind nicht identisch mit den Zweigstellenstandorten, die Sie in ihrer lync Server Topologie konfigurieren. Ausführliche Informationen zu Zweigstellenstandorten finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-reference-topologies.md">Referenz Topologien in lync Server 2013</A> . Siehe auch <A href="lync-server-2013-supported-topologies.md">Unterstützte Topologien in lync Server 2013</A> in der Unterstützungsdokumentation.



</div>

Zum Konfigurieren eines Netzwerkstandorts und Zuordnen dieser zu einer netzwerkregion können Sie entweder den Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder die lync Server-Verwaltungsshell Cmdlets **New-CsNetworkSite** oder **CsNetworkSite** ausführen. Ausführliche Informationen finden Sie unter [erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in der Bereitstellungsdokumentation, oder lesen Sie die lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Zum Beispiel können dem Standort "New York" in der Region "Nordamerika" die folgenden IP-Subnetze zugewiesen werden: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für "New York" zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

<div>


> [!WARNING]  
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein lync-Client nimmt seine lokale IP-Adresse an und maskiert die IP-Adresse mit der zugeordneten Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung selbst dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)<BR>Wenn sich beispielsweise ein lync-Client auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske 255.255.255.0 anmeldet, wird die Umgehungs-ID angefordert, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – wenngleich der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator die Subnetze genau so eingibt, wie von lync-Clients bereitgestellt (die mit Subnetzen während der Netzwerkkonfiguration entweder statisch oder durch DHCP (Dynamic Host Configuration Protocol) konfiguriert sind.)



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz im Unternehmensnetzwerk muss einem Netzwerkstandort zugeordnet sein (das heißt, jedes Subnetz muss einem geografischen Standort zugeordnet sein). Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP-Funktionen, die Endpunkte geografisch zu finden. Durch das Auffinden der Endpunkte kann die Anrufsteuerung beispielsweise den Fluss von Audio-und Videodaten in Echtzeit regulieren, die an den Netzwerkstandort und von diesem gesendet werden.

Um Subnetzen Netzwerkstandorten zuzuordnen, können Sie entweder den Abschnitt **Netzwerkkonfiguration** von lync Server-Systemsteuerung verwenden oder den lync Server-Verwaltungsshell verwenden. Anweisungen hierzu finden Sie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in der Bereitstellungsdokumentation oder in der lync Server-Verwaltungsshell-Dokumentation.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planung der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planung von Notrufdiensten (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planen der medienumgehung in lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

