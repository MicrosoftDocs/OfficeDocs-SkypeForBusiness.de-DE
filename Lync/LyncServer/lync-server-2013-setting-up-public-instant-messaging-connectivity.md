---
title: 'Lync Server 2013: Einrichten der öffentlichen Chatkonnektivität'
TOCTitle: Einrichten der öffentlichen Chatkonnektivität
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205041(v=OCS.15)
ms:contentKeyID: 49294578
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten der öffentlichen Chatkonnektivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Wenn Ihre Organisation Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL unterstützen möchte, können Sie das Zertifikat nicht mit dem Lync Server-Bereitstellungs-Assistenten anfordern. Führen Sie stattdessen die folgenden Schritte aus:

## Einrichten von Verbindungen mit öffentlichen Instant Messaging-Diensten

1.  Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie die Edgepools, und klicken Sie dann mit der rechten Maustaste auf Ihren Edgeserver oder Edgeserverpool. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** unter **Allgemein** die Option **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus. Klicken Sie auf **OK** .

3.  Klicken Sie auf **Aktion** , und wählen Sie **Topologie** und dann **Veröffentlichen** aus. Wenn Sie gefragt werden, ob Sie die Topologie veröffentlichen möchten, klicken Sie auf **Weiter** . Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen** .

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

5.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.

## So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten über AOL

1.  Wenn die erforderliche Vorlage für die Zertifizierungsstelle zur Verfügung gestellt wurde, verwenden Sie auf dem Edgeserver das folgende Cmdlet der Windows PowerShell, um das Zertifikat anzufordern:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Der standardmäßige Zertifikatname der für Lync Server verwendeten Vorlage lautet "Web Server". Geben Sie den \<Vorlagennamen\> nur an, wenn eine andere Vorlage verwendet werden muss als die Standardvorlage.
    

    > [!IMPORTANT]
    > Wenn Ihre Organisation die Verbindung mit öffentlichen Instant Messaging-Diensten über AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten die Windows PowerShell zum Anfordern des Zertifikats verwenden, das dem externen Edge für den Zugriffs-Edgedienst zugewiesen werden soll. Der Grund dafür ist, dass die "Web Server"-Vorlage der Zertifizierungsstelle, die der Zertifikat-Assistent zum Anfordern von Zertifikaten verwendet, keine EKU-Clientkonfiguration unterstützt. Vor der Verwendung der Windows PowerShell zum Erstellen des Zertifikats muss der Administrator der Zertifizierungsstelle eine neue Vorlage mit Unterstützung für Client-EKU erstellen und bereitstellen.


