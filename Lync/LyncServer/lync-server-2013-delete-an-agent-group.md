---
title: Löschen einer Agentgruppe
TOCTitle: Löschen einer Agentgruppe
ms:assetid: df385fd1-62f4-42b7-a349-4eb38dea50c8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182597(v=OCS.15)
ms:contentKeyID: 49295646
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer Agentgruppe

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren, um eine Agentgruppe zu löschen.

## So löschen Sie eine Agentgruppe mithilfe der Lync Server-Systemsteuerung

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Reaktionsgruppen** und dann auf **Gruppe**.

4.  Geben Sie auf der Seite **Reaktionsgruppen** im Suchfeld einen Teil oder den vollständigen Namen der Agentgruppe ein, die Sie löschen möchten.

5.  Klicken Sie in der Ergebnisliste auf die Gruppe, die Sie löschen möchten, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

6.  Klicken Sie auf **OK**.

## So löschen Sie eine Agentgruppe mithilfe der Cmdlets

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Get-CsRgsAgentGroup -Identity <Application Server service> -Name "<name of agent group>" | Remove-CsRgsAgentGroup
    
    Beispiel:
    
        Get-CsRgsAgentGroup -Identity service:ApplicationServer:redmond.contoso.com -Name "Human Resources" | Remove-CsRgsAgentGroup

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Agent-Gruppe in Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)  

#### Weitere Ressourcen

[Remove-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsRgsAgentGroup)

