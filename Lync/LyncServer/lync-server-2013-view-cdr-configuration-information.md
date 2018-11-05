---
title: Anzeigen von Informationen zu Konfigurationen mit Aufzeichnung von Kommunikationsdatensätzen
TOCTitle: Anzeigen von Informationen zu Konfigurationen mit Aufzeichnung von Kommunikationsdatensätzen
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49890797
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Konfigurationen mit Aufzeichnung von Kommunikationsdatensätzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Bei der Installation von Microsoft Lync Server 2013 wird eine einzelne globale Auflistung von KDS-Konfigurationseinstellungen erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Sie können die in Ihrer Organisation verwendeten KDS-Konfigurationseinstellungen anzeigen, indem Sie Lync Server-Systemsteuerung oder das [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration)-Cmdlet verwenden.

## So zeigen Sie KDS-Konfigurationsinformationen mithilfe von Lync Server-Systemsteuerung an

1.  Klicken Sie im Lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** wird eine Liste mit allen KDS-Konfigurationseinstellungen angezeigt; für jede Einstellungsauflistung wird der **Name** der Auflistung angezeigt; ob KDS aktiviert wurde oder nicht (die Eigenschaft **KDS**); und ob die Bereinigung (die Eigenschaft **Bereinigungsfunktion für aufgezeichnete Kommunikationsdatensätze**) aktiviert wurde oder nicht. Sie können detaillierte Informationen zu einer Auflistung anzeigen, indem Sie doppelt auf diese Auflistung klicken. Alternativ können Sie die gewünschte Auflistung auswählen und auf **Bearbeiten** und **Details anzeigen** klicken. Beachten Sie Folgendes: Es können jeweils nur detaillierte Informationen zu einer Auflistung mit KDS-Konfigurationseinstellungen angezeigt werden.

## So zeigen Sie KDS-Konfigurationsinformationen mithilfe des Lync Server-Verwaltungsshell-Cmdlets an

Sie können die KDS-Konfigurationseinstellungen auch mithilfe von Lync Server-Verwaltungsshell und dem Cmdlet „Get-CsCdrConfiguration“ anzeigen. Sie können dieses Cmdlet entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie KDS-Konfigurationsinformationen an

  - Sie können Informationen zu allen KDS-Konfigurationseinstellungen anzeigen, indem Sie in der Lync Server-Verwaltungsshell den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Get-CsCdrConfiguration
    
    Es werden Informationen nach dem folgenden Muster zurückgegeben:
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

Weitere Informationen finden Sie im Hilfethema zum [Get-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCdrConfiguration)-Cmdlet.

