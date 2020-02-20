---
title: 'Lync Server 2013: Installieren von Edge-Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Installieren von Edge-Servern für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Sie installieren lync Server 2013 auf Edge-Servern mithilfe lync Server Bereitstellungs-Assistenten. Durch Ausführung des Bereitstellungs-Assistenten auf jedem Edgeserver können Sie die meisten Aufgaben ausführen, die zur Einrichtung des Edgeservers erforderlich sind. Um lync Server 2013 auf einem Edgeserver bereitstellen zu können, müssen Sie den Topologie-Generator bereits ausgeführt haben, um die Edgeserver Topologie zu definieren und zu veröffentlichen, und Sie auf Medien exportieren, die im Edgeserver verfügbar sind. Ausführliche Informationen finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) und [Exportieren der lync Server 2013 Topologie und Kopieren dieser Daten in externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Nachdem Sie die einzelnen Edgeserver mithilfe des Bereitstellungs-Assistenten installiert, installiert und die erforderlichen Zertifikate zugewiesen und die erforderlichen Dienste gestartet haben, können Sie das Setup mithilfe der Informationen unter [Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) zum Aktivieren und Konfigurieren des Zugriffs durch externe Benutzer sowie der Informationen unter [Überprüfen der Edge-Bereitstellung in lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) abschließen, einschließlich der Server-und Clientkonnektivität.

<div>

## <a name="to-install-an-edge-server"></a>So installieren Sie einen Edgeserver

1.  Melden Sie sich als Mitglied der lokalen Administratorgruppe bei dem Computer an, auf dem Sie den Edgeserver installieren möchten, oder verwenden Sie ein Konto mit gleichwertigen Benutzerrechten und -berechtigungen.

2.  Stellen Sie sicher, dass die Topologie-Konfigurationsdatei, die Sie mithilfe des Topologie-Generators erstellt und anschließend auf externe Medien exportiert und kopiert haben, im Edgeserver verfügbar ist (beispielsweise Zugriff auf das USB-Laufwerk, auf dem Sie die Topologie-Konfigurationsdatei kopiert haben, oder überprüfen Zugriff auf die Netzwerkfreigabe, in die Sie die Datei kopiert haben.)

3.  Starten Sie den Bereitstellungs-Assistenten.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie in einer Meldung dazu aufgefordert werden, Microsoft Visual C++ Redistributable zu installieren, klicken Sie auf <STRONG>Ja</STRONG>. Im nächsten Dialogfeld können Sie den vorgegebenen <STRONG>Installationsspeicherort</STRONG> akzeptieren oder auf <STRONG>Durchsuchen</STRONG> klicken, um einen alternativen Speicherort anzugeben. Klicken Sie anschließend auf <STRONG>Installieren</STRONG>. Aktivieren Sie im nächsten Dialogfeld das Kontrollkästchen <STRONG>Ich stimme den Bedingungen des Lizenzvertrags zu</STRONG>, und klicken Sie auf <STRONG>OK</STRONG>.

    
    </div>

4.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

5.  Klicken Sie nach Abschluss der Bereitstellungsphase durch den Assistenten unter **Schritt 1. Lokalen Konfigurationsspeicher installieren** auf **Ausführen**, und führen Sie die folgenden Schritte aus:
    
      - Klicken Sie im Dialogfeld **Lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** auf **Aus Datei importieren (für Edgeserver empfohlen)**, wechseln Sie zum Speicherort der exportierten Topologiekonfigurationsdatei, wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen** und anschließend auf **Weiter**.
    
      - Der Bereitstellungs-Assistent liest die Konfigurationsinformationen aus der Konfigurationsdatei aus und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
      - Nachdem der Prozess **Befehle ausführen** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.

6.  Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2: lync Server Komponenten einrichten oder entfernen** , um die lync Server 2013-Edge-Komponenten zu installieren, die in der auf dem lokalen Computer gespeicherten XML-Konfigurationsdatei angegeben sind.

7.  Verwenden Sie nach Abschluss der Installation die Informationen unter [Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md) , um die erforderlichen Zertifikate zu installieren und zuzuweisen, bevor Sie die Dienste starten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

