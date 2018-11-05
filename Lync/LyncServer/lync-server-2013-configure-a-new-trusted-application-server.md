---
title: Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers in Lync Server 2013
TOCTitle: Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers in Lync Server 2013
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg617964(v=OCS.15)
ms:contentKeyID: 49295009
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Eine vertrauenswürdige Anwendung ist eine auf Microsoft Unified Communications Managed-API (UCMA) 3.0 Core SDK basierende Anwendung, die von Microsoft Lync Server 2013 als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Dokumentation zum Unified Communications Managed API 3.0 Core-SDK" unter [http://go.microsoft.com/fwlink/?linkid=210320\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=210320%26clcid=0x407).

Informationen zum Konfigurieren von Microsoft Outlook Web Access (OWA) und Lync Server 2013 finden Sie unter "Konfigurieren der Integration von Outlook Web App und Lync Server 2010" in der Microsoft Exchange Server 2013-Dokumentation.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein. Es ist auch möglich, die geeigneten Administratorberechtigungen und -rechte für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

## So konfigurieren Sie einen vertrauenswürdigen Anwendungsserver

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

3.  Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld **Topologie speichern unter** auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie auf **Speichern**.

5.  Klicken Sie im linken Fensterbereich auf **Vertrauenswürdige Anwendungsserver** und anschließend auf **Neuer Pool für vertrauenswürdige Anwendungen**.

6.  Geben Sie den **Pool-FQDN** des Pools vertrauenswürdiger Anwendungen ein, geben Sie an, ob der Pool einen einzelnen oder mehrere Server enthalten soll, und klicken Sie auf **Weiter**.

7.  Wählen Sie auf der Seite **Nächsten Hop auswählen** den Lync Server 2013-Front-End-Pool aus der Liste aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten **Lync Server 2013** aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.
    
    Der **Pool für vertrauenswürdige Anwendungen** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet werden.

