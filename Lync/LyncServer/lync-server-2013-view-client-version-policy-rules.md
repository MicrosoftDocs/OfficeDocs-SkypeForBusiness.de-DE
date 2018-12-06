---
title: Anzeigen von Regeln für Clientversionsrichtlinien
TOCTitle: Anzeigen von Regeln für Clientversionsrichtlinien
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ923060(v=OCS.15)
ms:contentKeyID: 52056501
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Regeln für Clientversionsrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Eine Clientversionsrichtlinie besteht aus einer Reihe von Regeln für Clientversionsrichtlinien. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten. Sie können die Regeln für Clientversionsrichtlinien über die Systemsteuerung für Lync Server 2013 oder die Verwaltungsshell für Lync Server 2013 anzeigen.

## So zeigen Sie Regeln für Clientversionsrichtlinien mithilfe der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionsrichtlinie**.

4.  Doppelklicken Sie auf der Seite **Clientversionsrichtlinie** auf eine Clientversionsrichtlinie, die Sie anzeigen möchten.

5.  Die Regeln werden auf der Seite **Clientversionsrichtlinie bearbeiten** angezeigt. Sie können die Details einer Regel anzeigen, indem Sie die Regel markieren und dann auf **Details einblenden** klicken.

## Anzeigen der Regeln für Clientversionsrichtlinien mithilfe der Windows PowerShell-Cmdlets

Sie können die Regeln für Clientversionsrichtlinien mit der Lync Server-Verwaltungsshell und dem **Get-CsClientVersionPolicyRule**-Cmdlet anzeigen. Dieses Cmdlet kann entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung der Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Regeln für Clientversionsrichtlinien an

  - Geben Sie zum Anzeigen der Regeln für Clientversionsrichtlinien den folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsClientVersionPolicyRule
    
    Für jede konfigurierte Regel werden Informationen ähnlich wie die folgenden zurückgegeben:
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

Weitere Informationen finden Sie im Hilfethema für das [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicyRule)-Cmdlet.

