---
title: Konfigurieren von DNS-Einträgen für die Bereitstellung eines Pilotpools
TOCTitle: Konfigurieren von DNS-Einträgen für die Bereitstellung eines Pilotpools
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49890767
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS-Einträgen für die Bereitstellung eines Pilotpools

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Bevor Sie den Lync Server 2013-Pilotpool bereitstellen können, müssen die DNS-Hosteinträge (A) für den Pilotpool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein.

**So konfigurieren Sie DNS-Hosteinträge (A)**

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start** , klicken Sie auf **Verwaltung** und anschließend auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Lync Server 2013 installiert wird.

3.  Klicken Sie auf **Neuer Host (A oder AAAA)** .

4.  Klicken Sie auf **Name** , und geben Sie den Hostnamen für den Pool ein (der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Geben Sie im Feld **IP-Adresse** die IP-Adresse für den Front-End-Pool ein.

6.  Klicken Sie auf **Host hinzufügen** und dann auf **OK** .

7.  Klicken Sie abschließend auf **Fertig stellen** .

