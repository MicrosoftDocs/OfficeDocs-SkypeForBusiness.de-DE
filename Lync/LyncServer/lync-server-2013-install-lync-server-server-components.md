---
title: 'Lync Server 2013: Installieren von lync Server-Server Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9237ed0b60e14383f69ff1e7ef0b0927afe49c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498702"
---
# <a name="install-server-components-for-lync-server-2013"></a>Installieren von Server Komponenten für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-05_

Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie bei dem Server mit einem Domänenbenutzerkonto angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der Gruppe RTCUniversalReadOnlyAdmins in Active Directory ist.

Der lync Server-Bereitstellungs-Assistent wird verwendet, um die erforderlichen Komponenten für jede lync-Serverrolle zu installieren und den Server zu aktivieren. In diesem Artikel werden die Schritte zum Bereitstellen eines Standard Edition-Server oder eines Front-End-Server in ihrer lync-Infrastruktur erläutert.

<div>

## <a name="to-install-lync-server-components"></a>So installieren Sie Lync Server-Komponenten

1.  Wenn der lync Server-Bereitstellungs-Assistent nicht gestartet wird, starten Sie ihn auf dem Server, auf dem Sie lync installieren möchten.

2.  Klicken Sie auf **lync Server System installieren oder aktualisieren**.

3.  Bestätigen Sie im Bereitstellungs-Assistenten, dass **Schritt 1: Installieren des lokalen Konfigurationsspeichers** ein grünes Häkchen aufweist, was bedeutet, dass dieser Server eine lokale Kopie des Speichers erfolgreich installiert hat. Wenn die Option nicht aktiviert ist, müssen Sie den lokalen Konfigurationsspeicher auf dem Server installieren. Führen Sie die Schritte unter [Installieren des lokalen Konfigurationsspeichers in lync Server 2013 aus](lync-server-2013-install-the-local-configuration-store.md) , und kehren Sie dann hierher zurück.

4.  Wenn Sie die lync Server 2013 Komponenten auf Ihrem Server installieren möchten, klicken Sie neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen** .

5.  Klicken Sie auf der Seite **lync Server Komponenten einrichten** auf **weiter** , um Komponenten gemäß der Definition in der veröffentlichten Topologie einzurichten.

6.  Auf der Seite **Befehle werden ausgeführt** wird eine Zusammenfassung der Befehle und Installationsinformationen angezeigt, wenn die Einrichtung stattfindet. Anschließend können Sie die Liste zum Auswählen eines anzuzeigenden Protokolls verwenden und dann auf **Protokoll anzeigen**klicken.

7.  Wenn lync Server 2013-Komponenten-Setup abgeschlossen ist und Sie die Protokolle nach Bedarf überprüft haben, klicken Sie auf **Fertig stellen** , um diesen Schritt in der Installation abzuschließen.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie aufgefordert werden, den Server neu zu starten (was möglicherweise geschieht, wenn die Windows-Desktop Umgebung installiert werden muss), tun Sie dies unbedingt. Wenn der Computer wieder betriebsbereit ist, müssen Sie diese Schritte erneut ausführen, beginnend mit Schritt 3, der weiter oben aufgeführt ist (führen Sie im Bereitstellungs-Assistenten im wesentlichen Schritt 2 aus).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

