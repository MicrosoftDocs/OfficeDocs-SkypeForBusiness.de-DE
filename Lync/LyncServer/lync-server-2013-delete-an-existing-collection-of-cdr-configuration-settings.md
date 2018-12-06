---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49890835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Bei der Installation von Microsoft Lync Server 2013 wird eine einzelne globale Auflistung von KDS-Konfigurationseinstellungen erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.

Beachten Sie, dass Sie auch die globalen Einstellungen löschen können. Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.

Sie können die KDS-Konfigurationseinstellungen mithilfe von Lync Server-Systemsteuerung oder dem [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration)-Cmdlet entfernen.

## So entfernen Sie die KDS-Konfigurationseinstellungen mithilfe von Lync Server-Systemsteuerung

1.  Klicken Sie im Lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die STRG-TASTE gedrückt und klicken dann auf weitere Auflistungen.

3.  Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.

4.  Klicken Sie im Dialogfeld Lync Server-Systemsteuerung auf **OK**.

## So entfernen Sie KDS-Konfigurationseinstellungen mithilfe des Lync Server-Verwaltungsshell-Cmdlets

Sie können Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen mithilfe von Windows PowerShell und des **Remove-CsCdrConfiguration**-Cmdlet löschen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen

  - Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

## So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

  - Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

## So entfernen Sie alle KDS-Konfigurationseinstellungen, die die Aufzeichnung von Kommunikationsdatensätzen deaktivieren

  - Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, bei denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wurde:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCdrConfiguration)-Cmdlet.

