---
title: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
TOCTitle: Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49890991
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS-Einträgen für die Pilotpoolbereitstellung

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Vor dem Bereitstellen des Lync Server 2013-Pilotpools müssen Sie die DNS-Host-Einträge (A) für den Pilotpool aktualisieren. Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe **Domänen-Admins** oder der Gruppe **DnsAdmins** bei dem Server oder der Domäne angemeldet sein.

**So konfigurieren Sie DNS-Hosteinträge (A)**

1.  Klicken Sie auf dem DNS-Server (Domain Name System) auf **Start** , klicken Sie auf **Verwaltung** und anschließend auf **DNS** .

2.  Erweitern Sie in der Konsolenstruktur für Ihre Domäne den Knoten **Forward-Lookupzonen** , und klicken Sie dann mit der rechten Maustaste auf die Domäne, in der Lync Server 2013 installiert wird.

3.  Klicken Sie auf **Neuer Host (A oder AAAA)** .

4.  Klicken Sie auf **Name** , und geben Sie den Hostnamen für den Lync Server 2013-Pool ein (der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss nicht als Teil des A-Eintrags eingegeben werden).

5.  Geben Sie im Feld **IP-Adresse** die IP-Adresse für den Front-End-Pool ein.

6.  Klicken Sie auf **Host hinzufügen** und dann auf **OK** .

7.  Klicken Sie abschließend auf **Fertig stellen** .

