---
title: Prüfliste für die Bereitstellung der Anrufsteuerung für Lync Server 2013
TOCTitle: Prüfliste für die Bereitstellung der Anrufsteuerung für Lync Server 2013
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398928(v=OCS.15)
ms:contentKeyID: 49295531
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste für die Bereitstellung der Anrufsteuerung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Überprüfen Sie anhand der folgenden Liste, ob Sie alle erforderlichen Konfigurationsaufgaben für die Bereitstellung der Anrufsteuerung (Call Admission Control, CAC) abgeschlossen haben.

  - Wenn ein oder mehrere Edgeserver bereitgestellt wurden, muss die IP-Adresse jeder externen Schnittstelle der Subnetzliste in den Netzwerkkonfigurationseinstellungen mit der Bitmaske 32 hinzugefügt werden. Sie sollten dieses Subnetz (IP-Adresse) außerdem der Netzwerkstandort-ID für den geografischen Standort zuordnen, an dem der A/V-Edgedienst bereitgestellt wurde.
    

    > [!NOTE]
    > Zum Implementieren der Anrufsteuerung sind keine Edgeserver erforderlich.



  - Stellen Sie über die Lync Server-Systemsteuerung oder durch Ausführen des in [Aktivieren der Anrufsteuerung in Lync Server 2013](lync-server-2013-enable-call-admission-control.md) beschriebenen Cmdlets sicher, dass die Anrufsteuerung aktiviert ist.

  - Stellen Sie sicher, dass die Anrufsteuerung an allen zentralen Standorten aktiviert ist. Diese Aufgabe können Sie im Topologie-Generator ausführen. Wenn beim Veröffentlichen eine Warnung generiert wird, ignorieren Sie diese *nicht*.

  - Stellen Sie sicher, dass alle im Unternehmensnetzwerk verwalteten Subnetze in den Netzwerkkonfigurationseinstellungen konfiguriert sind. Jedes Subnetz muss einem Netzwerkstandort zugeordnet sein, wie unter [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) erläutert.

  - Stellen Sie sicher, dass die Subnetz- oder IP-Adressen aller Front-End-Server, Survivable Branch Appliances (SBAs), A/V-Konferenzserver (sofern in einem separaten Pool bereitgestellt) und Vermittlungsserver in den Netzwerkkonfigurationseinstellungen konfiguriert sind.

