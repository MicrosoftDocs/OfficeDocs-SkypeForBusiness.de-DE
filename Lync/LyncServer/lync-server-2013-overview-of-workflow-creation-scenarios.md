---
title: 'Lync Server 2013: Übersicht über Szenarios zur Erstellung von Workflows'
TOCTitle: Übersicht über Szenarios zur Erstellung von Workflows
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204646(v=OCS.15)
ms:contentKeyID: 49293052
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über Szenarios zur Erstellung von Workflows in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:

  - **Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agent-Gruppen, Warteschleifen, Feiertage und Geschäftszeiten, Wartemusik usw.

  - **Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle "CsResponseGroupAdministrator" (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle "CsResponseGroupManager" zu, wählt eine Warteschleife aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agent-Gruppen erstellt und die Gruppe ebenfalls der Warteschleife zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.
    

    > [!NOTE]
    > Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.


