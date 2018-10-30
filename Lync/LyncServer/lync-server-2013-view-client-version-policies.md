---
title: Anzeigen von Clientversionsrichtlinien
TOCTitle: Anzeigen von Clientversionsrichtlinien
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ898479(v=OCS.15)
ms:contentKeyID: 52056362
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Clientversionsrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Clientversionsrichtlinien dienen zum Anwenden einer Reihe von Regeln für die Clientversionsverwaltung entweder auf globaler Ebene oder auf bestimmte Standorte, Pools oder Benutzergruppen. Sie können die in Ihrer Lync Server 2013-Umgebung konfigurierten Clientversionsrichtlinien entweder in der Systemsteuerung für Lync Server 2013 oder in der Verwaltungsshell für Lync Server 2013 anzeigen.

## So zeigen Sie Clientversionsrichtlinien mithilfe der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Clientversionsrichtlinie**.

4.  Wenn Sie die Regeln für eine Clientversionsrichtlinie auf der Seite **Clientversionsrichtlinie** anzeigen möchten, doppelklicken Sie auf die anzuzeigende Richtlinie.

## Anzeigen von Clientversionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können Clientversionsrichtlinien mithilfe des Cmdlets **Get-CsClientVersionPolicy** anzeigen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Clientversionsrichtlinien an

  - Zum Anzeigen von Informationen zu allen Ihren Clientversionsrichtlinien geben Sie in der Lync Server-Verwaltungsshell folgenden Befehl ein und drücken dann die EINGABETASTE:
    
        Get-CsClientVersionPolicy
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientVersionPolicy).

