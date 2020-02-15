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
ms.openlocfilehash: 00b4ffc463412064b578938516c4ea33b0dbb663
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Installieren des lokalen Konfigurationsspeichers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-27_

Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie bei dem Server mit einem Domänenbenutzerkonto angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der RTCUniversalReadOnlyAdmin-Gruppe ist.

Um mit dem lync Server-Bereitstellungs-Assistenten etwas tun zu können, muss der lokale Konfigurationsspeicher auf einem Server vorhanden sein. Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers, der nach der lokalen Installation von SQL Server Express erstellt wird. Der zentrale Verwaltungsspeicher selbst wird der vorhandenen SQL Server Datenbank hinzugefügt, die auf der Standard Edition-Server-oder SQL Server Express basierten Datenbank installiert ist.

<div>


> [!IMPORTANT]  
> Wenn Sie lync Server 2013-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Pfad einzugeben, um lync Server 2013 zu installieren. Auf diese Weise können Sie auf einem anderen Laufwerk als dem Systemlaufwerk installieren, wenn es für Ihre Organisation erforderlich ist, oder wenn Sie über Platzprobleme verfügen. Sie können den Pfad der Installationspfade für die lync Server Dateien im Dialogfeld Setup einfach auf ein neues verfügbares Laufwerk ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen lync Server 2013 Dateien bereitgestellt.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>So installieren Sie den lokalen Konfigurationsspeicher

1.  Navigieren Sie auf den Installationsmedien zu \\Setup\\amd64\\Setup. exe, und klicken Sie dann auf **OK**.

2.  Wenn Sie zur Installation von Microsoft Visual C++ 2012 Redistributable aufgefordert werden, klicken Sie auf **Ja**.

3.  Klicken Sie auf der Seite **Installationsspeicherort für lync Server 2013** auf **OK**.

4.  Überprüfen Sie auf der Seite **Endbenutzer-Lizenzvertrag** die Lizenzbedingungen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags**zu, und klicken Sie dann auf **OK** , um den Vorgang fortsetzen zu können.

5.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

6.  Klicken Sie auf der Seite **lync Server 2013** neben Schritt 1 **: lokalen Konfigurationsspeicher installieren**auf **Ausführen**.

7.  Stellen Sie auf der Seite **lokalen Konfigurationsspeicher installieren** sicher, dass die Option **direkt aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **weiter**.

8.  Wenn die Installation der lokalen Serverkonfiguration abgeschlossen ist, klicken Sie auf **Fertig stellen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

