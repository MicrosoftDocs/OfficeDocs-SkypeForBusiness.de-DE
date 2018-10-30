---
title: Zuweisen von Anwesenheitsrichtlinien auf Benutzerebene
TOCTitle: Zuweisen von Anwesenheitsrichtlinien auf Benutzerebene
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182614(v=OCS.15)
ms:contentKeyID: 49296003
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen von Anwesenheitsrichtlinien auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei einer Anwesenheitsrichtlinie handelt es sich um einen Satz von Einschränkungen für Anwesenheitsinformationen. In der folgenden Tabelle werden die in Lync Server 2013 verfügbaren Einstellungen für Anwesenheitsrichtlinien beschrieben.

### Einstellungen für Anwesenheitsrichtlinien

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
<td><p>Maximale Anzahl von Abonnentenkategorieabonnements</p></td>
<td><p>Beschränkt die Anzahl an zulässigen Abonnentenkategorieabonnements. Wenn Communicator beispielsweise die Anwesenheitsinformationen eines Benutzers abonniert, umfasst dies je ein Abonnement der einzelnen Kategorien &quot;Visitenkarte&quot;, &quot;Kalenderdaten&quot;, &quot;Notizen&quot;, &quot;Dienste&quot; und &quot;Status&quot;.</p>
<p>Wenn für diese Einstellung der Wert 0 festgelegt wird, bedeutet dies, dass das Benutzer- oder Kontaktobjekt nicht von anderen Teilnehmern abonniert werden kann.</p>
<div>

> [!NOTE]
> Bei Festlegung auf einen hohen Wert kann sich diese Einstellung deutlich auf die Leistung auswirken, und der durchschnittliche Benutzer verfügt über eine große Anzahl an Benutzern, die seine Anwesenheitsinformationen abonniert haben.


</div></td>
<td><p>Ganze Zahl</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>Maximale Anzahl von Anwesenheitsabonnementaufforderungen in der Warteschlange</p></td>
<td><p>Beschränkt die Anzahl von Einträgen in der Tabelle mit Abonnentenaufforderungen. Über diese Einstellung wird die maximale Anzahl von Aufforderungen festgelegt, die für einen Benutzer in der Warteschlange platziert werden können. Wenn Benutzer A beispielsweise die Anwesenheitsinformationen von Benutzer B abonniert, wird Benutzer B darüber informiert, und in der Tabelle mit Abonnentenaufforderungen von Benutzer B wird eine Bestätigungsaufforderung erstellt. Nachdem Benutzer B das Abonnement bestätigt, wird die Bestätigungsaufforderung aus der Tabelle mit Abonnentenaufforderungen von Benutzer B entfernt.</p>
<p>Wenn für diese Einstellung der Wert 0 festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Bestätigung aufgefordert wird, wenn ein Benutzer seine Anwesenheitsinformationen abonniert.</p></td>
<td><p>Ganze Zahl oder Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


Die Anwesenheitsrichtlinien **Standardrichtlinie** und **Dienst: Mittel** werden bei der Bereitstellung von Lync Server standardmäßig installiert. In der folgenden Tabelle werden die spezifischen Einstellungen dieser beiden Anwesenheitsrichtlinien beschrieben.

### Anwesenheitsrichtlinien

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
<td><p>Richtlinie für Anwendungen, für die mehr Benutzer die Anwesenheitsinformationen des Objekts abonnieren müssen.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>

