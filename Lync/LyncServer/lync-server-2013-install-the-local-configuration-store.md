---
title: 'Lync Server 2013: Installieren des lokalen Konfigurationsspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installieren des lokalen Konfigurationsspeichers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-27_

Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie mit einem Domänenbenutzerkonto am Server angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der RTCUniversalReadOnlyAdmin-Gruppe ist.

Damit Sie mit dem lync Server-Bereitstellungs-Assistenten etwas tun können, muss der lokale Konfigurationsspeicher auf einem Server vorhanden sein. Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers, der nach der lokalen Installation von SQL Server Express erstellt wird. Der zentrale Verwaltungsspeicher selbst wird der vorhandenen SQL Server-Datenbank hinzugefügt, die auf dem Standard Edition-Server oder auf der SQL Server Express-basierten Datenbank installiert ist.

<div>


> [!IMPORTANT]  
> Wenn Sie das lync Server 2013-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie zur Eingabe eines Laufwerks und Pfads aufgefordert, auf dem lync Server 2013 installiert werden soll. Auf diese Weise können Sie die Installation auf einem anderen Laufwerk als dem Systemlaufwerk durchführen, wenn es in Ihrer Organisation erforderlich ist, oder wenn Sie Platz Bedenken haben. Sie können einfach den Pfad für den Installationspfad für die lync Server-Dateien im Dialogfeld einrichten auf ein neues, verfügbares Laufwerk ändern. Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen lync Server 2013-Dateien ebenfalls bereitgestellt.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>So installieren Sie den lokalen Konfigurationsspeicher

1.  Navigieren Sie auf Ihrem Installationsmedium zu \\Setup\\amd64\\Setup. exe, und klicken Sie dann auf **OK**.

2.  Wenn Sie aufgefordert werden, die Microsoft Visual C++ 2012-verteilbare Installation zu installieren, klicken Sie auf **Ja**.

3.  Klicken Sie auf der Seite **lync Server 2013-Installationsspeicherort** auf **OK**.

4.  Überprüfen Sie auf der Seite **Endbenutzer-Lizenzvertrag** die Lizenzbedingungen, und wählen Sie **Ich akzeptiere die Bedingungen im Lizenzvertrag**aus, und klicken Sie dann auf **OK** , um den Vorgang fortsetzen zu können.

5.  Klicken Sie auf der Seite Deployment-Assistent auf **lync Server System installieren oder aktualisieren**.

6.  Klicken Sie auf der Seite **lync Server 2013** neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.

7.  Vergewissern Sie sich auf der Seite **Lokalen Konfigurationsspeicher installieren**, dass die Option **Direkt vom zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.

8.  Wenn die Installation der lokalen Serverkonfiguration abgeschlossen ist, klicken Sie auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

