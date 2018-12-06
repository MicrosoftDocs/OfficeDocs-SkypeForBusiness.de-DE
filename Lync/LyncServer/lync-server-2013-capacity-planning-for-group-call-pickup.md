---
title: Kapazitätsplanung für die Gruppenanrufannahme
TOCTitle: Kapazitätsplanung für die Gruppenanrufannahme
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ984297(v=OCS.15)
ms:contentKeyID: 52056284
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Kapazitätsplanung für die Gruppenanrufannahme

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der folgenden Tabelle wird das Benutzermodell der Gruppenanrufannahme beschrieben, das Sie als Grundlage für die Anforderungen bei der Kapazitätsplanung verwenden können.


> [!IMPORTANT]
> Die Gruppenanrufannahme basiert auf der Anwendung zum Parken von Anrufen. Beachten Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines gekoppelten Pools die Arbeitsauslastungen für Parken von Anrufen-Dienste, einschließlich der Gruppenanrufannahme, in beiden Pools unterstützen muss.



### Benutzermodell der Gruppenanrufannahme

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrik</th>
<th>Pro Front-End-Pool (mit 8 Front-End-Servern)</th>
<th>Pro Standard Edition-Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Empfohlene Benutzeranzahl pro Gruppe</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Empfohlene Gruppenanzahl</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Anzahl der für die Gruppenanrufannahme aktivierten Benutzern pro Pool</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Maximale Rate an eingehenden Anrufen pro Pool und Minute an alle Benutzer, die für die Gruppenanrufannahme aktiviert sind</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Rate an von Benutzern mit Gruppenanrufannahme wieder aufgenommenen Anrufen pro Pool pro Minute</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <UL>
> <LI>
> <P>Für Front-End-Pools mit weniger als acht&nbsp;Front-End-Servern werden die Metriken linear berechnet. Enthält Ihr Front-End-Pool beispielsweise einen Front-End-Server, beträgt die maximale 1/8 der in der Tabelle aufgeführten Werte.</P>
> <LI>
> <P>Sie können die empfohlene Anzahl von Benutzern pro Gruppe erhöhen oder reduzieren, solange die maximale Anzahl von Benutzern pro Pool nicht überschritten wird. Ihr Standard Edition-Server kann z.&nbsp;B. 120&nbsp;Gruppen mit je 25&nbsp;Benutzern enthalten, da die Anzahl der für die Gruppenanrufannahme aktivierten Benutzer sich im Rahmen der zulässigen Anzahl des Benutzermodells befindet (d.&nbsp;h. 120&nbsp;Gruppen mal 25&nbsp;Benutzer ergeben 3.000 für die Gruppenanrufannahme aktivierte Benutzer).</P></LI></UL>


