---
title: 'Lync Server 2013: Testen des Directors'
TOCTitle: Testen des Directors
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398767(v=OCS.15)
ms:contentKeyID: 49294816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen des Directors in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Zu diesem Zeitpunkt haben Sie einen Director oder einen Directorpool konfiguriert, Ihre DNS-SRV-Einträge (Domain Name System) verweisen Clients jedoch noch immer an die Anmeldung über einen Pool- oder einen Standard Edition-Server. Bevor Sie den DNS-Eintrag so ändern, dass Lync 2013-Clients sich automatisch über den Director anmelden, testen Sie einen Client, indem sie ihn manuell an den Director verweisen.

## So testen Sie die Bereitstellung

1.  Melden Sie sich bei dem Computer an, auf dem Sie die Lync Server-Systemsteuerung mit einem Domänenkonto installiert haben, das der Gruppe **CSAdministrator** angehört.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im Navigationsbereich auf **Topologie** , und vergewissern Sie sich, dass in der Spalte **Status** ein grüner Server mit einem Pfeil ( ![Serversymbol mit grünem Pfeil](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Serversymbol mit grünem Pfeil")) für Ihren Director oder Directorpool angezeigt wird.

4.  Stellen Sie eine Verbindung auf zwei Computern her, auf denen der Lync Server 2013-Client installiert ist, und melden Sie sich bei jedem Computer mit einem anderen Benutzerkonto an, das für Lync Server 2013 aktiviert ist.

5.  Klicken Sie auf einem der Clientcomputer auf das Menü **Optionen** , wählen Sie die Einstellungsgruppe **Persönlich** aus, klicken Sie auf **Erweitert** , dann auf **Manuelle Konfiguration** , und legen Sie dann die Option **Interner Servername oder IP-Adresse** auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des neuen Directors oder Directorpools ein.

6.  Melden Sie sich bei beiden Clients an, und stellen Sie sicher, dass die Anmeldung auf dem Client, der sich über den Director anmeldet, erfolgreich verläuft. Beachten Sie den Anwesenheitsstatus des anderen Benutzers, und prüfen Sie, ob beide Sofortnachrichten austauschen können.

