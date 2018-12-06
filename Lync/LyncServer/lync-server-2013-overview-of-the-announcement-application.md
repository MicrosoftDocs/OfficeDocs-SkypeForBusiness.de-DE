---
title: 'Lync Server 2013: Übersicht über die Ankündigungsanwendung'
TOCTitle: Übersicht über die Ankündigungsanwendung
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204757(v=OCS.15)
ms:contentKeyID: 49293506
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Ankündigungsanwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-13_

Bei Bereitstellung der Ansageanwendung müssen Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren. Anhand dieser Tabelle wird die Aktion ermittelt, die durchgeführt werden soll, wenn jemand eine nicht zugewiesene Nummer wählt. Die Tabelle nicht zugewiesener Rufnummern enthält für die Organisation gültige Rufnummernbereiche und legt fest, welche Ansageanwendung für welchen Bereich eingesetzt wird. Wenn ein Anrufer eine Rufnummer wählt, die für Ihre Organisation gültig, jedoch keiner Person zugewiesen ist, ermittelt Lync Server in der Routingtabelle für nicht zugewiesene Nummern, zu welchem Bereich die Nummer gehört, und leitet den Anruf an die für diesen Bereich angegebene Ansageanwendung weiter. Die Ansageanwendung beantwortet den Anruf und gibt eine Audionachricht (sofern dies konfiguriert ist) wieder. Anschließend wird der Anruf unterbrochen oder an ein vorab festgelegtes Ziel (z. B. einen Agent) übergeben. Mithilfe der Cmdlets in der Lync Server-Verwaltungsshell können Sie mehrere Audionachrichten konfigurieren oder Ziele übergeben.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

In Lync Server 2013 wird die Ansageanwendung automatisch mit der Reaktionsgruppenanwendung installiert. Die Ansageanwendung und die Reaktionsgruppenanwendung sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: Bei der Bereitstellung von Enterprise-VoIP werden diese beiden Anwendungen automatisch bereitgestellt.

