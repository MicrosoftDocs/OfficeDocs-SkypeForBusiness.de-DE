---
title: 'Lync Server 2013: Überprüfen des Topologieentwurfs'
TOCTitle: Überprüfen des Topologieentwurfs
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412951(v=OCS.15)
ms:contentKeyID: 49295301
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen des Topologieentwurfs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-01-02_

Der Topologie-Generator führt eine automatische Überprüfung der Topologie durch. Jeder Topologiefehler wird als Überprüfungsfehler identifiziert, angegeben durch das entsprechende Fehlersymbol neben der Serverrolle. Es ist wichtig, ebenfalls sicherzustellen, dass die Topologie die gewünschte Konfiguration für Ihre Bereitstellung richtig darstellt.

## So überprüfen Sie die Topologie vor deren Veröffentlichung

1.  Vergewissern Sie sich, dass alle einfachen URLs richtig konfiguriert wurden.

2.  Stellen Sie sicher, dass der SQL Server-basierte Server online und für den Computer verfügbar ist, auf dem Topologie-Generator installiert wurde (einschließlich aller erforderlichen Firewallregeln).

3.  Vergewissern Sie sich, dass die Dateifreigabe verfügbar ist, und dass die richtigen Berechtigungen definiert wurden.

4.  Stellen Sie sicher, dass die richtigen Serverrollen zur Erfüllung der Bereitstellungsanforderungen in der Topologie definiert wurden.

5.  Vergewissern Sie sich, dass die Server in Active Directory-Domänendienste vorhanden sind. Dies geschieht automatisch, wenn Sie die Server der Domäne hinzugefügt haben.

Wenn Sie die Topologie überprüft haben und keine Überprüfungsfehler aufgetreten sind, können Sie die Topologie veröffentlichen. Im Falle von Überprüfungsfehlern müssen Sie diese zunächst korrigieren, bevor Sie die Topologie veröffentlichen können. Ausführliche Informationen zum Veröffentlichen Ihrer Topologie finden Sie unter [Veröffentlichen der Topologie in Lync Server 2013](lync-server-2013-publish-the-topology.md).

