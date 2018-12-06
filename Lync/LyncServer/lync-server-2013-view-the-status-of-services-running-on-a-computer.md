---
title: Anzeigen des Status der Dienste, die auf einem Computer ausgeführt werden in Lync Server 2013
TOCTitle: Anzeigen des Status der Dienste, die auf einem Computer ausgeführt werden in Lync Server 2013
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182606(v=OCS.15)
ms:contentKeyID: 49295896
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen des Status der Dienste, die auf einem Computer ausgeführt werden in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Über die Systemsteuerung für Lync Server 2013 können Sie alle Dienste, die auf einem bestimmten Computer in Ihrer Lync Server-Topologie ausgeführt werden, sowie den Status der einzelnen Dienste anzeigen.

## So zeigen Sie den Status von Diensten an, die auf einem Computer ausgeführt werden

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie**.

4.  Navigieren Sie auf der Seite **Status** zum gewünschten Computer, indem Sie die Liste sortieren oder durchsuchen, und klicken Sie anschließend auf den Computernamen.

5.  Führen Sie einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Dienststatus abrufen**, um den letzten Status der Dienste anzuzeigen, die auf dem Computer ausgeführt werden.
    
      - Zum Anzeigen einer Liste der einzelnen Dienste, die auf dem Computer ausgeführt werden, sowie des jeweiligen Status klicken Sie auf **Eigenschaften** und anschließend auf **Schließen**, um zur Liste zurückzukehren.

## Anzeigen des Dienststatus mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können den Dienststatus auch mithilfe von Lync Server-Verwaltungsshell und des **Get-CsWindowsService**-Cmdlets anzeigen. Dieses Cmdlet können Sie entweder in Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## So zeigen Sie den Dienststatus an

  - Zum Anzeigen des Dienststatus auf einem Computer geben Sie in Lync Server-Verwaltungsshell einen Befehl ähnlich dem folgenden ein, und drücken Sie die EINGABETASTE:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

Ausführliche Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

