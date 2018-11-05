---
title: Anzeigen von Informationen zu Geräteaktualisierungsregeln
TOCTitle: Anzeigen von Informationen zu Geräteaktualisierungsregeln
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994077(v=OCS.15)
ms:contentKeyID: 52056465
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Geräteaktualisierungsregeln

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können detaillierte Informationen zu bereits importierten Geräteupdateregeln anzeigen, einschließlich Typ, Modell und Marke der Geräte, auf die das Update zutrifft, Version und Typ des Updates sowie Gebietsschema und Pool für das Update. Die Informationen stehen für alle importierten Geräteupdateregeln zur Verfügung – Regeln mit ausstehender Genehmigung, bereitgestellte (genehmigte), zurückgerufene (wiederhergestellte) und nicht verwendete (zurückgesetzte) Regeln. Sie können entweder über die Lync Server-Systemsteuerung oder die Windows PowerShell auf diese Informationen zugreifen.


> [!NOTE]
> Ausführliche Informationen zum Importieren, Genehmigen, Zurücksetzen, Wiederherstellen und Entfernen von Regeln finden Sie in den Themen, die unter <A href="lync-server-2013-device-update-rules.md">Geräteaktualisierungsregeln in Lync Server&nbsp;2013</A> aufgelistet sind.



## So zeigen Sie Geräteupdateregeln mithilfe der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Geräteupdate**. Auf der Seite **Geräteupdate** werden die importierten Regeln aufgelistet.

## Anzeigen von Geräteupdateregeln mit den Windows PowerShell-Cmdlets

Detaillierte Informationen zu allen Geräteupdateregeln können Sie auch mithilfe der Windows PowerShell und dem **Get-CsDeviceUpdateRule**-Cmdlet anzeigen. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.


> [!NOTE]
> Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server&nbsp;Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## So zeigen Sie alle Geräteupdateregeln an

  - Der folgende Befehl gibt Informationen zu allen Geräteupdateregeln zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:
    
        Get-CsDeviceUpdateRule
    
    Der Befehl gibt für jede Geräteupdateregel ähnliche Informationen wie die folgenden zurück:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## So zeigen Sie alle Geräteupdateregeln auf einem bestimmten Webserver an

  - Um Geräteupdateregeln auf einem bestimmten Computer anzuzeigen, verwenden Sie den Parameter "Filter" gefolgt von der Serveridentität und dem Platzhalterzeichen (\*). Beispiel:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

Einzelheiten dazu finden Sie im Hilfethema zum Cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule).

