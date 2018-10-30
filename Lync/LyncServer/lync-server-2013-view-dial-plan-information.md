---
title: Anzeigen von Informationen zu Wählplänen in Lync Server 2013
TOCTitle: Anzeigen von Informationen zu Wählplänen in Lync Server 2013
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49890667
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Wählplänen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Führen Sie die folgenden Schritte aus, um Informationen für einen vorhandenen Wählplan anzuzeigen. Informationen zum Erstellen eines neuen Wählplans finden Sie unter[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## So zeigen Sie Informationen zu einem Wählplan in Lync Server-Systemsteuerung an

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Wähleinstellungen**.

4.  Doppelklicken Sie auf der Seite **Wähleinstellungen** auf einen Satz mit Wähleinstellungen.
    

    > [!NOTE]
    > Sie können jeweils nur Informationen zu einem Wählplan anzeigen.



## Anzeigen von Wähleinstellungen mithilfe von Windows PowerShell-Cmdlets

  - Wählpläne können auch mithilfe der Windows PowerShell-Befehlszeilenschnittstelle und dem Cmdlet **Get-CsDialPlan** angezeigt werden. Das Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Zum Anzeigen von Informationen zu allen Wählplänen geben Sie den folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsDialPlan
    
    Dieser Befehl gibt Informationen wie die folgenden zurück:
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## Siehe auch

#### Aufgaben

[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

