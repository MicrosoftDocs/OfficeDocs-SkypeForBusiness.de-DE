---
title: Anwenden einer Archivierungsrichtlinie auf Benutzer
TOCTitle: Anwenden einer Archivierungsrichtlinie auf Benutzer
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521004(v=OCS.15)
ms:contentKeyID: 49294193
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anwenden einer Archivierungsrichtlinie auf Benutzer

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn ein Benutzer für Lync Server 2013 aktiviert wurde und Sie eine oder mehrere Benutzerrichtlinien für die Archivierung von Benutzern erstellt haben, die in Lync Server 2013 untergebracht sind, können Sie für einzelne Benutzer Archivierungsunterstützung implementieren, indem Sie auf diese Benutzer oder Benutzergruppen die entsprechenden Richtlinien anwenden. Wenn Sie zum Beispiel eine Richtlinie zur Unterstützung der Archivierung von internen Kommunikationsvorgängen erstellen, können Sie diese auf mindestens einen Benutzer oder eine Benutzergruppe anwenden, um die Archivierung von deren Kommunikation in Lync Server 2013 zu unterstützen.


> [!NOTE]
> Wenn Sie bei Ihrer Bereitstellung Microsoft Exchange-Integration aktiviert haben, steuern Exchange- Compliance-Archivrichtlinien, ob für die auf Exchange 2013 befindlichen Benutzer Archivierung aktiviert ist und deren Postfächer archiviert werden sollen. Einzelheiten dazu finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.<BR>Bevor Sie Archivierung aktivieren, sollten Sie in den Archivierungskonfigurationen alle entsprechenden Optionen angeben. Weitere Informationen dazu finden Sie in der Betriebsdokumentation unter <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools</A>.



Gehen Sie nach der in diesem Thema aufgeführten Anleitung vor, um eine zuvor erstellte Benutzerrichtlinie für Archivierung auf eine oder mehrere Benutzerkonten oder -gruppen anzuwenden.

## So wenden Sie eine Benutzerrichtlinie für die Archivierung auf ein Benutzerkonto an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**, und suchen Sie dann nach dem Benutzerkonto, das Sie konfigurieren möchten.

4.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Wählen Sie in **Lync Server-Benutzer bearbeiten** unter **Archivierungsrichtlinie** die Benutzerrichtlinie für Archivierung aus, die Sie anwenden möchten.
    

    > [!NOTE]
    > Mit den Einstellungen <STRONG>&lt;Automatisch&gt;</STRONG> werden die Standardeinstellungen der Serverinstallation angewendet. Diese Einstellungen werden vom Server automatisch übernommen.



6.  Klicken Sie auf **Commit**.

## Zuweisen einer benutzerbezogenen Archivierungsrichtlinie mithilfe des Lync Server-Verwaltungsshell-Cmdlets

Benutzerbezogene Archivierungsrichtlinien können auch mithilfe der Lync ServerWindows PowerShell und dem **Grant-CsArchivingPolicy**-Cmdlet zugewiesen werden. Dieses Cmdlet können Sie entweder von der Verwaltungsshell für Lync Server 2013 aus oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Zuweisen einer benutzerbezogenen Archivierungsrichtlinie zu einem einzelnen Benutzer

  - Mit dem folgenden Befehl wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer "Ken Myer" zugewiesen.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Zuweisen einer benutzerbezogenen Archivierungsrichtlinie zu mehreren Benutzern

  - Der folgende Befehl weist die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zu, deren Konten sich auf dem Registrierungsstellenpool "atl-cs-001.litwareinc.com" befinden. Einzelheiten über den in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Aufheben der Zuweisung einer benutzerbezogenen Archivierungsrichtlinie

  - Der folgende Befehl hebt alle bestehenden Zuweisungen von benutzerbezogenen Archivierungsrichtlinien zu "Ken Myer" auf. Danach wird Ken Myer automatisch von der globalen Richtlinie oder, wenn vorhanden, von der Richtlinie für seinen lokalen Standort verwaltet. (Standortrichtlinien haben Vorrang vor der globalen Richtlinie).
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Details dazu finden Sie in der Dokumentation zum [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy)-Cmdlet.

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)

