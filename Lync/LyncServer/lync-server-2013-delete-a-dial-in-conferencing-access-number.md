---
title: Löschen einer Zugriffsnummer für Einwahlkonferenzen
TOCTitle: Löschen einer Zugriffsnummer für Einwahlkonferenzen
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520956(v=OCS.15)
ms:contentKeyID: 49293320
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Zugriffsnummer für Einwahlkonferenzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Zugriffsnummer für Einwahlkonferenzen zu löschen.

## So löschen Sie eine Zugriffsnummer für Einwahlkonferenzen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.

5.  Klicken Sie auf **OK**.

## Entfernen von Zugriffsnummern für Einwahlkonferenzen mithilfe von Windows PowerShell-Cmdlets

Zugriffsnummern für Einwahlkonferenzen können auch mithilfe der Windows PowerShell und dem Cmdlet **Remove-CsDialInConferencingAccessNumber** gelöscht werden. Das Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Löschen einer bestimmten Zugriffsnummer für Einwahlkonferenzen

  - Mit diesem Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit der Identität "sip:RedmondDialInAccess@litwareinc.com" gelöscht:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## Entfernen aller Zugriffsnummern für Einwahlkonferenzen, die einer bestimmten Region zugeordnet sind

  - Mit diesem Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region "Northwest" zugeordnet sind:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## Entfernen von Zugriffsnummern für Einwahlkonferenzen basierend auf der primären Sprache

  - Mit diesem Befehl werden alle Zugriffsnummern für Einwahlkonferenzen mit der primären Sprache Italienisch gelöscht.
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber).

