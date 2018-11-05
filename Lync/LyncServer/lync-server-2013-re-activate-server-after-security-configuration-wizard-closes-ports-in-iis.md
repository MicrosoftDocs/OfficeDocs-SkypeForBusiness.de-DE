---
title: 'Lync Server 2013: Erneutes Aktivieren eines Servers, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS schließt'
TOCTitle: Erneutes Aktivieren eines Servers, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS schließt
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398851(v=OCS.15)
ms:contentKeyID: 49295425
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erneutes Aktivieren eines Servers, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS schließt

 

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Einige Lync Server 2013-Rollen führen die Webdienste auf Port 4443 der Internetinformationsdienste (Internet Information Services, IIS) aus. Durch Ausführen des Lync Server-Bereitstellungs-Assistenten oder der Datei bootstrapper.exe oder durch Verwendung des **Enable-CsComputer**-Cmdlets wird eine Firewallausnahme definiert und der Port geöffnet. Wenn Sie den Windows Server 2008 R2-Sicherheitskonfigurations-Assistenten (oder andere Skripts zum Schutz Ihres Systems) ausführen, wird Port 4443 blockiert, und externe Clients können keine Verbindung zu Webdiensten herstellen. Zum erneuten Öffnen des Ports können Sie entweder die Firewallausnahme direkt bearbeiten oder den Server erneut aktivieren.

## So aktivieren Sie den Server mithilfe des Bereitstellungs-Assistenten erneut

1.  Klicken Sie auf der Seite " Lync Server-Bereitstellungs-Assistent" auf **Ausführen** neben **Schritt 2: Lync Server-Komponenten einrichten oder entfernen** .

2.  Klicken Sie auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter** .

3.  Wenn der Taskstatus auf der Seite **Befehle ausführen** als abgeschlossen angezeigt wird, klicken Sie auf **Fertig stellen** .
    

    > [!NOTE]
    > Sie können auch die Datei "bootstrapper.exe" oder das Cmdlet <STRONG>Enable-CsComputer</STRONG> ausführen, um den Server erneut zu aktivieren.


