---
title: 'Lync Server 2013: Zuweisen des Bereichs für eine Standortrichtlinie'
TOCTitle: Zuweisen des Bereichs für eine Standortrichtlinie
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205360(v=OCS.15)
ms:contentKeyID: 49295706
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen des Bereichs für eine Standortrichtlinie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Wie auch andere Lync Server-Richtlinien, so können Standortrichtlinien auf mehreren Ebenen zugewiesen werden: auf der globalen Ebene, der Standortebene und der Benutzerebene. Jedoch verhält sich der Umfang von Standortrichtlinien auf Benutzerebene etwas anders als andere Lync Server-Richtlinien. Genau gesagt können benutzerspezifische Standortrichtlinien auf Endpunktobjekte (wie etwa Benutzer und Kontaktobjekte für Telefone in öffentlichen Bereichen) und auf Lync Server-Netzwerkstandorte angewendet werden. Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln). Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist. Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor jeglichen benutzerspezifischen Richtlinieneinstellungen.

Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen, und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.


> [!NOTE]
> Der Grund für dieses spezielle Richtlinienverhalten ist, dass, wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon gelten, welchem Pool oder welchem Standort der Benutzer zugewiesen ist.


