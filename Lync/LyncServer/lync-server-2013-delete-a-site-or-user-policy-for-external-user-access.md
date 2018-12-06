---
title: 'Lync Server 2013: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff'
TOCTitle: Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521013(v=OCS.15)
ms:contentKeyID: 49294332
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Sie können alle Standort- oder Benutzerrichtlinien löschen, die in der Lync Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt sind. Beim Löschen der globalen Richtlinie wird die Richtlinie nicht wirklich gelöscht, sondern lediglich auf die Standardeinstellungen zurückgesetzt. Diese Einstellungen unterstützen keine Optionen für den Zugriff durch externe Benutzer. Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

## So löschen Sie eine Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Externer Benutzerzugriff** und dann auf **Richtlinie für den externen Zugriff** .

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die zu löschende Standort- oder Benutzerrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen** .

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK** .

## Enfternen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Die Richtlinien für den externen Zugriff können über das Windows PowerShell-Cmdlet und das Remove-CsExternalAccessPolicy-Cmdlet gelöscht werden. Das Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff

  - Dieser Befehl entfernt die Richtlinie für den externen Zugriff, die auf den Standort "Redmond" angewendet werden:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

## So entfernen Sie alle Richtlinien für den externen Zugriff, die auf Benutzerbasis angemeldet werden

  - Dieser Befehl entfernt alle Richtlinien für den externen Zugriff, die auf Benutzerbasis konfiguriert wurden:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

## So entfernen Sie alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist

  - Dieser Befehl löscht alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

Weitere Informationen finden Sie in dem Hilfethema zum [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)-Cmdlet.

