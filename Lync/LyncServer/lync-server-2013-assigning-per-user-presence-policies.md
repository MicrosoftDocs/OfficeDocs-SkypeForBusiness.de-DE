---
title: 'Lync Server 2013: Zuweisen von benutzerspezifischen Anwesenheitsrichtlinien'
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
ms.openlocfilehash: c4ae464e37c7d4061c9a7311d7df427b7a66db1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Zuweisen von benutzerspezifischen Präsenz Richtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-11_

Bei einer Anwesenheitsrichtlinie handelt es sich um eine Reihe von Beschränkungen und Einschränkungen, die sich auf die Anwesenheit auswirken. In der folgenden Tabelle werden die verfügbaren Anwesenheitsrichtlinien Einstellungen in lync Server 2013 beschrieben.

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
<td><p>Schränkt die Anzahl der Abonnenten Kategorie-Abonnements ein. Wenn Communicator beispielsweise die Anwesenheit eines Benutzers abonniert, erhält es ein Kategorie-Abonnement für jede Visitenkarte, Kalenderdaten, Notizen, Dienste und Status Kategorien.</p>
<p>Eine Einstellung von 0 bedeutet, dass das Benutzer-oder Kontaktobjekt nicht von anderen abonniert werden kann.</p>
<div>

> [!NOTE]  
> Diese Einstellung kann erhebliche Auswirkungen auf die Leistung haben, wenn Sie auf eine hohe Zahl festgelegt ist, und der durchschnittliche Benutzer hat eine große Anzahl von Benutzern, die seine Anwesenheit abonnieren.


</div></td>
<td><p>Ganze Zahl</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Maximale Anzahl von Benachrichtigungen in der Warteschlange für Anwesenheitsabonnements</p></td>
<td><p>Schränkt die Anzahl der Einträge in der Tabelle "angeforderte Abonnenten" ein. Diese Einstellung bestimmt die maximale Anzahl von Ansagen, die für einen bestimmten Benutzer in die Warteschlange gestellt werden können. Wenn Benutzer a beispielsweise die Anwesenheit von Benutzer b abonniert, erhält Benutzer b eine Aufforderung, dass Benutzer a jetzt Benutzer b abonniert hat, und in der Tabelle mit den Teilnehmern von Benutzer b wird eine Bestätigungsaufforderung erstellt. Nachdem der Benutzer b das Abonnement akzeptiert oder bestätigt hat, wird die Bestätigungsaufforderung aus Benutzer b-Tabelle "angeforderte Abonnenten" entfernt.</p>
<p>Eine Einstellung von 0 bedeutet, dass der Benutzer nicht aufgefordert wird, wenn jemand seine Anwesenheit abonniert.</p></td>
<td><p>Ganze Zahl oder Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Standardmäßig werden die **Standardrichtlinien** und- **Dienste: mittlere** Anwesenheitsrichtlinien installiert, wenn Sie lync Server bereitstellen. In der folgenden Tabelle werden die spezifischen Einstellungen der beiden Anwesenheitsrichtlinien beschrieben.

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

