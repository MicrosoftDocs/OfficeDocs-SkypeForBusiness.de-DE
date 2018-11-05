---
title: Anzeigen von Konfigurationseinstellungen für Clientversionen
TOCTitle: Anzeigen von Konfigurationseinstellungen für Clientversionen
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ923062(v=OCS.15)
ms:contentKeyID: 52056439
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Konfigurationseinstellungen für Clientversionen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Konfigurationseinstellungen für Clientversionen werden verwendet, um die Clientversionskontrolle zu aktivieren und zu deaktivieren. Die globale Clientversionskonfiguration wird zusammen mit Lync Server 2013 installiert und zum Aktivieren bzw. Deaktivieren der Clientversionskontrolle für die gesamte Serverbereitstellung verwendet. Wenn die globale Konfiguration aktiviert ist, werden alle eingerichteten Clientversionsrichtlinien bei der Anmeldung von Benutzern wirksam. Sie können Konfigurationseinstellungen für Clientversionen über die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013 anzeigen.


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.



## So zeigen Sie Konfigurationseinstellungen für Clientversionen mithilfe der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionskonfiguration**.

4.  Doppelklicken Sie auf den Namen der Clientversionskonfiguration, die Sie anzeigen möchten.

## Anzeigen der Konfigurationseinstellungen für Clientversionen mithilfe der Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen für Clientversionen mithilfe des **Get-CsClientVersionConfiguration**-Cmdlets anzeigen. Dieses Cmdlet kann entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Informationen zur Clientversionskonfiguration an

  - Um Informationen zu allen Konfigurationseinstellungen für Clientversionen anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsClientVersionConfiguration
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionConfiguration).

