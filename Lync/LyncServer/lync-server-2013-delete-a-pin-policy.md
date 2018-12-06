---
title: Löschen einer PIN-Richtlinie
TOCTitle: Löschen einer PIN-Richtlinie
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521020(v=OCS.15)
ms:contentKeyID: 49294519
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer PIN-Richtlinie

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie (persönliche Identifikationsnummer) zu löschen.


> [!NOTE]
> Die globale PIN-Richtlinie kann nicht gelöscht werden.



## So löschen Sie eine PIN-Richtlinie in Systemsteuerung für Lync Server 2013

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.

4.  Geben Sie auf der Seite **PIN-Richtlinie** im Suchfeld Teile oder den vollständigen Namen der Richtlinie ein, die Sie löschen möchten.

5.  Klicken Sie in der Richtlinienliste auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Entfernen der PIN-Richtlinien mithilfe von Lync Server-Verwaltungsshell und Cmdlets

Sie können PIN-Richtlinien mithilfe von Windows PowerShell und des Cmdlets „Remove-CsPinPolicy“ löschen. Sie können dieses Cmdlet entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Entfernen einer bestimmten PIN-Richtlinie

  - Mit diesem Befehl wird die PIN-Richtlinie mit dem Identitätswert „RedmondUsersPinPolicy“ entfernt.
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

## Entfernen aller auf Standortebene angewendeten PIN-Richtlinien

  - Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die auf Standortebene konfiguriert sind:
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

## Entfernen aller PIN-Richtlinien, die die Verwendung gängiger Muster zulassen

  - Mit diesem Befehl werden alle PIN-Richtlinien entfernt, die die Verwendung gängiger Muster zulassen: G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPinPolicy)-Cmdlet.

