---
title: 'Lync Server 2013: Netzwerkeinstellungen für erweiterte Enterprise-VoIP-Features'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Lync Server verfügt über drei erweiterte Enterprise-VoIP-Features: Anrufannahme Steuerung (CAC), Notfalldienste (E9-1-1) und medienumgehung. Diese Features geben bestimmte Konfigurationsanforderungen für netzwerkregionen, Netzwerk Websites und die Zuordnung jedes Subnets in der lync Server-Topologie mit einer Netzwerk Website frei. Ausführliche Informationen zur Planung der bereitstellungdieser Features finden Sie unter:

  - [Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)

  - [Planen von Notrufdiensten (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

Details zum Bereitstellen der einzelnen Features finden Sie unter [Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in der Bereitstellungsdokumentation.

Dieses Thema bietet eine Übersicht über die Konfigurationsanforderungen, die für alle drei erweiterten Enterprise-VoIP-Features gelten.

<div>

## <a name="network-regions"></a>Netzwerkregionen

Bei einer Netzwerkregion handelt es sich um einen Netzwerkhub oder Netzwerkbackbone, der ausschließlich in der Konfiguration von Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung verwendet wird.

<div>


> [!NOTE]  
> Netzwerkregionen sind nicht mit lync Server-Einwahlkonferenz Regionen identisch, die für die Zuordnung von Einwahlkonferenz-Zugriffsnummern mit einem oder mehreren lync Server-Wählplänen erforderlich sind. Details zu Einwahlkonferenz Regionen finden Sie unter <A href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in lync Server 2013</A> in der Planungsdokumentation.



</div>

Für CAC ist es erforderlich, dass jeder Netzwerkbereich über eine zugeordnete lync Server Central-Website verfügt, die den Mediendatenverkehr in der Region verwaltet (d.-a. Entscheidungen basierend auf den von Ihnen konfigurierten Richtlinien trifft, ob eine Audio-oder Videositzung in Echtzeit möglich ist oder nicht. festgelegt werden). Lync Server Central-Websites stellen keine geografischen Speicherorte, sondern logische Gruppen von Servern dar, die als Pool oder Gruppe von Pools konfiguriert sind. Ausführliche Informationen zu zentralen Websites finden Sie unter [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md) in der Planungsdokumentation. Weitere Informationen finden Sie auch unter [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md) in der Dokumentation zur Unterstützung.

Zum Konfigurieren einer netzwerkregion können Sie entweder die Registerkarte **Regionen** im Abschnitt **Netzwerkkonfiguration** der lync Server-Systemsteuerung verwenden oder die lync Server **-Verwaltungsshell "New-CsNetworkRegion** " oder " **CsNetworkRegion** " ausführen. Cmdlets. Anweisungen hierzu finden Sie unter [erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur lync Server-Verwaltungsshell.

Die gleichen Netzwerkbereichs Definitionen werden von allen drei erweiterten Enterprise-VoIP-Features freigegeben. Wenn Sie bereits Netzwerkregionen für eine Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen für die anderen Funktionen erstellen. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben.

Wenn Sie eine lync Server Central-Website einem Netzwerkbereich zuordnen möchten, geben Sie den zentralen Standortnamen entweder über den Abschnitt **Netzwerkkonfiguration** der lync Server-Systemsteuerung oder durch Ausführen des **CsNetworkRegion** oder der **Gruppe-CsNetworkRegion an. **Cmdlets der lync Server-Verwaltungsshell. Anweisungen hierzu finden Sie unter [erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="network-sites"></a>Netzwerkstandorte

Ein Netzwerkstandort stellt einen geografischen Standort dar, z. B. ein Zweigstellenbüro, ein regionales Büro oder ein Hauptbüro. Jeder Netzwerkstandort muss einer bestimmten Netzwerkregion zugeordnet sein.

<div>


> [!NOTE]  
> Netzwerk Websites werden nur von den erweiterten Enterprise-VoIP-Features verwendet. Sie sind nicht identisch mit den Zweigstellen, die Sie in ihrer lync Server-Topologie konfigurieren. Details zu Verzweigungs Websites finden Sie unter <A href="lync-server-2013-reference-topologies.md">Referenz Topologien in lync Server 2013</A> in der Planungsdokumentation. Weitere Informationen finden Sie auch unter <A href="lync-server-2013-supported-topologies.md">Unterstützte Topologien in lync Server 2013</A> in der Dokumentation zur Unterstützung.



</div>

Wenn Sie eine Netzwerk Website konfigurieren und Sie einem Netzwerkbereich zuordnen möchten, können Sie entweder den Abschnitt **Netzwerkkonfiguration** der lync Server-Systemsteuerung verwenden oder die lync Server-Verwaltungsshell **New-CsNetworkSite** oder **CsNetworkSite** ausführen. Cmdlets. Ausführliche Informationen finden Sie unter [erstellen oder Ändern einer Netzwerk Website in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in der Bereitstellungsdokumentation, oder lesen Sie die Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="identify-ip-subnets"></a>Identifizieren von IP-Subnetzen

Arbeiten Sie mit Ihrem Netzwerkadministrator zusammen, um zu ermitteln, welche IP-Subnetze jedem Netzwerkstandort zugewiesen sind. Wenn Ihr Netzwerkadministrator die IP-Subnetze bereits in Netzwerkregionen und Netzwerkstandorte unterteilt hat, wird diese Aufgabe erheblich vereinfacht.

Sie können z. B. dem Standort „New York“ in der Region „Nordamerika“ die folgenden IP-Subnetze zuweisen: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Wenn der Benutzer Bob, der üblicherweise in Detroit arbeitet, für eine Schulung in das New Yorker Büro reist, seinen Computer einschaltet und sich mit dem Netzwerk verbindet, erhält sein Computer eine IP-Adresse aus einem der vier Bereiche, die für „New York“ zugewiesen sind, beispielsweise die Adresse 172.29.80.103.

<div>


> [!WARNING]  
> Die während der Netzwerkkonfiguration auf dem Server angegebenen IP-Subnetze müssen dem Format entsprechen, das von Clientcomputern bereitgestellt wird, damit eine ordnungsgemäße Verwendung für die Medienumgehung gewährleistet ist. Ein lync-Client übernimmt die lokale IP-Adresse und maskiert die IP-Adresse mit der zugehörigen Subnetzmaske. Bei Ermittlung der Umgehungs-ID für jeden Client vergleicht die Registrierung die Liste der IP-Subnetze für jeden Netzwerkstandort mit dem vom Client bereitgestellten Subnetz, um eine exakte Übereinstimmung zu ermitteln. Aus diesem Grund ist es wichtig, dass es sich bei den während der Netzwerkkonfiguration auf dem Server eingegebenen Subnetzen nicht um virtuelle, sondern um tatsächliche Subnetze handelt. (Wenn Sie die Anrufsteuerung bereitstellen, jedoch keine Medienumgehung verwenden, funktioniert die Anrufsteuerung auch dann ordnungsgemäß, wenn Sie virtuelle Subnetze konfigurieren.)<BR>Wenn beispielsweise ein lync-Client sich auf einem Computer mit einer IP-Adresse von 172.29.81.57 mit einer IP-Subnetzmaske von 255.255.255.0 anmeldet, wird die Bypass-ID angefordert, die dem Subnetz 172.29.81.0 zugeordnet ist. Wenn das Subnetz als 172.29.0.0/16 definiert ist, betrachtet die Registrierung dies – auch wenn der Client dem virtuellen Subnetz angehört – nicht als Übereinstimmung, da die Registrierung ausschließlich nach Subnetz 172.29.81.0 sucht. Daher ist es wichtig, dass der Administrator Subnetze genau so eingibt, wie dies von lync-Clients bereitgestellt wird (die mit Subnetzen während der Netzwerkkonfiguration entweder statisch oder durch DHCP (Dynamic Host Configuration Protocol) bereitgestellt werden.)



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>Zuordnen von Subnetzen zu Netzwerkstandorten

Jedes Subnetz innerhalb des Unternehmensnetzwerks muss einem geografischen Netzwerkstandort zugeordnet werden. Diese Zuordnung von Subnetzen ermöglicht es den erweiterten Enterprise-VoIP-Features, die Endpunkte geografisch zu finden. Durch die Ermittlung der Standorte von Endpunkten kann die Anrufsteuerung z. B. den Fluss von Audio- und Videoechtzeitdaten zum und vom Netzwerkstandort steuern.

Um Subnetze mit Netzwerkstandorten zu verknüpfen, können Sie entweder den Abschnitt **Netzwerkkonfiguration** der lync Server-Systemsteuerung verwenden, oder Sie können die lync Server-Verwaltungsshell verwenden. Anweisungen hierzu finden Sie unter [Zuordnen eines Subnetzes zu einer Netzwerk Website in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in der Bereitstellungsdokumentation oder in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen des Anrufsteuerungsdiensts in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Planen von Notrufdiensten (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

