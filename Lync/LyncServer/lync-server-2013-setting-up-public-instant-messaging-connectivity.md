---
title: 'Lync Server 2013: Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b3efe4e5d8e5cb84631969205842e56024394c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Wenn Ihre Organisation Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL unterstützen möchte, können Sie das Zertifikat nicht mit dem Lync Server-Bereitstellungs-Assistenten anfordern. Führen Sie stattdessen die folgenden Schritte aus:

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>So richten Sie die Verbindung mit öffentlichen Instant Messaging-Diensten ein

1.  Auf einem Front-End-Server öffnen Sie den Topologie-Generator. Erweitern Sie "Edgepools", und klicken Sie mit der rechten Maustaste auf "Edgeserver" oder "Edgeserver-Pool". Klicken Sie auf "Eigenschaften bearbeiten".

2.  Klicken Sie in "Eigenschaften bearbeiten" unter "Allgemein" auf "Partnerverbund für diesen Edgepool aktivieren" (Port 5061). Klicken Sie auf "OK".

3.  Klicken Sie auf "Aktion", wählen Sie "Topologie", und wählen Sie "Veröffentlichen" aus. Wenn Sie unter "Topologie veröffentlichen" dazu aufgefordert werden, klicken Sie auf "Weiter". Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf "Fertig stellen".

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".

5.  Klicken Sie unter "Lync Server-Komponenten einrichten" auf "Weiter". Auf dem Übersichtsbildschirm werden die Aktionen angezeigt, die gerade ausgeführt werden. Nachdem Sie die Bereitstellung durchgeführt haben, klicken Sie auf "Protokoll anzeigen", um verfügbare Protokolldateien anzuzeigen. Klicken Sie auf "Fertig stellen", um die Bereitstellung abzuschließen.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten über AOL

1.  Wenn die erforderliche Vorlage für die Zertifizierungsstelle zur Verfügung gestellt wurde, verwenden Sie auf dem Edgeserver das folgende Cmdlet der Windows PowerShell, um das Zertifikat anzufordern:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Der standardmäßige Zertifikatname der Vorlage, die für lync Server verwendet wird, ist Webserver. Geben Sie nur \<den Vorlagen\> Namen an, wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen mit AOL unterstützen möchte, müssen Sie Windows PowerShell anstelle des Zertifikat-Assistenten verwenden, um das Zertifikat dem externen Edge für die Zugriffs-Edgedienst zuzuweisen. Der Grund dafür ist, dass die "Web Server"-Vorlage der Zertifizierungsstelle, die der Zertifikat-Assistent zum Anfordern von Zertifikaten verwendet, keine EKU-Clientkonfiguration unterstützt. Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der Zertifizierungsstellenadministrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

