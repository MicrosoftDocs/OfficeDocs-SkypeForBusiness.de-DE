---
title: 'Lync Server 2013: Optionen für Bereitstellungen mit direkten SIP-Verbindungen'
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
ms.openlocfilehash: e88dd5a576e467fbca25e9f467bd168fd6401d17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762223"
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

Wenn in Ihrer Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet wird, können Sie lync Server 2013 als einzige Telefonlösung für einen Teil oder eine ganze Organisation verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:

  - **Inkrementelle Bereitstellung:** Bei dieser Option wird davon ausgegangen, dass Sie über eine vorhandene PBX-Infrastruktur (Private Branch Exchange) verfügen und beabsichtigen, Enterprise-VoIP inkrementell für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einzuführen.

  - **Reine lync Server-Bereitstellung:** bei dieser Option wird davon ausgegangen, dass Sie die Bereitstellung von Enterprise-VoIP an einer Website erwägen, die keine herkömmliche Telefonie-Infrastruktur aufweist.

<div>

## <a name="incremental-deployment"></a>Incremental Deployment

Bei der inkrementellen Bereitstellung ist lync Server 2013 die einzige Telefonlösung für einzelne Teams oder Abteilungen, während die restlichen Benutzer in einer Organisation weiterhin eine Telefonanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, IP-Telefonie in Ihrem Unternehmen durch gesteuerte Pilotprogramme einzuführen. Arbeitsgruppen, deren Kommunikationsanforderungen am besten von Microsoft Unified Communications erfüllt werden, werden in Enterprise-VoIP verschoben, während andere Benutzer auf der vorhandenen Telefonanlage verbleiben. Zusätzliche Arbeitsgruppen können nach Bedarf in Enterprise-VoIP migriert werden.

Die Option "inkrementell" wird empfohlen, wenn Sie über klar definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen aufweisen und sich für eine zentralisierte Verwaltung eignen. Diese Option ist auch effektiv, wenn Sie über Teams oder Abteilungen verfügen, die sich über weite geografische Gebiete verteilen, wo die Einsparungen bei den Gebühren für Ferngespräche erheblich sein können. In der Tat ist diese Option für die Erstellung virtueller Teams hilfreich, deren Mitglieder auf der ganzen Welt verstreut sein können. Sie können solche Teams erstellen, ändern oder auflösen, indem Sie schnell auf wechselnde geschäftliche Anforderungen reagieren.

Die folgende Abbildung zeigt die generische Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Telefonanlage. Dies ist die empfohlene Topologie für die inkrementelle Bereitstellung.

**Incremental deployment option**

![Abteilungsbezogene Migrationsoption (Diagramm)](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Abteilungsbezogene Migrationsoption (Diagramm)")

<div>


> [!NOTE]  
> Wenn Sie Ihre lync Server-Bereitstellung mit einem zertifizierten direkten SIP-Partner verbinden, ist kein PSTN-Gateway (Public Switched Telephone Network) zwischen dem Vermittlungsserver und der Telefonanlage erforderlich. Eine Liste der zertifizierten Direct SIP-Partner finden Sie auf <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>der Microsoft Unified Communications Open Interoperability Program-Website unter.



</div>

<div>


> [!NOTE]  
> Der Medienpfad, der in dieser Abbildung dargestellt ist, hat die medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.



</div>

In dieser Topologie sind ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise-VoIP aktiviert. Ein PSTN-Gateway verknüpft die VoIP-fähige Arbeitsgruppe (Voice over Internet Protocol) mit der Telefonanlage. Benutzer, die für Enterprise-VoIP aktiviert sind, einschließlich Remotemitarbeitern, kommunizieren über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern an das PSTN und an Kollegen, die nicht für Enterprise-VoIP aktiviert sind, werden an das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich noch im PBX-System befinden, oder von Anrufern im PSTN, werden an das PSTN-Gateway weitergeleitet, das die Anrufe an den lync-Server für das Routing weiterleitet.

Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP zu einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Telefonanlage und Enterprise-VoIP vor der Telefonanlage.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind the PBX

Wenn Enterprise-VoIP hinter der Telefonanlage bereitgestellt wird, kommen alle Anrufe vom PSTN an die Telefonanlage, die Anrufe an Enterprise-VoIP-Benutzer an ein PSTN-Gateway weiterleitet, und Anrufe an PBX-Benutzer an die Telefonanlage.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice in Front of the PBX

Wenn Enterprise-VoIP vor der Telefonanlage bereitgestellt wird, kommen alle Anrufe an das PSTN-Gateway, das Anrufe an Enterprise-VoIP-Benutzer an den lync-Server weiterleitet und für PBX-Benutzer an die Telefonanlage anruft. Anrufe an das PSTN von Enterprise-VoIP-und PBX-Benutzern werden über das IP-Netzwerk an das kostengünstigste PSTN-Gateway weitergeleitet. Die folgende Tabelle zeigt die vor-und Nachteile dieser Konfiguration.

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
<td><p>Vorhandene Gateways unterstützen möglicherweise nicht die gewünschten Features oder Kapazitäten.</p></td>
</tr>
<tr class="even">
<td><p>PBX handles all earlier devices.</p></td>
<td><p>Erfordert einen trunk vom Gateway zur Telefonanlage und vom Gateway zum Vermittlungs Server. Möglicherweise benötigen Sie weitere Trunks des Dienstanbieters.</p></td>
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

Enterprise-VoIP bietet neuen Unternehmen und auch neuen Office-Websites für vorhandene Unternehmen die Möglichkeit, eine vollständige VoIP-Lösung zu implementieren, ohne sich um die Integration von Telefonanlagen zu kümmern oder um eine beträchtliche Bereitstellung und Wartung zu vermeiden. Kosten einer IP-PBX-Infrastruktur. Diese Lösung unterstützt sowohl Website-als auch Remotemitarbeiter.

In dieser Bereitstellung werden alle Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das PSTN werden an das entsprechende PSTN-Gateway weitergeleitet. Lync 2013 oder lync Phone Edition dient als Softphone. Die Remote Anrufsteuerung steht nicht zur Verfügung und ist nicht erforderlich, da es keine PBX-Telefone gibt, die von Benutzern gesteuert werden können. Voicemail-und automatische Telefonzentralendienste stehen über die optionale Bereitstellung von Exchange Unified Messaging (um) zur Verfügung.

<div>


> [!NOTE]  
> Zusätzlich zur Netzwerkinfrastruktur, die für die Unterstützung von lync Server 2013 erforderlich ist, kann eine reine VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Faxgeräten und analogen Geräten verwenden.



</div>

Die folgende Abbildung zeigt eine typische Topologie für eine reine VoIP-Bereitstellung.

**VoIP-only deployment option**

![Greenfidle-Bereitstellungsoption](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle-Bereitstellungsoption")

<div>


> [!NOTE]  
> Der Medienpfad, der in dieser Abbildung dargestellt ist, hat die medienumgehung aktiviert (die empfohlene Konfiguration). Wenn Sie sich entscheiden, die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungs Server weitergeleitet.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

