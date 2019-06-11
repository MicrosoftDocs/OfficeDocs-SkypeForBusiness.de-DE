---
title: 'Lync Server 2013: Einrichten der öffentlichen Chatkonnektivität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen (im) mit AOL unterstützen möchte, können Sie den lync Server-Bereitstellungs-Assistenten nicht verwenden, um das Zertifikat anzufordern. Führen Sie stattdessen die Schritte im folgenden Verfahren aus.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Einrichten der öffentlichen Instant Messaging-Konnektivität

1.  Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie Edge-Pools, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edge-Serverpool. Wählen Sie Eigenschaften bearbeiten aus.

2.  Wählen Sie in Eigenschaften bearbeiten unter Allgemein die Option Föderation für diesen Edge-Pool aktivieren (Port 5061) aus. Klicken Sie auf OK.

3.  Klicken Sie auf Aktion, wählen Sie Topologie aus, und wählen Sie veröffentlichen aus. Wenn Sie dazu aufgefordert werden, die Topologie zu veröffentlichen, klicken Sie auf Weiter. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf Fertig stellen.

4.  Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen. Klicken Sie erneut auf ausführen.

5.  Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL

1.  Wenn die erforderliche Vorlage für die Zertifizierungsstelle verfügbar ist, verwenden Sie das folgende Windows PowerShell-Cmdlet auf dem Edgeserver, um das Zertifikat anzufordern.
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Der Standardzertifikat Name der für lync Server verwendeten Vorlage ist Web Server. Geben Sie nur \<den Vorlagen\> Namen an, wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Ihre Organisation öffentliche Chat Verbindungen mit AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten Windows PowerShell verwenden, um das Zertifikat anzufordern, das dem externen Edge für den Access Edge-Dienst zugewiesen werden soll. Der Grund hierfür ist, dass die vom Zertifikat-Assistenten zum Anfordern eines Zertifikats verwendete Zertifikat Zertifizierungsstellen-Webservervorlage die Client-EKU-Konfiguration nicht unterstützt. Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der CA-Administrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

