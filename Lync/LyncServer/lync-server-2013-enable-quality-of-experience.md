---
title: Aktivieren von QoE (Quality of Experience)
TOCTitle: Aktivieren von QoE (Quality of Experience)
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182583(v=OCS.15)
ms:contentKeyID: 49295382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von QoE (Quality of Experience)

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben. Ausführliche Informationen finden Sie unter [Planen der Überwachung in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um QoE in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.


> [!NOTE]
> Zur Aktivierung von QoE müssen Sie zunächst die Überwachung und eine Monitoring-Back-End-Datenbank konfigurieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Bereitstellen des Monitoring Servers</A>.



## So aktivieren Sie QoE mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Quality of Experience-Daten**.

4.  Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion** und anschließend auf **QoE aktivieren**.

## Aktivieren von QoE mithilfe von Windows PowerShell-Cmdlets

QoE können Sie mit der Windows PowerShell und dem **Set-CsQoEConfiguration**-Cmdlet aktivieren. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So aktivieren Sie QoE für einen einzelnen Standort

  - Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf "True" ($True) fest.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

## So deaktivieren Sie QoE für einen einzelnen Standort

  - Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf "False" ($False) fest. Die Überwachung wird dadurch nicht deinstalliert. Das Erfassen und Speichern von QoE-Daten wird unterbrochen.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## So aktivieren Sie QoE mit einem einzelnen Befehl an mehreren Standorten

  - Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

Ausführliche Informationen finden Sie unter [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration).

## Siehe auch

#### Weitere Ressourcen

[Planen der Überwachung in Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md)

