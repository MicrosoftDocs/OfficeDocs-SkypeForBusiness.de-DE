---
title: Ändern von einfachen URLs nach der Migration
TOCTitle: Ändern von einfachen URLs nach der Migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49890894
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern von einfachen URLs nach der Migration

 

_**Letztes Änderungsdatum des Themas:** 2012-09-22_

Lync Server unterstützt drei einfache URLs:

  - **Meet** : Dient als Basis-URL für alle Konferenzen, die am Standort oder in der Organisation abgehalten werden. Mit der einfachen Meet-URL sind Links für den Besprechungsbeitritt einfach zu verstehen, leicht zu kommunizieren und zu verteilen.

  - **Dial-in** : Ermöglicht den Zugriff auf die Webseite mit den Einstellungen für eine Einwahlkonferenz. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben.

  - **Admin** : Ermöglicht einen schnellen Zugriff auf die Lync Server-Systemsteuerung. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation.

Nach dem Migrieren zu Lync Server 2013 müssen Sie die Auswirkung der Änderung auf die DNS-Einträge und Zertifikate für einfache URLs kennen. Wenn der Vorgängerversions-Director für Lync Server 2010 weiterhin in der Topologie verwendet wird, sind keine Änderungen der einfachen URLs erforderlich. Wenn der Director für Lync Server 2010 nach der Migration aus der Topologie entfernt wird, müssen die einfachen URL-DNS-Einträge so aktualisiert werden, dass sie auf einen der Lync Server 2013-Pools verweisen. Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet "Enable-CsComputer" auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## Ändern einfacher URLs nach der Migration

**So aktualisieren Sie die einfache Meet-URL**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den oberen Knoten **Lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten** .

2.  Wählen Sie im linken Bereich den Eintrag **Einfache URLs** aus. Wählen Sie dann unter **Besprechungs-URLs:** die Meet-URL aus, und klicken Sie auf **URL bearbeiten** .

3.  Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK** , um die bearbeitete URL zu speichern.

**So aktualisieren Sie die einfache Admin-URL**

1.  Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den oberen Knoten **Lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten** .

2.  Wählen Sie im linken Bereich den Eintrag **Einfache URLs** aus. Geben Sie dann unter dem Feld **URL für Verwaltungszugriff** die einfache URL ein, die Sie für den Verwaltungszugriff auf Systemsteuerung für Lync Server 2013 verwenden möchten, und klicken Sie anschließend auf **OK** .
    

    > [!TIP]
    > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Möglichkeit ist <STRONG>https://admin.</STRONG> <EM>&lt;Domäne&gt;</EM> .



## Siehe auch

#### Konzepte

[Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

