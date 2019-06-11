---
title: 'Lync Server 2013: Optionen für Bereitstellungen mit direkten SIP-Verbindungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Optionen für Bereitstellungen mit direkten SIP-Verbindungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

In diesem Thema finden Sie Beispiel Topologien für die Bereitstellung direkter SIP-Verbindungen.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server eigenständig

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie lync Server 2013 als einzige Telefonlösung für einen Teil oder eine ganze Organisation verwenden. This section describes the following deployments in detail:

  - **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einzuführen.

  - **Reine lync Server-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einer Website erwägen, die keine herkömmliche Telefonie-Infrastruktur aufweist.

<div>

## <a name="incremental-deployment"></a>Incremental Deployment

Bei der inkrementellen Bereitstellung ist lync Server 2013 die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Telefonanlage verwenden. This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Telefonanlage verbleiben. Zusätzliche Arbeitsgruppen können nach Bedarf in Enterprise-VoIP migriert werden.

The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management. This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant. In fact, this option is useful for creating virtual teams whose members may be scattered across the globe. You can create, modify, or disband such teams in rapid response to shifting business requirements.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Telefonanlage. This is the recommended topology for incremental deployment.

**Incremental deployment option**

![Diagramm zur Option] für die Abteilungs Migration (images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramm zur Option") für die Abteilungs Migration

<div>


> [!NOTE]  
> Wenn Sie Ihre lync Server-Bereitstellung mit einem zertifizierten direkten SIP-Partner verbinden, ist kein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Telefonanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie auf <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>der Microsoft Unified Communications Open Interoperability Program-Website unter.



</div>

<div>


> [!NOTE]  
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.



</div>

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeitern, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im PBX-System befinden, oder von Anrufern im PSTN, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an den lync-Server für das Routing weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP zu einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Telefonanlage und Enterprise-VoIP vor der Telefonanlage.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind the PBX

Wenn Enterprise-VoIP hinter der Telefonanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Telefonanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet, und Anrufe an PBX-Benutzer an die Telefonanlage.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice in Front of the PBX

Wenn Enterprise-VoIP vor der Telefonanlage bereitgestellt wird, kommen alle Anrufe an das PSTN-Gateway, das Anrufe an Enterprise-VoIP-Benutzer an den lync-Server weiterleitet und für PBX-Benutzer an die Telefonanlage anruft. Anrufe an das PSTN von Enterprise-VoIP-und PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. The following table shows the advantages and disadvantages of this configuration.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Telefonanlage

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Advantages</th>
<th>Disadvantages</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX bietet weiterhin Benutzern, die nicht für Enterprise-VoIP aktiviert sind.</p></td>
<td><p>Existing gateways may not support the features or capacity that you want.</p></td>
</tr>
<tr class="even">
<td><p>PBX handles all earlier devices.</p></td>
<td><p>Erfordert einen trunk vom Gateway zur Telefonanlage und vom Gateway zum Vermittlungs Server. You may need more trunks from the service provider.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP-Benutzer behalten die gleichen Telefonnummern.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Nur-VoIP-Bereitstellung von lync Server

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine vollständige VoIP-Lösung zu implementieren, ohne sich um die Integration von Telefonanlagen zu kümmern oder um eine beträchtliche Bereitstellung und Wartung zu vermeiden. Kosten einer IP-PBX-Infrastruktur. This solution supports both on-site and remote workers.

In this deployment, all calls are routed over the IP network. Calls to the PSTN are routed to the appropriate PSTN gateway. Lync 2013 oder lync Phone Edition dient als Softphone. Remote call control is unavailable and unnecessary because there are no PBX phones for users to control. Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.

<div>


> [!NOTE]  
> Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von lync Server 2013 erforderlich ist, kann eine reine VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.



</div>

The following figure shows a typical topology for a VoIP-only deployment.

**VoIP-only deployment option**

![Greenfidle-Bereitstellungsoption] (images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")

<div>


> [!NOTE]  
> The media path shown in this figure has media bypass enabled (the recommended configuration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

