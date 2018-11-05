---
title: 'Lync Server 2013: Testen des Standard Edition-Servers'
TOCTitle: Testen des Standard Edition-Servers
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412890(v=OCS.15)
ms:contentKeyID: 49295177
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen des Standard Edition-Servers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Das folgende Verfahren beschreibt, wie die Bereitstellung eines Standard Edition-Servers getestet werden kann.

## So testen Sie die Bereitstellung eines Standard Edition-Servers

1.  Fügen Sie in "Active Directory-Computer und -Benutzer" das Active Directory-Benutzerobjekt der Administratorrolle für die Lync Server 2013-Bereitstellung (für die die Lync Server-Systemsteuerung installiert ist) der Gruppe **CSAdministrator** hinzu.

2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    

    > [!NOTE]
    > Bei dem Benutzerkonto darf es sich nicht um den lokalen Administrator des Servers handeln, auf dem Lync Server 2013 Standard Edition ausgeführt wird. Wenn Sie der Gruppe "CsAdministors" nicht die entsprechenden Benutzer und Gruppen hinzufügen, erhalten Sie beim Öffnen der Systemsteuerung für Lync Server 2013 die folgende Fehlermeldung: "Nicht autorisiert: Der Zugriff wird aufgrund eines Fehlers bei der rollenbasierten Zugriffssteuerung verweigert."



3.  Melden Sie sich mit dem Verwaltungskonto bei dem Computer an, auf dem die Lync Server-Systemsteuerung installiert ist.

4.  Starten Sie die Lync Server-Systemsteuerung, und geben Sie bei Aufforderung die Anmeldeinformationen ein. Die Systemsteuerung für Lync Server 2013 zeigt Informationen zur Bereitstellung an.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie** , und vergewissern Sie sich, dass für jede Lync Server-Serverrolle, die bereitgestellt und online geschaltet wurde, der Dienststatus als Computersymbol mit einem grünen Pfeil und einem grünen Häkchen angezeigt wird.

6.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer** , und aktivieren Sie anschließend die beiden Benutzer für Lync Server 2013.

7.  Melden Sie einen Benutzer bei einem Computer, der Teil der Domäne ist, und den anderen Benutzer bei einem anderen Computer in der Domäne an.

8.  Installieren Sie Lync Server 2013 auf den beiden Clientcomputern, und vergewissern Sie sich anschließend, dass sich beide Benutzer bei Lync Server 2013 anmelden und Chatnachrichten austauschen können können.

## Siehe auch

#### Konzepte

[Bereitstellen von Clients und Geräten in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

