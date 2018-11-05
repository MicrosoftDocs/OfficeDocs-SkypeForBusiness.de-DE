---
title: Wiederherstellen eines Enterprise Edition-Mitgliedsservers
TOCTitle: Wiederherstellen eines Enterprise Edition-Mitgliedsservers
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202191(v=OCS.15)
ms:contentKeyID: 52056470
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wiederherstellen eines Enterprise Edition-Mitgliedsservers

 

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Bei einem Ausfall eines Servers, auf dem eine der folgenden Serverrollen ausgeführt wird, führen Sie das Verfahren in diesem Thema aus, um den Server wiederherzustellen. Wenn mehrere Server unabhängig voneinander ausfallen, führen Sie das Verfahren für jeden einzelnen Server aus.

  - Front-End-Server

  - Vermittlungsserver

  - Director

  - Server für beständigen Chat

  - Edgeserver


> [!TIP]
> Es wird empfohlen, vor der Wiederherstellung ein Abbild des Systems zu erstellen. Sie können dieses Abbild dann als Rollbackpunkt verwenden, falls Probleme bei der Wiederherstellung auftreten. Es ist sinnvoll, das Abbild nach der Installation des Betriebssystems und von SQL&nbsp;Server zu erstellen und die Zertifikate wiederherzustellen oder erneut zu registrieren.



## So stellen Sie einen Mitgliedsserver wieder her

1.  Voraussetzung ist ein bereinigter oder neuer Server, der denselben vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der ausgefallene Server aufweist. Installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her bzw. registrieren Sie sie erneut.
    

    > [!NOTE]
    > Folgen Sie den Verfahren zur Bereitstellung der Server in Ihrer Organisation, um diesen Schritt durchzuführen.



2.  Melden Sie sich von einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, bei dem Server an, den Sie wiederherstellen.

3.  Navigieren Sie zum Installationsordner oder Datenträger von Lync Server, und starten Sie den Lync Server-Bereitstellungs-Assistenten unter **\\setup\\amd64\\Setup.exe**.

4.  Folgen Sie dem Bereitstellungs-Assistenten, um folgende Schritte auszuführen:
    
    1.  Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen Sie **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** aus, um die Lync Server-Serverrollen zu installieren.
    
    3.  Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Ausführliche Informationen über die Ausführung des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation zu der Serverrolle, die Sie wiederherstellen.

