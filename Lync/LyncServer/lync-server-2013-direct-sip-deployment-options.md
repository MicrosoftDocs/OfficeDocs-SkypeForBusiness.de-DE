---
title: 'Lync Server 2013: direkte SIP-Bereitstellungsoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521e1665361e15fffdf1e058731d04bc2eb9aa4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Direkte SIP-Bereitstellungsoptionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Dieses Thema enthält Beispiel Topologien für die Bereitstellung von direkten SIP-Verbindungen.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server eigenständig

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie lync Server 2013 als einzige Telefonielösung für einen Teil oder die gesamte Organisation verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

  - **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und Enterprise-VoIP inkrementell in kleineren Gruppen oder Teams in Ihrer Organisation einführen möchten.

  - **Lync Server nur-VoIP-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einem Standort erwägen, der über keine herkömmliche Telefonie-Infrastruktur verfügt.

<div>

## <a name="incremental-deployment"></a>Inkrementelle Bereitstellung

Bei der inkrementellen Bereitstellung ist lync Server 2013 die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, IP-Telefonie mithilfe von kontrollierten Pilotprogrammen in Ihr Unternehmen einzuführen. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications bedient werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Nebenstellenanlage verbleiben. Bei Bedarf können zusätzliche Arbeitsgruppen zu Enterprise-VoIP migriert werden.

Die inkrementelle Option wird empfohlen, wenn Sie über klar definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen haben und sich für eine zentralisierte Verwaltung eignen. Diese Option ist auch dann wirksam, wenn Sie über Teams oder Abteilungen verfügen, die sich über große geografische Bereiche verteilen, wobei die Einsparungen bei den Gebühren für Ferngespräche beträchtlich sein können. Diese Option ist tatsächlich nützlich, um virtuelle Teams zu erstellen, deren Mitglieder sich möglicherweise auf der ganzen Welt verteilen. Sie können solche Teams in einer schnellen Reaktion auf wechselnde Geschäftsanforderungen erstellen, ändern oder auflösen.

In der folgenden Abbildung ist die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage dargestellt. Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.

**Option für die inkrementelle Bereitstellung**

![Diagramm zur Abteilungs Migrations Option](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramm zur Abteilungs Migrations Option")

<div>


> [!NOTE]  
> Wenn Sie Ihre lync Server-Bereitstellung mit einem zertifizierten direkten SIP-Partner verbinden, ist ein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Nebenstellenanlage nicht erforderlich. Eine Liste mit zertifizierten Direct SIP-Partnern finden Sie auf <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>der Website Microsoft Unified Communications Open Interoperability Program unter.



</div>

<div>


> [!NOTE]  
> Für den in dieser Abbildung gezeigten Medienpfad ist die medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver weitergeleitet.



</div>

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. Ein PSTN-Gateway verbindet die VoIP-fähige Arbeitsgruppe (Voice over Internet Protocol) mit der Nebenstellenanlage. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remote Arbeitsthreads, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im PBX-System oder von Anrufern im PSTN befinden, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an lync Server weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Anbindung von Enterprise-VoIP an eine vorhandene PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise-VoIP hinter der Nebenstellenanlage

Wenn Enterprise-VoIP hinter der Nebenstellenanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Nebenstellenanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet und Anrufe an PBX-Benutzer an die Nebenstellenanlage.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise-VoIP vor der Nebenstellenanlage

Wenn Enterprise-VoIP vor der Nebenstellenanlage bereitgestellt wird, werden alle Anrufe an das PSTN-Gateway geleitet, das Anrufe für Enterprise-VoIP-Benutzer an lync Server weiterleitet und PBX-Benutzer zur Nebenstellenanlage aufruft. Anrufe an das PSTN sowohl von Enterprise-VoIP-als auch von PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. In der folgenden Tabelle sind die vor-und Nachteile dieser Konfiguration aufgeführt.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Vor-und Nachteile der Bereitstellung von Enterprise-VoIP vor der Nebenstellenanlage

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Vorteile</th>
<th>Nachteile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX bedient weiterhin Benutzer, die nicht für Enterprise-VoIP aktiviert sind.</p></td>
<td><p>Vorhandene Gateways unterstützen möglicherweise nicht die gewünschten Features oder Kapazitäten.</p></td>
</tr>
<tr class="even">
<td><p>PBX verarbeitet alle älteren Geräte.</p></td>
<td><p>Erfordert einen trunk vom Gateway zur Nebenstellenanlage und vom Gateway zum Vermittlungsserver. Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise-VoIP-Benutzer behalten dieselben Telefonnummern.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server nur-VoIP-Bereitstellung

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine umfassende VoIP-Lösung zu implementieren, ohne sich Gedanken über die Integration von Nebenstellenanlagen oder die erhebliche Bereitstellung und Wartung machen zu müssen. Kosten einer IP-PBX-Infrastruktur. Diese Lösung unterstützt sowohl vor-Ort-als auch Remote-Arbeitskräfte.

In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das PSTN werden an das entsprechende PSTN-Gateway weitergeleitet. Lync 2013 oder lync Phone Edition dient als Softphone. Die Remote Anrufsteuerung ist nicht verfügbar und unnötig, da es keine Nebenstellentelefone gibt, die von Benutzern gesteuert werden können. Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.

<div>


> [!NOTE]  
> Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung von lync Server 2013 erforderlich ist, kann eine nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.



</div>

In der folgenden Abbildung ist eine typische Topologie für eine reine VoIP-Bereitstellung dargestellt.

**Reine VoIP-Bereitstellung (Option)**

![Greenfidle-Bereitstellungsoption](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")

<div>


> [!NOTE]  
> Für den in dieser Abbildung gezeigten Medienpfad ist die medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie die medienumgehung deaktivieren, wird der Medienpfad durch den Vermittlungsserver weitergeleitet.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

