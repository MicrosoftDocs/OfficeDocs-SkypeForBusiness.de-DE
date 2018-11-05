---
title: Aktivieren der Aufzeichnung von Kommunikationsdatensätzen (KDS)
TOCTitle: Aktivieren der Aufzeichnung von Kommunikationsdatensätzen (KDS)
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520980(v=OCS.15)
ms:contentKeyID: 49293731
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Aufzeichnung von Kommunikationsdatensätzen (KDS)

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Nutzungs- und Diagnoseinformationen über Peer-zu-Peer-Aktivitäten aufgezeichnet, z. B. Chat, VoIP-Anrufe (Voice over Internet Protocol), Anwendungsfreigabe, Dateiübertragung und Besprechungen. Anhand der Nutzungsdaten kann die Rendite berechnet werden, und die Diagnosedaten können zur Problembehandlung bei Peer-zu-Peer-Aktivitäten und Besprechungen eingesetzt werden.

Verwenden Sie das folgende Verfahren, um die Aufzeichnung von Kommunikationsdatensätzen (KDS) in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.


> [!NOTE]
> Zur Aktivierung von KDS müssen Sie die Überwachung und eine Überwachungsdatenbank konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Bereitstellen des Monitoring Servers</A>.



## So aktivieren Sie KDS mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.

4.  Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Aktion** und anschließend auf **KDS aktivieren**.
    

    > [!NOTE]
    > KDS ist standardmäßig aktiviert.



## So aktivieren Sie KDS mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können KDS auch mithilfe der Windows PowerShell und des **Set-CsCdrConfiguration**-Cmdlets aktivieren. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie KDS für einen einzelnen Standort

  - Sie können KDS aktivieren, indem Sie den Parameter **EnableCDR** auf **True** (**$True**) setzen.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## So deaktivieren Sie KDS für einen einzelnen Standort

  - Sie können KDS deaktivieren, indem Sie den Parameter **EnableCDR** auf **False** (**$False**) setzen. Hierdurch wird die Überwachung nicht deinstalliert, sondern die Sammlung und Speicherung von KDS-Daten angehalten.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## So verwenden Sie einen einzelnen Befehl zum Aktivieren von KDS an mehreren Standorten

  - Mit diesem Befehl wird KDS für alle derzeit in der Organisation verwendeten KDS-Einstellungen aktiviert.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

Weitere Informationen finden Sie im Hilfethema für das [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Planen der Überwachung in Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md)

