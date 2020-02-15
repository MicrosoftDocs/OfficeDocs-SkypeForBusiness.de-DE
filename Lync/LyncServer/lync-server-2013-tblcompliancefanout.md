---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c535dc860c5d1a8725d27217e8269c3d6c4902d2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a>tblComplianceFanout in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblComplianceFanout enthält alle Server, die ein Konformitätsereignis verarbeitet haben.

### <a name="columns"></a>Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>int</p></td>
<td><p>Ereignis-ID</p></td>
</tr>
<tr class="even">
<td><p>fanoutServerID</p></td>
<td><p>int</p></td>
<td><p>Serveridentität (entspricht tblServerIdentity. Server ID-Tabelle).</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fanoutEventID</p></td>
<td><p>Fremdschlüssel mit Lookup in der tblComplianceData. cmplEventID-Tabelle.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

