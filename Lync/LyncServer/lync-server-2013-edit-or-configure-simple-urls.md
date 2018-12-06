---
title: 'Lync Server 2013: Bearbeiten oder Konfigurieren einfacher URLs'
TOCTitle: Bearbeiten oder Konfigurieren einfacher URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398063(v=OCS.15)
ms:contentKeyID: 49292969
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bearbeiten oder Konfigurieren einfacher URLs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-04_

Für dieses Verfahren ist keine Mitgliedschaft in einer lokalen Administratorgruppe oder einer Domänengruppe mit besonderen Rechten erforderlich. Melden Sie sich als Standardbenutzer bei einem Computer an.

Lync Server 2013 verwendet einfache URLs zur Weiterleitung interner und externer Dienstaufrufe an den Front-End-Server oder den Director (sofern bereitgestellt). Ausführliche Informationen zu einfachen URLs finden Sie unter [Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in der Planungsdokumentation. Es gibt mehrere Optionen für die Auswahl des Formats für einfache URLs. Ausführliche Informationen zu diesen Optionen finden Sie unter [DNS-Anforderungen für einfache URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in der Planungsdokumentation.

Standardmäßig werden einfache URLs in der folgenden Form konfiguriert (z. B. die einfache URL zur Einwahl): https://dialin.\<SIP-Domäne\>

## So konfigurieren Sie einfache URLs

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Knoten **Lync Server** und klicken Sie anschließend auf **Eigenschaften bearbeiten**.

2.  Wählen Sie im Bereich **Einfache URLs** entweder **Telefonzugriff-URLs:** (Dialin) oder **Besprechungs-URLs:** (Meet) aus und klicken Sie anschließend auf **URL bearbeiten** .

3.  Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK** , um die bearbeitete URL zu speichern. Im hier gezeigten Beispiel wurde die URL zur Einwahl in "https://pool01.contoso.net/dialin" geändert.

4.  Bearbeiten Sie ggf. auch die Besprechungs-URL, indem Sie dieselben Schritte ausführen.

## So definieren Sie die optionale einfache URL für den administrativen Zugriff

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Knoten **Lync Server** und klicken Sie anschließend auf **Eigenschaften bearbeiten**.

2.  Geben Sie im Feld **URL für Verwaltungszugriff** die einfache URL ein, die Sie für den Verwaltungszugriff auf die Systemsteuerung für Lync Server 2013 verwenden möchten, und klicken Sie auf **OK** .
    

    > [!TIP]
    > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Möglichkeit ist <STRONG>https://admin.</STRONG> <EM>&lt;Domäne&gt;</EM> .

    

    > [!IMPORTANT]
    > Wenn Sie eine einfache URL nach der anfänglichen Bereitstellung ändern, müssen Sie sich der Auswirkungen auf DNS-Einträge (Domain Name System) und Zertifikate für einfache URLs bewusst sein. Wenn die Änderung sich auf die Basis einer einfachen URL auswirkt, müssen Sie auch die DNS-Einträge und Zertifikate ändern. Beispielsweise führt eine Änderung von "https://lync.contoso.com/Meet" in "https://meet.contoso.com" zu einer Änderung der Basis-URL von "lync.contoso.com" in "meet.contoso.com", sodass auch die DNS-Einträge und Zertifikate zum Verweis auf "meet.contoso.com" geändert werden müssen. Wenn Sie die einfache URL von "https://lync.contoso.com/Meet" in "https://lync.contoso.com/Meetings" ändern, ändert sich die Basis-URL "lync.contoso.com" nicht, und eine Änderung der DNS-Einträge und Zertifikate ist nicht erforderlich. Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet <STRONG>Enable-CsComputer</STRONG> auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.



## Siehe auch

#### Konzepte

[Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

