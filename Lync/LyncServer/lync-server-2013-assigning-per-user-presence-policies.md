---
title: 'Lync Server 2013: Zuweisen von Anwesenheitsrichtlinien für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Zuweisen von Anwesenheitsrichtlinien für einzelne Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-11_

Eine Anwesenheitsrichtlinie besteht aus einer Reihe von Grenzwerten und Einschränkungen, die sich auf die Anwesenheit auswirken. In der folgenden Tabelle werden die in lync Server 2013 verfügbaren Anwesenheitsrichtlinien Einstellungen beschrieben.

### <a name="presence-policy-settings"></a>Einstellungen für Anwesenheitsrichtlinien

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>XML-Name</th>
<th>Anzeigename</th>
<th>Beschreibung</th>
<th>Typ</th>
<th>Wert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>Maximale Anzahl von Abonnenten Kategorie-Abonnements</p></td>
<td><p>Begrenzt die Anzahl der Abonnements für Abonnenten Kategorien. Wenn Communicator beispielsweise die Anwesenheit eines Benutzers abonniert, erhält er ein Kategorie-Abonnement für jede Visitenkarte, Kalenderdaten, Notizen, Dienste und Zustandskategorien.</p>
<p>Eine Einstellung von "0" bedeutet, dass der Benutzer oder das Kontaktobjekt nicht von anderen abonniert werden kann.</p>
<div>

> [!NOTE]  
> Diese Einstellung kann erhebliche Auswirkungen auf die Leistung haben, wenn Sie auf eine hohe Zahl festgelegt ist und der durchschnittliche Benutzer eine große Anzahl von Benutzern abonniert hat.


</div></td>
<td><p>Ganze Zahl</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Maximale Anzahl von Benachrichtigungen für Anwesenheitsabonnements in der Warteschlange</p></td>
<td><p>Schränkt die Anzahl von Einträgen in der Tabelle "angeforderte Abonnenten" ein. Diese Einstellung bestimmt die maximale Anzahl von Eingabeaufforderungen, die für einen bestimmten Benutzer in die Warteschlange gestellt werden können. Wenn Benutzer a beispielsweise die Anwesenheit von Benutzer b abonniert hat, erhält Benutzer b eine Aufforderung, dass Benutzer a jetzt Benutzer b abonniert hat, und in der Tabelle mit der Aufforderung "Abonnenten" von Benutzer b wird eine Bestätigungsaufforderung erstellt. Nachdem der Benutzer b das Abonnement akzeptiert oder bestätigt hat, wird die Bestätigungsaufforderung aus der Tabelle "angeforderte Abonnenten" von Benutzer b entfernt.</p>
<p>Eine Einstellung von "0" bedeutet, dass der Benutzer nicht dazu aufgefordert wird, wenn jemand seine Anwesenheit abonniert hat.</p></td>
<td><p>Ganzzahl oder Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Standardmäßig werden beim Bereitstellen von lync Server die Richtlinien **Standardrichtlinie** und **Dienst: Medium** -Anwesenheitsrichtlinien installiert. In der folgenden Tabelle werden die spezifischen Einstellungen der beiden Anwesenheitsrichtlinien beschrieben.

### <a name="presence-policies"></a>Anwesenheitsrichtlinien

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Richtlinienname</th>
<th>Beschreibung</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standardrichtlinie</p></td>
<td><p>Richtlinie für typische Benutzer. Dies ist die standardmäßige Anwesenheitsrichtlinie.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>Dienst: Mittel</p></td>
<td><p>Richtlinie für Anwendungen, die mehr Benutzer benötigen, um die Anwesenheit des Objekts zu abonnieren.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

