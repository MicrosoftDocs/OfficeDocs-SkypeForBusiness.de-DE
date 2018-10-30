---
title: Überprüfen der Office Communications Server 2007 R2-Umgebung
TOCTitle: Überprüfen der Office Communications Server 2007 R2-Umgebung
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49890971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Office Communications Server 2007 R2-Umgebung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Vor der Bereitstellung von Lync Server 2013 zusammen mit Office Communications Server 2007 R2 müssen Sie überprüfen, ob die Office Communications Server 2007 R2-Dienste konfiguriert und gestartet wurden.

**Überprüfen, ob der Pool gestartet wurde, mithilfe des Verwaltungstools von Office Communications Server 2007 R2**

1.  Öffnen Sie das Verwaltungstool von Office Communications Server 2007 R2.

2.  Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.

3.  Stellen Sie sicher, dass die Dienste auf dem Standard Edition-Server oder im Enterprise-Pool ausgeführt werden.
    
    ![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")

**Überprüfen der für Office Communications Server 2007 R2 konfigurierten Benutzer**

1.  Öffnen Sie das Verwaltungstool von Office Communications Server 2007 R2.

2.  Erweitern Sie den Knoten **Gesamtstruktur**, den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.

3.  Klicken Sie auf **Benutzer**.

4.  Überprüfen Sie die Liste der Office Communications Server 2007 R2-Benutzer.
    
    ![Liste der Benutzer in OCS-Verwaltungstool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Liste der Benutzer in OCS-Verwaltungstool")

**Überprüfen der XMPP-Verbundpartnerkonfiguration der Vorversion**

1.  Navigieren Sie auf dem XMPP-Vorversionsserver zum Applet Verwaltungstools\\Dienste .

2.  Überprüfen Sie, ob der Office Communications Server-XMPP-Gatewaydienst gestartet ist.
    
    ![Office Communications Server: XMPP-Gatewaydienst](images/JJ205231.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server: XMPP-Gatewaydienst")

