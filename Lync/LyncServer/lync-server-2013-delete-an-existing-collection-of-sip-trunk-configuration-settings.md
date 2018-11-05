---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49890708
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

  - Ob die Medienumgebung für Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.

  - Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Bei der Installation von Microsoft Lync Server 2013 wird eine globale Auflistung von SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Diese globale Auflistung von Einstellungen kann nicht gelöscht werden. Sie können jedoch die Lync Server-Systemsteuerung oder das [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)-Cmdlet verwenden, um die Eigenschaften in der globalen Auflistung auf ihre Standardwerte zurückzusetzen. Wenn Sie beispielsweise die Eigenschaft **Enable3pccRefer** auf **True** setzen, wird diese Eigenschaft beim Zurücksetzen der globalen Auflistung auf den Standardwert **False** zurückgesetzt.

Administratoren können auch benutzerdefinierte Trunkkonfigurationseinstellungen auf Standort- oder Dienstebene (für ein einzelnes PSTN-Gateway) erstellen. Diese benutzerdefinierten Einstellungen können entfernt werden. Beachten Sie beim Entfernen dieser benutzerdefinierten Einstellungen Folgendes:

  - Wenn Sie Einstellungen auf Dienstebene entfernen, wird der mit diesen Einstellungen verwaltete SIP-Trunk mit den Einstellungen verwaltet, die für den entsprechenden Standort gelten, sofern vorhanden. Wenn keine Standorteinstellungen vorhanden sind, werden diese Trunks mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

  - Wenn Sie Einstellungen auf Standortebene entfernen, werden alle mit diesen Einstellungen verwaltete SIP-Trunks jetzt mit der globalen Auflistung der Trunkkonfigurationseinstellungen verwaltet.

## Entfernen der Trunkkonfigurationseinstellungen mithilfe der Lync Server-Systemsteuerung

1.  Klicken Sie in Lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.

2.  Wählen Sie auf der Registerkarte **Trunkkonfiguration** die Auflistung der zu löschenden SIP-Trunkkonfigurationseinstellungen aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**. Klicken Sie zum Löschen mehrerer Auflistungen auf die erste zu löschende Auflistung, halten Sie die STRG-TASTE gedrückt, und klicken Sie dann auf die weiteren Auflistungen, die Sie entfernen möchten.

3.  Die Eigenschaft **State** für die Auflistung wird in **Commit nicht ausgeführt** aktualisiert. Um für die Änderungen ein Commit auszuführen und die Auflistung zu löschen, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Commit für alle Elemente ausführen**.

4.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.

5.  Klicken Sie im Dialogfeld **Systemsteuerung für Microsoft Lync Server 2013** auf **OK**.

6.  Wenn Sie Ihre Meinung ändern und die Auflistung nicht löschen möchten, klicken Sie auf **Commit ausführen**, und klicken Sie dann auf **Alle noch nicht übernommenen Änderungen verwerfen**. Wenn das Dialogfeld **Systemsteuerung für Microsoft Lync Server 2013** angezeigt wird, klicken Sie auf **OK**.

## Entfernen der Trunkkonfigurationseinstellungen mithilfe der Lync Server-PowerShell-Cmdlets

Trunkkonfigurationseinstellungen können auch mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsTrunkConfiguration** entfernt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Entfernen einer angegebenen Auflistung von Einstellungen

  - Mit dem folgenden Befehl werden die Trunkkonfigurationseinstellungen gelöscht, die auf den Standort "Redmond" angewendet wurden:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

## Entfernen aller auf Standortebene angewendeten Auflistungen

  - Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, die auf Dienstebene angewendet wurden:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

## Entfernen aller Auflistungen, bei denen die Medienumgehung aktiviert ist

  - Mit dem folgenden Befehl werden alle Trunkkonfigurationseinstellungen entfernt, bei denen die Medienumgehung aktiviert ist:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

Weitere Informationen finden Sie im Hilfethema für das [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration)-Cmdlet.

