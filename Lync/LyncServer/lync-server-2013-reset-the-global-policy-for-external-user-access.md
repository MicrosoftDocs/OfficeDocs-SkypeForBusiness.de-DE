---
title: 'Lync Server 2013: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff'
TOCTitle: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182545(v=OCS.15)
ms:contentKeyID: 49294586
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die globale Richtlinie kann nicht vollständig gelöscht werden. Bei Verwendung der Option **Löschen** für die globale Richtlinie wird die globale Richtlinie lediglich auf die Standardeinstellungen zurückgesetzt. In diesen Einstellungen ist die Unterstützung von Optionen für den externen Benutzerzugriff nicht aktiviert.

## So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für externen Zugriff** .

4.  Klicken Sie auf der Registerkarte **Richtlinie für externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Löschen** .

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK** . Sie werden in einer Meldung im oberen Seitenbereich darüber informiert, dass die globale Richtlinie zurückgesetzt wurde.

## Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Die globale Richtlinie für den externen Zugriff kann mithilfe der Windows PowerShell und des Cmdlets "Remove-CsExternalAccessPolicy" zurückgesetzt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder aus einer Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Verwenden Sie den folgenden Befehl, um die globale Richtlinie für den externen Zugriff zurückzusetzen:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Weitere Informationen finden Sie in dem Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)-Cmdlet.

